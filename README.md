# 🦷 dental-glow-by-claude

> **این پروژه یه لندینگ پیج سادس — اما ایده پشتش با هوش مصنوعی ساخته شده.**
> می‌شه با همین روش، یه سایت کامل یا حتی یه محصول واقعی برای مشتری ساخت.

---

## 💡 ایده چیه؟

وقتی برای یه سایت محصول یا خدمات یه عکس معمولی داری، کاربر چیز خاصی نمی‌بینه.
ولی اگه همون عکس با یه افکت X-Ray ترکیب بشه — **کاربر کنجکاو می‌شه، موس می‌کشه، درگیر می‌شه.**

این پروژه دقیقاً همین کار رو می‌کنه:
- عکس ۱ → نمای بیرونی محصول یا خدمات (لبخند زیبا)
- عکس ۲ → نمای داخلی / X-Ray (ایمپلنت و ساختار دندان)
- افکت → موس که روی تصویر می‌ره، لایه X-Ray با یه دایره نرم و مه‌آلود reveal می‌شه

---

## 🖼️ مرحله ۱ — ساخت عکس‌ها با ChatGPT

برای هر محصول یا خدماتی می‌تونی دو عکس مشابه بسازی.
کافیه تو ChatGPT (نسخه با DALL·E) این پرامپت رو بدی و فقط **اسم محصولت** رو جاش بذاری:

<details>
<summary>📋 پرامپت ساخت عکس (کلیک کن)</summary>

```
Create a premium landing-page product visual set for [نام محصول].

Generate TWO separate images of the exact same product, with identical
shape, proportions, design language, perspective, and overall identity.

========================
IMAGE 1 — CLEAN HERO PRODUCT SHOT
========================
Create a highly realistic studio product photo of [نام محصول] placed
naturally on a clean white seamless background.

Requirements:
- ultra-realistic product photography
- premium commercial / landing page hero style
- the product must be standing or placed naturally on the ground / surface, not floating
- background pure white or very light white studio backdrop
- product color should contrast beautifully with the white background:
  prefer deep navy blue, royal blue, dark metallic blue, or another elegant
  premium color if suitable for the product
- soft realistic studio shadows under the product
- glossy or semi-matte premium material rendering depending on the product type
- clean reflections, polished details, realistic textures
- minimal composition, centered or slightly offset for modern website hero section
- no props, no people, no text, no logos, no watermark
- lighting should be soft, controlled, high-end studio lighting
- shot should feel like an expensive website hero image for a premium brand
- camera angle: 3/4 front perspective unless a better angle suits the product
- product must look physically grounded, realistic, elegant, and market-ready

========================
IMAGE 2 — XRAY / TRANSPARENT CUTAWAY VERSION
========================
Create a second image of the exact same [نام محصول] from the same angle,
same composition, same scale, and same position as Image 1, but in a
premium x-ray / transparent cutaway visualization style.

Requirements:
- preserve the exact same product identity, silhouette, dimensions,
  proportions, and viewpoint from Image 1
- same white studio background
- same composition and hero framing
- product outer shell should be semi-transparent / x-ray-like
- reveal the internal components, structure, layers, mechanisms, materials,
  or construction of the product in a visually stunning and realistic way
- internal parts should look detailed, premium, believable, and neatly organized
- use a clean high-end transparent blue / glass / x-ray visual language
- the exterior should still remain visible enough so the product silhouette
  is instantly recognizable
- cinematic but clean technical-commercial style
- realistic shadows and subtle studio reflections
- no exploded view unless it naturally improves readability
- no labels, no arrows, no text, no infographic elements
- not cartoonish, not sketchy — it must look like a premium CGI / technical
  visualization made for a modern product landing page
- the final result should feel like a luxury website section showing
  "outside + inside" of the same product

========================
GLOBAL ART DIRECTION
========================
- both images must feel like part of the same landing page design system
- modern premium commercial aesthetic
- clean, minimal, high-end, realistic
- sharp focus, detailed materials, elegant lighting
- no clutter
- suitable for website hero / landing page / premium product presentation
- output should look like a blend of luxury product photography and
  high-end product CGI visualization

IMPORTANT:
Image 2 must be the exact same product as Image 1, with the same geometry,
same camera angle, same framing, same position, and same scale.
The only difference is that Image 2 should transform the product into a
transparent x-ray / cutaway version that reveals the internals while
preserving the outer form. Do not redesign the product between the two images.
```

</details>

---

## 📁 مرحله ۲ — جایگذاری عکس‌ها

بعد از ساخت عکس‌ها، اون‌ها رو تو فولدر پروژه بذار و اسمشون رو اینطوری تغییر بده:

```
عکس ۱ (نمای معمولی)  →  after.png
عکس ۲ (نمای X-Ray)   →  before.png
```

جایگزین عکس‌های فعلی پروژه بشن — تمام!

---

## 🤖 مرحله ۳ — ساخت سایت با Claude

اگه خواستی از صفر با عکس‌های خودت سایت بسازی، این پرامپت رو **به همراه دو عکس** به Claude بده:

<details>
<summary>📋 پرامپت ساخت سایت برای Claude (کلیک کن)</summary>

```
Build a professional landing page using pure HTML/CSS/JS (no frameworks).
Language: Persian (Farsi), direction: RTL, font: Vazirmatn from Google Fonts.

I'm giving you two images:
- after.png  → normal product/service photo (base layer)
- before.png → x-ray/internal/cutaway version (reveal layer)

HERO — main effect:
Stack the two images on top of each other covering the full viewport width
(height: 72vh, object-fit: cover). after.png is the base layer (always
visible). before.png sits on top, fully hidden via CSS mask-image. When
the mouse enters the hero, a large soft circle (~270px radius) follows the
cursor and reveals the x-ray image underneath. The circle edges must be
heavily feathered using multiple gradient stops:
  black 0%, black 25%, rgba(0,0,0,.75) 42%, rgba(0,0,0,.4) 58%,
  rgba(0,0,0,.12) 74%, transparent 100%
No hard edges — foggy and smooth like a spotlight. Hide the system cursor
inside the hero and show a custom glowing cyan ring instead. Apply a short
white fade overlay (~16% height) at the bottom of the hero.

BELOW HERO (white section):
Centered layout with: status pill tag + large heading + description +
two CTA buttons + three small inline stat badges.

REST OF PAGE (in order):
1. Stats bar — 4 numbers with Persian count-up animation on scroll
2. Services grid — 6 cards with hover lift and colored top border animation
3. "Why Us" section — dark blue gradient, 4 glassmorphism feature rows + contact card
4. Testimonials — 3 patient review cards with stars and avatars
5. CTA banner — gradient card with two buttons
6. Full footer — 4 columns

Navbar: fixed, transparent over hero, transitions to white + blur on scroll.
Animations: fade-up via IntersectionObserver on all sections with staggered delays.
Colors: primary #0891b2, deep #0c4a6e, accent #06b6d4, background #f0f9ff.
```

</details>

---

## 📂 ساختار فایل‌ها

```
dental-glow-by-claude/
├── index.html     ← کل سایت در یک فایل
├── after.png      ← عکس ۱ (نمای معمولی)
├── before.png     ← عکس ۲ (نمای X-Ray)
└── README.md
```

---

## 🚀 اجرا

هیچ نصبی لازم نیست — فقط فایل `index.html` رو تو مرورگر باز کن.

```bash
git clone https://github.com/msadeghkarimi/dental-glow-by-claude.git
cd dental-glow-by-claude
# فایل index.html رو باز کن
```

---

## 🛠️ تکنولوژی

| | |
|---|---|
| HTML5 | ساختار |
| CSS3 | mask-image، grid، backdrop-filter، custom properties |
| JavaScript | IntersectionObserver، reveal effect، count-up |
| Font | Vazirmatn — Google Fonts |

---

## ⚠️ نکته مهم

این پروژه **یه لندینگ پیج سادست** — اما ایده و اجرای کامل اون با هوش مصنوعی ساخته شده.
با همین روش می‌شه یه **سایت کامل** یا یه **محصول واقعی برای مشتری** ساخت —
بدون اینکه یه خط کد دستی بنویسی.

---

## 📲 آموزش طراحی سایت بدون کدنویسی

می‌خوای یاد بگیری چطور با هوش مصنوعی سایت طراحی کنی — **بدون هیچ خط کدی**؟

👉 پیج **[@msadeghkarimi](https://instagram.com/msadeghkarimi)** رو دنبال کن.

---

> 🤖 این پروژه توسط **Claude Sonnet** (Anthropic) طراحی و کد نویسی شده است.
