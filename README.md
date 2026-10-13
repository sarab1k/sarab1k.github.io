<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>سار | مجلة إخبارية وثقافية شاملة</title>
    <style>
        :root {
            --primary: #0f172a;
            --accent: #2563eb;
            --accent-hover: #1d4ed8;
            --bg: #f8fafc;
            --card-bg: #ffffff;
            --text-main: #1e293b;
            --text-muted: #64748b;
            --border: #e2e8f0;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg);
            color: var(--text-main);
            line-height: 1.6;
        }

        /* Header & Navigation */
        header {
            background-color: var(--primary);
            color: #fff;
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 1.5rem;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: #fff;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .logo span {
            background: var(--accent);
            padding: 2px 8px;
            border-radius: 6px;
            font-size: 1rem;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 1.5rem;
        }

        nav a {
            color: #cbd5e1;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.2s;
        }

        nav a:hover {
            color: #fff;
        }

        /* Ticker Bar */
        .ticker {
            background: #1e293b;
            color: #94a3b8;
            font-size: 0.9rem;
            padding: 0.5rem 0;
            border-bottom: 1px solid #334155;
        }

        .ticker-content {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .ticker-badge {
            background: #ef4444;
            color: white;
            padding: 2px 8px;
            border-radius: 4px;
            font-weight: bold;
            font-size: 0.75rem;
        }

        /* Main Layout */
        .main-layout {
            display: grid;
            grid-template-columns: 2.8fr 1fr;
            gap: 2rem;
            margin-top: 2rem;
            margin-bottom: 3rem;
        }

        @media (max-width: 900px) {
            .main-layout {
                grid-template-columns: 1fr;
            }
            nav {
                display: none; /* ينصح بإضافة قائمة هاتف مستقبلاً */
            }
        }

        /* Featured Article */
        .featured-card {
            background: var(--card-bg);
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid var(--border);
            margin-bottom: 2rem;
            box-shadow: 0 4px 6px -1px rgba(0,0,0,0.05);
        }

        .featured-img {
            width: 100%;
            height: 350px;
            object-fit: cover;
            background-color: #cbd5e1;
        }

        .featured-info {
            padding: 1.5rem;
        }

        .tag {
            display: inline-block;
            background: #dbeafe;
            color: var(--accent);
            padding: 4px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
            margin-bottom: 0.5rem;
        }

        .featured-title {
            font-size: 1.8rem;
            margin-bottom: 0.75rem;
            color: var(--primary);
        }

        .meta-date {
            font-size: 0.85rem;
            color: var(--text-muted);
            margin-bottom: 0.75rem;
        }

        /* Articles Grid */
        .grid-title {
            font-size: 1.4rem;
            margin-bottom: 1rem;
            padding-bottom: 0.5rem;
            border-bottom: 2px solid var(--accent);
        }

        .articles-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.5rem;
        }

        .article-card {
            background: var(--card-bg);
            border-radius: 10px;
            overflow: hidden;
            border: 1px solid var(--border);
            transition: transform 0.2s, box-shadow 0.2s;
        }

        .article-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
        }

        .article-img {
            width: 100%;
            height: 180px;
            object-fit: cover;
            background-color: #e2e8f0;
        }

        .article-body {
            padding: 1rem;
        }

        .article-title {
            font-size: 1.1rem;
            margin: 0.5rem 0;
            color: var(--primary);
        }

        .article-desc {
            font-size: 0.9rem;
            color: var(--text-muted);
            margin-bottom: 1rem;
        }

        /* Sidebar Widgets */
        .widget {
            background: var(--card-bg);
            border-radius: 10px;
            padding: 1.25rem;
            border: 1px solid var(--border);
            margin-bottom: 1.5rem;
        }

        .widget-title {
            font-size: 1.1rem;
            margin-bottom: 1rem;
            padding-bottom: 0.4rem;
            border-bottom: 2px solid var(--primary);
        }

        .popular-list {
            list-style: none;
        }

        .popular-item {
            padding: 0.5rem 0;
            border-bottom: 1px dashed var(--border);
        }

        .popular-item:last-child {
            border-bottom: none;
        }

        .popular-link {
            text-decoration: none;
            color: var(--text-main);
            font-weight: 500;
            font-size: 0.95rem;
            transition: color 0.2s;
        }

        .popular-link:hover {
            color: var(--accent);
        }

        /* Newsletter */
        .newsletter-input {
            width: 100%;
            padding: 0.6rem;
            border: 1px solid var(--border);
            border-radius: 6px;
            margin-bottom: 0.6rem;
            font-family: inherit;
        }

        .btn {
            width: 100%;
            background: var(--accent);
            color: white;
            border: none;
            padding: 0.6rem;
            border-radius: 6px;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.2s;
        }

        .btn:hover {
            background: var(--accent-hover);
        }

        /* Footer */
        footer {
            background: var(--primary);
            color: #94a3b8;
            text-align: center;
            padding: 2rem 0;
            margin-top: auto;
            border-top: 1px solid #334155;
        }

        footer p {
            font-size: 0.9rem;
        }
    </style>
</head>
<body>

    <!-- الترويسة الرئيسية -->
    <header>
        <div class="container header-content">
            <a href="#" class="logo">
                سار <span>مجلة</span>
            </a>
            <nav>
                <ul>
                    <li><a href="#">الرئيسية</a></li>
                    <li><a href="#">تقنية</a></li>
                    <li><a href="#">تطبيقات</a></li>
                    <li><a href="#">مقالات</a></li>
                    <li><a href="#">ثقافة</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- شريط الأخبار العاجلة -->
    <div class="ticker">
        <div class="container ticker-content">
            <span class="ticker-badge">عاجل</span>
            <span>مرحباً بكم في منصة "سار" النشرية الرسمية بحلتها الجديدة.</span>
        </div>
    </div>

    <!-- محتوى الصفحة الرئيسي -->
    <div class="container main-layout">

        <!-- القسم الأيمن: المقالات والأخبار -->
        <main>
            <!-- المقال البارز في الأعلى -->
            <article class="featured-card">
                <img src="https://picsum.photos/800/400?random=1" alt="غلاف المقال الرئيسي" class="featured-img">
                <div class="featured-info">
                    <span class="tag">مقال غلاف</span>
                    <div class="meta-date">نُشر قبل ساعتين • بواسطة المحرر</div>
                    <h2 class="featured-title">انطلاق منصة سار النشرية للتطبيقات والمقالات الثقافية والتقنية</h2>
                    <p class="article-desc">يسرنا الإعلان عن إطلاق الواجهة الجديدة لموقع سار، لتكون المنصة الشاملة لنشر المقالات، الأدوات، والقوالب الجاهزة بصورة مجانية ومفتوحة للجميع.</p>
                </div>
            </article>

            <!-- شبكة أحدث المقالات -->
            <h3 class="grid-title">أحدث المقالات والنشرات</h3>
            <div class="articles-grid">

                <article class="article-card">
                    <img src="https://picsum.photos/400/250?random=2" alt="مقال تقني" class="article-img">
                    <div class="article-body">
                        <span class="tag">تقنية</span>
                        <h4 class="article-title">كيف تبني موقعك الشخصي مجاناً؟</h4>
                        <p class="article-desc">دليل خطوة بخطوة لبناء واستضافة موقعك بدون تكاليف شهرية.</p>
                    </div>
                </article>

                <article class="article-card">
                    <img src="https://picsum.photos/400/250?random=3" alt="مقال تطبيقات" class="article-img">
                    <div class="article-body">
                        <span class="tag">تطبيقات</span>
                        <h4 class="article-title">أفضل أدوات تطوير تطبيقات الهاتف</h4>
                        <p class="article-desc">مراجعة شاملة لأحدث بيئات التطوير السريعة وتصميم الواجهات.</p>
                    </div>
                </article>

                <article class="article-card">
                    <img src="https://picsum.photos/400/250?random=4" alt="مقال تصميم" class="article-img">
                    <div class="article-body">
                        <span class="tag">تصميم</span>
                        <h4 class="article-title">أساسيات تصميم واجهات المستخدم UI/UX</h4>
                        <p class="article-desc">نصائح عمليّة لجعل موقعك وتطبيقك متوافقاً مع تجربة المستخدم.</p>
                    </div>
                </article>

            </div>
        </main>

        <!-- القسم الأيسر: الشريط الجانبي -->
        <aside>
            <!-- القائمة البريدية -->
            <div class="widget">
                <h4 class="widget-title">النشرة البريدية</h4>
                <p style="font-size: 0.85rem; color: var(--text-muted); margin-bottom: 0.8rem;">اشترك للحصول على أحدث المقالات والنشرات مباشرة.</p>
                <input type="email" class="newsletter-input" placeholder="اكتب بريدك الإلكتروني...">
                <button class="btn">اشتراك</button>
            </div>

            <!-- الأكثر قراءة -->
            <div class="widget">
                <h4 class="widget-title">الأكثر قراءة</h4>
                <ul class="popular-list">
                    <li class="popular-item"><a href="#" class="popular-link">1. إطلاق منصة سار الرسمية</a></li>
                    <li class="popular-item"><a href="#" class="popular-link">2. دليل تطوير الواجهات بلغة HTML & CSS</a></li>
                    <li class="popular-item"><a href="#" class="popular-link">3. أحدث القوالب المجانية المتاحة للنشر</a></li>
                </ul>
            </div>
        </aside>

    </div>

    <!-- التذييل -->
    <footer>
        <div class="container">
            <p>جميع الحقوق محفوظة © 2026 - موقع سار (SAR)</p>
        </div>
    </footer>

</body>
</html>
