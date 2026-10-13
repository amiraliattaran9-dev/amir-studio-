<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Amir Studio | محتوای خلاقانه با AI</title>
<link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;600;800&display=swap" rel="stylesheet">
<style>
* { margin:0; padding:0; box-sizing:border-box; }

:root {
  --turquoise: #00e5d4;
  --purple: #8b5cf6;
  --green: #22ff88;
  --bg-dark: #05070f;
  --glass: rgba(255,255,255,0.05);
}

body {
  font-family: 'Vazirmatn', sans-serif;
  background: var(--bg-dark);
  color: #e6f1ff;
  overflow-x: hidden;
  min-height: 100vh;
  padding-top: 70px;
}

body::before {
  content:'';
  position: fixed; inset: 0;
  background:
    radial-gradient(circle at 20% 20%, rgba(0,229,212,0.15), transparent 45%),
    radial-gradient(circle at 80% 30%, rgba(139,92,246,0.18), transparent 45%),
    radial-gradient(circle at 50% 90%, rgba(34,255,136,0.12), transparent 50%);
  z-index: -2;
  animation: bgMove 15s ease-in-out infinite alternate;
}
@keyframes bgMove {
  0% { transform: scale(1) rotate(0deg); }
  100% { transform: scale(1.15) rotate(3deg); }
}

/* ============ هدر ============ */
header {
  position: fixed; top:0; width:100%;
  padding: 18px 5%;
  display:flex; justify-content:space-between; align-items:center;
  backdrop-filter: blur(15px);
  background: rgba(5,7,15,0.75);
  border-bottom: 1px solid rgba(255,255,255,0.06);
  z-index: 100;
}
.logo {
  font-weight:800; font-size:1.3rem;
  background: linear-gradient(90deg, var(--turquoise), var(--purple), var(--green));
  -webkit-background-clip: text; background-clip: text; color: transparent;
  cursor:pointer;
  display:flex; align-items:center; gap:8px;
}
.logo .logo-mark {
  display:inline-flex; align-items:center; justify-content:center;
  width: 36px; height:36px; border-radius:10px;
  background: linear-gradient(135deg, var(--turquoise), var(--purple));
  color: #05070f; font-weight:800;
  box-shadow: 0 0 20px rgba(0,229,212,0.5);
}
nav { display:flex; gap:18px; align-items:center; flex-wrap:wrap; }
nav a {
  color:#a8b8d8; text-decoration:none;
  font-size:0.85rem; transition:0.3s;
  position:relative; padding-bottom: 3px;
  cursor:pointer;
}
nav a:hover, nav a.active { color: var(--turquoise); }
nav a.active::after {
  content:''; position:absolute; bottom:-8px; right:0; left:0;
  height:2px; background: var(--turquoise); border-radius:2px;
}
.menu-toggle {
  display:none; background:none; border:none;
  color: var(--turquoise); font-size:1.6rem; cursor:pointer;
}

/* ============ صفحات ============ */
.page { display: none; }
.page.active { display: block; }
section { padding: 60px 5% 80px; animation: pageIn 0.5s ease; }
@keyframes pageIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

.page-title {
  text-align:center; font-size: 2.4rem; font-weight:800;
  margin-bottom: 15px;
}
.page-title .grad {
  background: linear-gradient(90deg, var(--turquoise), var(--purple), var(--green));
  -webkit-background-clip:text; background-clip:text; color:transparent;
}
.page-sub {
  text-align:center; color:#8898b8; margin-bottom: 50px;
  font-size:1rem;
}

/* ============ هیرو ============ */
.hero {
  min-height: 75vh;
  display:flex; align-items:center; justify-content:center;
  padding: 60px 5%;
}
.hero-inner { max-width: 900px; text-align:center; }
.hero h1 {
  font-size: 3rem; font-weight:800; line-height:1.3;
  margin-bottom: 20px;
}
.hero h1 .grad {
  background: linear-gradient(90deg, var(--turquoise), var(--purple), var(--green));
  -webkit-background-clip:text; background-clip:text; color:transparent;
}
.hero p {
  font-size: 1.1rem; color:#a8b8d8; line-height:2;
  margin-bottom: 35px; max-width: 650px; margin-inline:auto;
}
.hero .btns {
  display:flex; gap:15px; justify-content:center; flex-wrap:wrap;
}

/* ============ دسته‌ها ============ */
.categories {
  display:grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 22px;
  max-width: 1200px; margin: 0 auto;
}
.cat-card {
  background: var(--glass);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 20px;
  padding: 35px 25px;
  text-align:center;
  text-decoration:none;
  color: inherit;
  transition: 0.4s;
  position:relative;
  overflow:hidden;
  cursor:pointer;
}
.cat-card::before {
  content:''; position:absolute; inset:0;
  background: linear-gradient(135deg, rgba(0,229,212,0.1), rgba(139,92,246,0.1));
  opacity:0; transition: 0.4s;
}
.cat-card:hover {
  transform: translateY(-10px);
  border-color: rgba(0,229,212,0.5);
  box-shadow: 0 25px 50px rgba(0,229,212,0.15);
}
.cat-card:hover::before { opacity:1; }
.cat-card .ico {
  font-size: 3rem; margin-bottom: 15px;
  position:relative; z-index:1;
  filter: drop-shadow(0 0 15px rgba(0,229,212,0.5));
  display:inline-block;
  transition: 0.4s;
}
.cat-card:hover .ico { transform: scale(1.15) rotate(-8deg); }
.cat-card h3 {
  font-size:1.15rem; margin-bottom:8px;
  position:relative; z-index:1;
}
.cat-card p {
  font-size:0.85rem; color:#8898b8;
  position:relative; z-index:1;
  margin-bottom: 12px;
}
.cat-card .count {
  display:inline-block;
  font-size: 0.72rem;
  padding: 4px 12px;
  border-radius: 20px;
  background: rgba(0,229,212,0.15);
  color: var(--turquoise);
  border: 1px solid rgba(0,229,212,0.3);
  position:relative; z-index:1;
}

/* ============ آمار ============ */
.stats {
  display:grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 20px;
  max-width: 1000px;
  margin: 50px auto 0;
}
.stat-box {
  text-align:center;
  padding: 30px 20px;
  background: var(--glass);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 20px;
}
.stat-box .num {
  font-size: 2.2rem; font-weight:800;
  background: linear-gradient(90deg, var(--turquoise), var(--purple));
  -webkit-background-clip:text; background-clip:text; color:transparent;
  margin-bottom: 8px;
}
.stat-box .lbl { color:#8898b8; font-size:0.85rem; }

/* ============ گالری ============ */
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 25px;
  max-width: 1300px;
  margin: 0 auto;
}
.gallery-item {
  background: var(--glass);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 20px;
  overflow: hidden;
  transition: 0.5s cubic-bezier(0.23, 1, 0.32, 1);
  cursor: pointer;
  position: relative;
}
.gallery-item:hover {
  transform: translateY(-10px);
  border-color: rgba(0,229,212,0.5);
  box-shadow: 0 30px 60px rgba(0,229,212,0.2);
}
.gallery-item::before {
  content:''; position:absolute; top:0; left:0; right:0;
  height:3px;
  background: linear-gradient(90deg, var(--turquoise), var(--purple));
  transform: scaleX(0); transform-origin:right;
  transition: 0.5s; z-index: 3;
}
.gallery-item:hover::before { transform: scaleX(1); }

.gallery-thumb {
  width:100%; height: 230px;
  position:relative; overflow:hidden;
  background: linear-gradient(135deg, rgba(0,229,212,0.1), rgba(139,92,246,0.15));
  display:flex; align-items:center; justify-content:center;
}
.gallery-thumb img {
  width:100%; height:100%;
  object-fit:cover;
  transition: transform 0.6s;
}
.gallery-item:hover .gallery-thumb img {
  transform: scale(1.1);
}
.gallery-thumb .placeholder-emoji {
  font-size: 4.5rem;
  filter: drop-shadow(0 0 25px rgba(0,229,212,0.6));
  transition: 0.5s;
}
.gallery-thumb .play-btn {
  position:absolute;
  width: 65px; height:65px;
  border-radius:50%;
  background: rgba(5,7,15,0.85);
  border: 2px solid var(--turquoise);
  display:flex; align-items:center; justify-content:center;
  font-size:1.5rem; color: var(--turquoise);
  box-shadow: 0 0 30px rgba(0,229,212,0.6);
  transition: 0.3s;
  z-index: 2;
}
.gallery-item:hover .play-btn {
  transform: scale(1.15);
  background: var(--turquoise);
  color: #05070f;
}
.badge-new {
  position:absolute;
  top: 15px; right: 15px;
  z-index: 2;
  background: rgba(5,7,15,0.85);
  border: 1px solid var(--green);
  color: var(--green);
  font-size: 0.72rem;
  padding: 5px 12px;
  border-radius: 20px;
  backdrop-filter: blur(10px);
  font-weight: 600;
}
.gallery-body { padding: 20px 22px 25px; }
.gallery-body h3 {
  font-size:1.1rem; margin-bottom:8px;
  transition: 0.3s;
}
.gallery-item:hover .gallery-body h3 { color: var(--turquoise); }
.gallery-body p {
  color:#8898b8; font-size:0.85rem;
  line-height:1.7; margin-bottom:14px;
}
.gallery-tags {
  display:flex; gap:6px; flex-wrap:wrap;
}
.gallery-tags span {
  font-size:0.7rem; padding:4px 10px;
  border-radius: 12px;
  background: rgba(139,92,246,0.15);
  color: #b8a8ff;
  border: 1px solid rgba(139,92,246,0.25);
}
.gallery-body audio {
  width:100%; margin-top: 12px;
  border-radius: 30px;
}

/* ============ دکمه‌ها ============ */
.btn {
  padding: 14px 30px; border-radius: 50px;
  font-weight:600; text-decoration:none;
  font-family:inherit; font-size:1rem;
  cursor:pointer; transition: 0.4s; border:none;
  display:inline-block;
}
.btn-primary {
  background: linear-gradient(90deg, var(--turquoise), var(--purple));
  color: #05070f;
  box-shadow: 0 0 30px rgba(0,229,212,0.4);
}
.btn-primary:hover {
  box-shadow: 0 0 45px rgba(0,229,212,0.7);
  transform: translateY(-3px);
}
.btn-outline {
  background: transparent; color: var(--turquoise);
  border: 1.5px solid var(--turquoise);
}
.btn-outline:hover {
  background: rgba(0,229,212,0.1);
  transform: translateY(-3px);
}

/* ============ بخش تماس ============ */
.contact-wrap {
  max-width: 900px; margin: 0 auto;
  background: linear-gradient(135deg, rgba(0,229,212,0.08), rgba(139,92,246,0.08));
  border: 1px solid rgba(255,255,255,0.1);
  border-radius: 30px;
  padding: 50px 40px;
  text-align: center;
  backdrop-filter: blur(15px);
}
.contact-wrap h2 {
  font-size: 2rem; margin-bottom: 15px;
}
.contact-wrap > p { color:#a8b8d8; margin-bottom: 35px; }
.contact-grid {
  display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 18px;
}
.contact-item {
  padding: 25px 15px;
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 18px;
  transition: 0.3s;
  text-decoration:none; color: inherit;
  display:block;
}
.contact-item:hover {
  transform: translateY(-5px);
  border-color: var(--turquoise);
  background: rgba(0,229,212,0.08);
}
.contact-item .ico { font-size:1.8rem; margin-bottom:12px; }
.contact-item .label { font-size:0.8rem; color:#8898b8; margin-bottom:5px; }
.contact-item .value { font-weight:600; color:#e6f1ff; font-size:0.95rem; word-break: break-all; }

/* ============ فوتر ============ */
footer {
  text-align: center; padding: 40px 20px;
  color: #5868a8; font-size: 0.85rem;
  border-top: 1px solid rgba(255,255,255,0.05);
  margin-top: 60px;
}

/* ============ واتساپ شناور ============ */
.whatsapp-float {
  position: fixed;
  bottom: 25px; left: 25px;
  width: 60px; height: 60px;
  border-radius: 50%;
  background: linear-gradient(135deg, #25D366, #128C7E);
  display: flex; align-items: center; justify-content: center;
  box-shadow: 0 0 30px rgba(37,211,102,0.6);
  cursor: pointer;
  z-index: 200;
  transition: 0.3s;
  text-decoration: none;
}
.whatsapp-float:hover {
  transform: scale(1.1);
  box-shadow: 0 0 40px rgba(37,211,102,0.9);
}
.whatsapp-float svg {
  width: 32px; height: 32px;
  fill: white;
}

/* ============ ریسپانسیو ============ */
@media (max-width: 850px) {
  .menu-toggle { display:block; }
  nav {
    position: fixed; top:65px; right:0; left:0;
    flex-direction: column;
    background: rgba(5,7,15,0.98);
    backdrop-filter: blur(20px);
    padding: 30px;
    gap:20px;
    transform: translateY(-150%);
    transition: 0.4s;
    border-bottom: 1px solid rgba(255,255,255,0.1);
    z-index: 99;
  }
  nav.open { transform: translateY(0); }
  .page-title { font-size: 1.8rem; }
  .hero h1 { font-size: 2rem; }
  section { padding: 40px 5% 60px; }
  .gallery { grid-template-columns: 1fr; }
  .contact-wrap { padding: 30px 20px; }
}
</style>
</head>
<body>

<!-- ============ هدر ============ -->
<header>
  <div class="logo" onclick="showPage('home')">
    <span class="logo-mark">A</span>
    <span>Amir Studio</span>
  </div>
  <button class="menu-toggle" onclick="document.querySelector('nav').classList.toggle('open')">☰</button>
  <nav id="mainNav">
    <a onclick="showPage('home')" data-page="home">خانه</a>
    <a onclick="showPage('logos')" data-page="logos">لوگوها</a>
    <a onclick="showPage('videos')" data-page="videos">ویدیوها</a>
    <a onclick="showPage('posters')" data-page="posters">پوسترها</a>
    <a onclick="showPage('podcasts')" data-page="podcasts">پادکست‌ها</a>
    <a onclick="showPage('tutorials')" data-page="tutorials">آموزشی</a>
  </nav>
</header>

<!-- ============ صفحه خانه ============ -->
<div class="page active" id="page-home">

  <section class="hero">
    <div class="hero-inner">
      <h1>محتوای <span class="grad">خلاقانه با هوش مصنوعی</span></h1>
      <p>
        استودیو امیر — طراحی لوگو، تولید ویدیوهای انیمیشنی، پوستر تبلیغاتی و پادکست حرفه‌ای.
        با ۵ سال تجربه در خدمت رشد کسب‌وکار شما.
      </p>
      <div class="btns">
        <a onclick="document.getElementById('categories').scrollIntoView({behavior:'smooth'})" class="btn btn-primary">مشاهده نمونه کارها</a>
        <a onclick="document.getElementById('contact').scrollIntoView({behavior:'smooth'})" class="btn btn-outline">درخواست پروژه</a>
      </div>
    </div>
  </section>

  <section id="categories">
    <h2 class="page-title">دسته‌های <span class="grad">نمونه کار</span></h2>
    <p class="page-sub">روی هر دسته کلیک کن تا نمونه کارهای آن را ببینی</p>

    <div class="categories">
      <div class="cat-card" onclick="showPage('logos')">
        <div class="ico">🎨</div>
        <h3>لوگوهای طراحی‌شده</h3>
        <p>لوگوهای اختصاصی با هویت بصری منحصربه‌فرد</p>
        <span class="count">۳ پروژه</span>
      </div>
      <div class="cat-card" onclick="showPage('videos')">
        <div class="ico">🎬</div>
        <h3>ویدیوهای انیمیشنی</h3>
        <p>انیمیشن‌های سه‌بعدی و موشن گرافیک</p>
        <span class="count">۳ پروژه</span>
      </div>
      <div class="cat-card" onclick="showPage('posters')">
        <div class="ico">🖼️</div>
        <h3>پوسترهای تبلیغاتی</h3>
        <p>پوسترهای جذاب برای کمپین‌های تبلیغاتی</p>
        <span class="count">۳ پروژه</span>
      </div>
      <div class="cat-card" onclick="showPage('podcasts')">
        <div class="ico">🎙️</div>
        <h3>پادکست‌ها</h3>
        <p>تولید و میکس پادکست‌های حرفه‌ای</p>
        <span class="count">۳ پروژه</span>
      </div>
      <div class="cat-card" onclick="showPage('tutorials')">
        <div class="ico">📚</div>
        <h3>ویدیوهای آموزشی</h3>
        <p>آموزش‌های تخصصی هوش مصنوعی</p>
        <span class="count">۳ ویدیو</span>
      </div>
    </div>

    <div class="stats">
      <div class="stat-box">
        <div class="num">۵۰+</div>
        <div class="lbl">پروژه موفق</div>
      </div>
      <div class="stat-box">
        <div class="num">۵ سال</div>
        <div class="lbl">سابقه کاری</div>
      </div>
      <div class="stat-box">
        <div class="num">۱۰۰٪</div>
        <div class="lbl">تضمین کیفیت</div>
      </div>
      <div class="stat-box">
        <div class="num">۲۴/۷</div>
        <div class="lbl">پشتیبانی</div>
      </div>
    </div>
  </section>

  <section id="contact">
    <div class="contact-wrap">
      <h2 class="page-title">تماس <span class="grad">با من</span></h2>
      <p>آماده همکاری روی پروژه بعدی شما هستم</p>

      <div class="contact-grid">
        <a href="tel:09333966216" class="contact-item">
          <div class="ico">📞</div>
          <div class="label">تماس مستقیم</div>
          <div class="value">۰۹۳۳۳۹۶۶۲۱۶</div>
        </a>
        <a href="https://wa.me/989333966216" target="_blank" class="contact-item">
          <div class="ico">💚</div>
          <div class="label">واتساپ</div>
          <div class="value">۰۹۳۳۳۹۶۶۲۱۶</div>
        </a>
        <a href="https://t.me/Amiraliattaran" target="_blank" class="contact-item">
          <div class="ico">💬</div>
          <div class="label">تلگرام</div>
          <div class="value">@Amiraliattaran</div>
        </a>
        <a href="mailto:a23736613@gmail.com" class="contact-item">
          <div class="ico">✉️</div>
          <div class="label">ایمیل</div>
          <div class="value">a23736613@gmail.com</div>
        </a>
      </div>
    </div>
  </section>

</div>

<!-- ============ صفحه لوگوها ============ -->
<div class="page" id="page-logos">
  <section>
    <h2 class="page-title">لوگوهای <span class="grad">طراحی‌شده</span></h2>
    <p class="page-sub">مجموعه‌ای از لوگوهای اختصاصی طراحی‌شده برای برندها</p>

    <div class="gallery">

      <div class="gallery-item">
        <div class="gallery-thumb">
          <span class="badge-new">جدید</span>
          <span class="placeholder-emoji">🎨</span>
          <!-- ✏️ عکس لوگو ۱ رو اینجا بذار:
          <img src="assets/logos/logo-1.jpg" alt="لوگو ۱">
          -->
        </div>
        <div class="gallery-body">
          <h3>لوگو نمونه ۱</h3>
          <p>توضیح کوتاه لوگوی اول اینجا قرار می‌گیرد</p>
          <div class="gallery-tags">
            <span>مینیمال</span><span>مدرن</span>
          </div>
        </div>
      </div>

      <div class="gallery-item">
        <div class="gallery-thumb">
          <span class="placeholder-emoji">⚡</span>
        </div>
        <div class="gallery-body">
          <h3>لوگو نمونه ۲</h3>
          <p>توضیح کوتاه لوگوی دوم اینجا قرار می‌گیرد</p>
          <div class="gallery-tags">
            <span>لوکس</span><span>حرفه‌ای</span>
          </div>
        </div>
      </div>

      <div class="gallery-item">
        <div class="gallery-thumb">
          <span class="placeholder-emoji">🌟</span>
        </div>
        <div class="gallery-body">
          <h3>لوگو نمونه ۳</h3>
          <p>توضیح کوتاه لوگوی سوم اینجا قرار می‌گیرد</p>
          <div class="gallery-tags">
            <span>خلاقانه</span><span>مدرن</span>
          </div>
        </div>
      </div>

    </div>
  </section>
</div>

<!-- ============ صفحه ویدیوها ============ -->
<div class="page" id="page-videos">
  <section>
    <h2 class="page-title">ویدیوهای <span class="grad">انیمیشنی</span></h2>
    <p class="page-sub">انیمیشن‌های سه‌بعدی، موشن گرافیک و ویدیوهای تبلیغاتی</p>

    <div class="gallery">

      <div class="gallery-item">
        <div class="gallery-thumb">
          <span class="badge-new">3D</span>
          <span class="placeholder-emoji">🎬</span>
          <div class="play-btn">▶</div>
        </div>
        <div class="gallery-body">
          <h3>ویدیو نمونه ۱</h3>
          <p>توضیح کوتاه ویدیوی اول اینجا قرار می‌گیرد</p>
          <div class="gallery-tags">
            <span>موشن گرافیک</span><span>3D</span>
          </div>
        </div>
      </div>

      <div class="gallery-item">
        <div class="gallery-thumb">
          <span class="placeholder-emoji">✨</span>
          <div class="play-btn">▶</div>
        </div>
        <div class="gallery-body">
          <h3>ویدیو نمونه ۲</h3>
          <p>توضیح کوتاه ویدیوی دوم اینجا قرار می‌گیرد</p>
          <div class="gallery-tags">
            <span>تبلیغاتی</span><span>سینمایی</span>
          </div>
        </div>
      </div>

      <div class="gallery-item">
        <div class="gallery-thumb">
          <span class="placeholder-emoji">🎭</span>
          <div class="play-btn">▶</div>
        </div>
        <div class="gallery-body">
          <h3>ویدیو نمونه ۳</h3>
          <p>توضیح کوتاه ویدیوی سوم اینجا قرار می‌گیرد</p>
          <div class="gallery-tags">
            <span>انیمیشن</span><span>کاراکتر</span>
          </div>
        </div>
      </div>

    </div>
  </section>
</div>

<!-- ============ صفحه پوسترها ============ -->
<div class="page" id="page-posters">
  <section>
    <h2 class="page-title">پوسترهای <span class="grad">تبلیغاتی</span></h2>
    <p class="page-sub">پوسترها