# my-website-3
<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>hamoudi</title>
<style>
/* ===== الخلفية ===== */
body {
    margin: 0;
    font-family: 'Arial', sans-serif;
    background-image: url('https://www.electrodepot.fr/media/wysiwyg/page/conseils-seo/pc_gaming_2.jpeg?frz-v=4380');
    background-size: cover;
    background-position: center;
    overflow-x: hidden;
}

body::before {
    content: "";
    position: fixed;
    width: 100%; height: 100%;
    backdrop-filter: blur(6px);
    background: linear-gradient(to bottom, rgba(0,0,0,0.5), rgba(0,0,0,0.3));
    z-index: -1;
}

/* ===== الشريط العلوي ===== */
.navbar { background-color: blue; padding: 15px; transition: 0.3s; }
.navbar:hover { background-color: black; }

/* ===== الشعار ===== */
.logo {
    position: absolute;
    top: 10px;
    left: 10px;
    background-color: rgb(8, 192, 32);
    padding: 12px 25px;
    border-radius: 12px;
    font-weight: bold;
    font-size: 18px;
    box-shadow: 0 5px 15px rgba(0,0,0,0.4);
}

/* ===== الأزرار في الوسط ===== */
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 70vh;
    gap: 40px;
}
.btn {
    background-color: red;
    color: black;
    padding: 22px 45px;
    border-radius: 25px;
    border: none;
    font-size: 24px;
    cursor: pointer;
    transition: all 0.4s ease;
    box-shadow: 0 5px 20px rgba(0,0,0,0.5);
    opacity: 0;
    transform: translateY(50px);
}
.btn:hover {
    background-color: white;
    color: red;
    transform: translateY(-5px) scale(1.15);
    box-shadow: 0 10px 25px rgba(0,0,0,0.6);
}

/* ===== نافذة البوب أب ===== */
.popup-box {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) scale(0.8);
    background: rgba(255,255,255,0.95);
    padding: 25px;
    border-radius: 20px;
    box-shadow: 0 0 25px rgba(0,0,0,0.6);
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.4s ease, transform 0.4s ease;
    z-index: 10;
    text-align: center;
}
.popup-box.show {
    opacity: 1;
    pointer-events: auto;
    transform: translate(-50%, -50%) scale(1);
}
.popup-box img { max-width: 320px; border-radius: 15px; margin-top: 15px; }
.popup-box .close-btn {
    margin-top: 20px;
    padding: 12px 25px;
    cursor: pointer;
    background-color: red;
    color: white;
    border: none;
    border-radius: 12px;
    font-weight: bold;
    font-size: 16px;
    transition: 0.3s;
}
.popup-box .close-btn:hover {
    background-color: black;
    color: white;
    transform: scale(1.1);
}

/* ===== السوشيال ميديا ===== */
.socials {
    position: fixed;
    bottom: 25px;
    width: 100%;
    display: flex;
    justify-content: center;
    gap: 50px;
}
.social {
    position: relative;
}
.social img {
    width: 50px;
    transition: all 0.3s ease;
    cursor: pointer;
    filter: drop-shadow(0 4px 10px rgba(0,0,0,0.5));
}
.social img:hover { transform: scale(1.6); }

/* ===== QR Codes مع Fade + Scale ===== */
.popup-qr {
    position: absolute;
    bottom: 70px;
    left: 50%;
    transform: translateX(-50%) scale(0.8);
    background: white;
    padding: 12px;
    border-radius: 12px;
    text-align: center;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.3s ease, transform 0.3s ease;
    z-index: 5;
}
.social:hover .popup-qr {
    opacity: 1;
    pointer-events: auto;
    transform: translateX(-50%) scale(1);
}
.popup-qr img { width: 100px; border-radius: 10px; }

/* ===== Animations on load ===== */
@keyframes fadeSlideUp {
    0% { opacity: 0; transform: translateY(50px);}
    100% { opacity: 1; transform: translateY(0);}
}
</style>
</head>
<body>

<div class="navbar"></div>
<div class="logo">✔حمودي✔</div>

<div class="container">
    <button class="btn" onclick="showHamoudi()">حمودي</button>
    <button class="btn" onclick="showIssac()">اسحاق</button>
</div>

<!-- نافذة البوب أب -->
<div class="popup-box" id="popup">
    <div id="popup-content"></div>
    <button class="close-btn" onclick="closePopup()">اغلاق</button>
</div>

<!-- السوشيال ميديا -->
<div class="socials">
    <div class="social">
        <a href="https://www.instagram.com/ishak.hmd09/?hl=ar" target="_blank">
            <img src="https://cdn-icons-png.flaticon.com/512/2111/2111463.png">
        </a>
        <div class="popup-qr">
            <img src="https://api.qrserver.com/v1/create-qr-code/?size=100x100&data=https://www.instagram.com/ishak.hmd09/?hl=ar">
            <br>Instagram
        </div>
    </div>
    <div class="social">
        <a href="https://www.facebook.com/ishak.hamoudi.37?locale=ar_AR" target="_blank">
            <img src="https://cdn-icons-png.flaticon.com/512/733/733547.png">
        </a>
        <div class="popup-qr">
            <img src="https://api.qrserver.com/v1/create-qr-code/?size=100x100&data=https://www.facebook.com/ishak.hamoudi.37?locale=ar_AR">
            <br>Facebook
        </div>
    </div>
    <div class="social">
        <a href="https://www.youtube.com/@ILF-DZ" target="_blank">
            <img src="https://cdn-icons-png.flaticon.com/512/1384/1384060.png">
        </a>
        <div class="popup-qr">
            <img src="https://api.qrserver.com/v1/create-qr-code/?size=100x100&data=https://www.youtube.com/@ILF-DZ">
            <br>YouTube
        </div>
    </div>
</div>

<script>
/* ===== دوال البوب أب ===== */
function showHamoudi() {
    const content = `
        <h2>معلومات حمودي</h2>
        <p>الاسم: اسحاق</p>
        <p>اللقب: حمودي</p>
        <p>تاريخ الميلاد:18-01-2010</p>
        <p>العمر: 16 سنة</p>
        <p>السنة:اولى ثانوي</p>
        <p>القسم: 1علمي6</p>
        <p>الإقامة: الجزائر البليدة</p>
    `;
    document.getElementById('popup-content').innerHTML = content;
    document.getElementById('popup').classList.add('show');
}

function showIssac() {
    const content = `
        <h2>اسحاق</h2>
        <img src="https://i.postimg.cc/bd646TNY/601405870-17869275072484719-2231905291685367876-n.jpg" alt="صورة اسحاق">
    `;
    document.getElementById('popup-content').innerHTML = content;
    document.getElementById('popup').classList.add('show');
}

function closePopup() {
    document.getElementById('popup').classList.remove('show');
}

/* ===== تأثير دخول الأزرار عند تحميل الصفحة ===== */
window.addEventListener('load', () => {
    document.querySelectorAll('.btn').forEach((btn, i) => {
        setTimeout(() => {
            btn.style.animation = 'fadeSlideUp 0.8s forwards';
        }, i * 150);
    });
});
</script>

</body>
</html>
