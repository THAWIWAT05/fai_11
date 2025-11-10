

@เว็บไซต์เซอไพรวันเกิด พี่ฝ้าย  11/1168

เว็บลง เลือกอันแรกแล้วกด สร้างได้เลย:https://render.com/

เว็บfai:
[https://sara-xqlf.onrender.com/](https://fai-11.onrender.com)

วิธีแก้ช่องใส่รหัส (บรรทัดที่ 33)
src/components/ui/OtpInput.jsx


ระวังอาจจะเออเรอตรงเพิ่ม gif จาก 5 เป็นน 7

background: linear-gradient(
        115deg,
        rgba(248, 229, 206, 0.893),
        rgba(167, 230, 247, 0.5),
        rgba(251, 216, 233, 0.507),
        rgba(198, 247, 218, 0.756),
        rgba(250, 236, 197, 0.6)
    );

    เปลียนสีพื้นหลัง อยู่ที่ src/index.css

ถ้าอยากลบหัวใจลอยออก ให้ไปเอา index.htmlเดิมมาใส่(แต่ถ้าลบออกมาจะมีสองตัวนะ จะมีcssกับ ตัรูหัวใจ อยู่ในไฟล?เดียวกัน








<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8" />
        <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
        <meta name="viewport" content="width=device-width, initial-scale=1" />
        <meta name="theme-color" content="#000000" />
        <meta name="description" content="Happy birthday" />
        <link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
        <link rel="preconnect" href="https://fonts.googleapis.com" />
        <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
        <link
            href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600;700&display=swap"
            rel="stylesheet"
        />
        <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />
        <link
            rel="stylesheet"
            href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.1/css/all.min.css"
        />

        <title>Love Home</title>

        <style>
            body {
                margin: 0;
                font-family: "Kanit", sans-serif;
                background: pink;
                text-align: center;
                overflow: hidden;
            }

            .heart {
                position: fixed;
                bottom: -20px;
                font-size: 24px;
                animation: floatUp linear;
            }

            @keyframes floatUp {
                0% {
                    transform: translateY(0);
                    opacity: 1;
                }
                100% {
                    transform: translateY(-100vh);
                    opacity: 0;
                }
            }

            /* Overlay intro */
            #overlay {
                position: fixed;
                top: 0;
                left: 0;
                width: 100%;
                height: 100%;
                background: white;
                display: flex;
                justify-content: center;
                align-items: center;
                z-index: 100;
                transition: opacity 1.5s ease-in-out;
            }

            #intro {
                font-size: 28px;
                color: #ff4d94;
                text-align: center;
                opacity: 0;
                transition: opacity 1.5s ease-in-out;
                max-width: 80%;
            }

            /* ปุ่มเล่นเพลง */
            #music-btn {
                position: fixed;
                bottom: 30px;
                left: 50%;
                transform: translateX(-50%);
                background: #ff4d94;
                color: white;
                font-size: 20px;
                padding: 12px 24px;
                border: none;
                border-radius: 30px;
                cursor: pointer;
                opacity: 0;
                transition: opacity 1s ease-in-out, transform 0.3s;
                z-index: 50;
            }

            #music-btn:hover {
                transform: translateX(-50%) scale(1.1);
                background: #ff66aa;
            }
        </style>

        <script>
            // 🔒 ป้องกันเปิด DevTools (นอกจาก localhost)
            if (window.location.hostname !== "localhost") {
                document.addEventListener("keydown", function (e) {
                    if (e.key === "F12") e.preventDefault();
                    if ((e.ctrlKey || e.metaKey) && e.shiftKey && ["I", "J"].includes(e.key))
                        e.preventDefault();
                    if ((e.ctrlKey || e.metaKey) && e.key === "U") e.preventDefault();
                    if ((e.ctrlKey || e.metaKey) && e.shiftKey && e.key === "C")
                        e.preventDefault();
                });
                document.addEventListener("contextmenu", (e) => e.preventDefault());
            }
        </script>
    </head>

    <body>
        <noscript>คุณต้องเปิดการใช้งาน JavaScript เพื่อดูหน้านี้นะครับ</noscript>
        <div id="root"></div>

        <!-- 💖 ส่วนข้อความอวยพร + หัวใจ + ปุ่มเพลง -->
        <div id="overlay">
            <div id="intro"></div>
        </div>

        <button id="music-btn">🎵 กดเปิดเพลงด้วยน้าา</button>
        <audio id="bg-music" src="%PUBLIC_URL%/music.mp3"></audio>

        <script>
            const messages = [
                "หวัดดีคับพี่ฝ้าย 💖",
                "Happy Birthday naaaaakubb",
                "มีความสุขเยอะๆนะคับ 🌸",
                "และก็ยิ้มเยอะๆๆนะคับ 😊 🌸"
            ];

            const overlay = document.getElementById("overlay");
            const intro = document.getElementById("intro");
            const musicBtn = document.getElementById("music-btn");
            const bgMusic = document.getElementById("bg-music");
            let index = 0;

            function showMessage() {
                if (index < messages.length) {
                    intro.textContent = messages[index];
                    intro.style.opacity = 1;

                    setTimeout(() => {
                        intro.style.opacity = 0;
                        index++;
                        setTimeout(showMessage, 1500);
                    }, 3000);
                } else {
                    overlay.style.opacity = 0;
                    setTimeout(() => {
                        overlay.style.display = "none";
                        startHearts();
                        showMusicButton();
                    }, 1500);
                }
            }

            // หัวใจลอย
            function showHearts() {
                const heart = document.createElement("div");
                heart.className = "heart";
                heart.innerText = "💓";
                document.body.appendChild(heart);

                heart.style.left = Math.random() * 100 + "vw";
                heart.style.animationDuration = 3 + Math.random() * 2 + "s";
                setTimeout(() => heart.remove(), 5000);
            }

            function startHearts() {
                setInterval(showHearts, 800);
            }

            // ปุ่มเพลง
            function showMusicButton() {
                musicBtn.style.opacity = 1;
            }

            musicBtn.addEventListener("click", () => {
                bgMusic.play();
                musicBtn.textContent = "🎵 กดเปิดเพลงด้วยน้าา";
                musicBtn.style.background = "#ff80c0";
            });

            window.onload = function () {
                showMessage();
            };
        </script>
    </body>
</html>





















# Surprise Birthday Premium 🎉

This project is a **Premium Version** of the Surprise Birthday website designed to provide a full-featured experience for celebrating special occasions. The premium version comes with additional features, enhanced animations, and a custom music player.

Demo:
[Demo premium version](https://surprise-birthday-premium.onrender.com)

## Features

-   🎁 **Interactive Gift Opening Animation**
-   📸 **Photo Albums with Modal Previews**
-   🎶 **Integrated Music Player**
-   🔐 **OTP-based Secret Unlock for Birthday Surprises**
-   🎉 **Youtube**
-   📸 **Photo Carousel**

## Not including Features in Basic Version

The following features are included in the full version only:

-   📸 **Photo Carousel**: The full version includes a feature to view gift albums in a photo carousel format.
-   🎶 **Music Player**: The full version includes an embedded music player for a more immersive experience.
-   🎁 **Interactive Gift Opening**: The full version includes a Lottie animation and gift opening experience.
-   🖼 **Floating Assets and Animation**: The full version includes floating an assets and some animation for a more immersive experience.
-   🎉 **Youtube**: The full version includes an embedded youtube for a more immersive experience.

## Installation

To install and run the project locally, follow these steps:

1. Clone this repository:

    ```bash
    git clone https://github.com/your-repository/surprise-birthday-premium.git

    ```

2. Navigate to the project directory:

    ```bash
    cd surprise-birthday-premium

    ```

3. Install the dependencies:

    ```bash
    pnpm install

    ```

4. Start the development server:
    ```bash
    pnpm dev
    ```

Your website will now be running at http://localhost:3000.

## Project Structure

```bash
 src/
 │
 ├── assets/               # Static assets like images and mock data
 │   └── images/           # Image files
 │   └── mock/             # Mock data for the project
 ├── components/           # Reusable React components
 │   └── common/           # General components used across the app
 │   └── features/         # Feature components
 │   └── ui/               # UI components for more complex functionality
 ├── hooks/                # Custom hooks for handling logic (e.g., useModal)
 ├── utils/                # Utility functions and helper components
 └── App.js                # Main entry point of the app

```

## License

This project is licensed under the MIT License.

## Full Version Features

For users interested in unlocking the full experience with additional features, please contact us for details on how to upgrade.

-   🎁 Interactive Gift Opening Animation
-   📸 Photo Albums with Modal Previews
-   🎶 Integrated Music Player
-   📸 Photo Carousel
-   🖼 Floating Assets and Animation
-   🎉 Youtube

## ประกาศลิขสิทธิ์และเงื่อนไขการใช้งาน

โปรเจกต์นี้เผยแพร่เพื่อให้ใช้งานได้ฟรีเฉพาะในกรณีส่วนตัวเท่านั้นและอยู่ภายใต้ลิขสิทธิ์ส่วนบุคคล

โดยหากผู้ใดนำโปรเจกต์ไปใช้เพื่อการหารายได้หรือวัตถุประสงค์เชิงพาณิชย์ จะต้องชำระค่าลิขสิทธิ์ตามที่กำหนด ดังนี้:

-   โปรเจกต์ Basic เพื่อการหารายได้หรือวัตถุประสงค์เชิงพาณิชย์ จะมีค่าลิขสิทธิ์จำนวน 300 บาท
-   โปรเจกต์แบบเต็ม (Premium Version) ซึ่งมีฟีเจอร์เพิ่มเติม จะมีค่าลิขสิทธิ์จำนวน 1,000 บาท

การกระทำใด ๆ ที่เป็นการละเมิดลิขสิทธิ์โดยไม่ปฏิบัติตามเงื่อนไขที่ระบุไว้ อาจมีผลทางกฎหมายภายใต้พระราชบัญญัติลิขสิทธิ์ พ.ศ. 2537 และการดำเนินคดีทางกฎหมายที่เกี่ยวข้องกับการละเมิดลิขสิทธิ์

ท่านสามารถติดต่อเพื่อสอบถามหรือชำระค่าลิขสิทธิ์ได้ผ่านช่องทางต่อไปนี้:

-   Line: @959zlvla
-   TikTok: [@term.suqi](https://www.tiktok.com/@term.suqi)
-   Instagram: [suqi_dev](https://www.instagram.com/suqi_dev)

สงวนลิขสิทธิ์ตามกฎหมาย และ ทรัพย์สินทางปัญญา

## Licensing & Pricing

This project is free for personal use.
If you plan to use the Basic version to generate income, the fee is 300 Baht.
To access the Premium version with full features, the price is 1000 Baht.
For purchasing the project or upgrading, contact via:

-   Line: @959zlvla
-   TikTok: [@term.suqi](https://www.tiktok.com/@term.suqi)
-   Instagram: [suqi_dev](https://www.instagram.com/suqi_dev)

## Contact

-   Line: @959zlvla
-   TikTok: [@term.suqi](https://www.tiktok.com/@term.suqi)
-   Instagram: [suqi_dev](https://www.instagram.com/suqi_dev)
-   Linktree: [termsuqi](https://linktr.ee/termsuqi)
