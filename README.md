<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Happy 7th Month Anniversary ❤️</title>
    <link href="https://fonts.googleapis.com/css2?family=Itim&family=Mali:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        :root { --primary-pink: #ff9a9e; --text-color: #5d54a4; }
        
        body, html { 
            margin: 0; padding: 0; width: 100%; height: 100%; 
            font-family: 'Itim', cursive; 
            background: linear-gradient(-45deg, #fad0c4, #ffd1ff, #a1c4fd, #c2e9fb);
            background-size: 400% 400%; animation: gradientBG 15s ease infinite; 
            overflow: hidden; display: flex; justify-content: center; align-items: center; 
        }

        @keyframes gradientBG { 0% { background-position: 0% 50%; } 50% { background-position: 100% 50%; } 100% { background-position: 0% 50%; } }
        
        /* Lock Screen for Mobile */
        #lock-screen { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(255, 255, 255, 0.2); backdrop-filter: blur(20px); display: flex; justify-content: center; align-items: center; z-index: 100; transition: 1s; }
        .lock-box { background: rgba(255, 255, 255, 0.95); padding: 30px; border-radius: 30px; box-shadow: 0 15px 40px rgba(0,0,0,0.1); text-align: center; width: 85%; max-width: 320px; border: 2px solid white; }
        
        input { width: 100%; padding: 15px; border: 2px solid #eee; border-radius: 20px; font-size: 18px; text-align: center; margin-bottom: 20px; outline: none; box-sizing: border-box; -webkit-appearance: none; }
        .btn-confirm { background: var(--primary-pink); color: white; border: none; padding: 15px; border-radius: 50px; font-size: 20px; width: 100%; cursor: pointer; -webkit-tap-highlight-color: transparent; }

        /* Main Content for Mobile */
        #main-content { 
            display: none; text-align: center; width: 90%; max-width: 450px; 
            background: rgba(255, 255, 255, 0.92); padding: 25px; 
            border-radius: 35px; box-shadow: 0 20px 50px rgba(0,0,0,0.1); 
            z-index: 10; max-height: 85vh; overflow-y: auto; position: relative;
        }

        .photo-frame { width: 180px; height: 180px; margin: 0 auto 15px; border-radius: 50%; border: 5px solid white; box-shadow: 0 10px 25px rgba(0,0,0,0.1); overflow: hidden; position: relative; }
        .photo-frame img { width: 100%; height: 100%; object-fit: cover; position: absolute; top: 0; left: 0; opacity: 0; transition: 1s; }
        .photo-frame img.active { opacity: 1; position: relative; }
        
        #timer-box { background: #fffafa; padding: 12px; border-radius: 20px; margin: 15px 0; border: 1px solid #ffe4e6; }
        #timer { font-weight: bold; font-size: 1.1rem; color: var(--text-color); }

        .message-area { font-size: 17px; line-height: 1.6; color: var(--text-color); text-align: left; min-height: 80px; white-space: pre-wrap; font-family: 'Mali'; }

        /* Video Button & Modal Mobile */
        #video-btn { display: none; margin-top: 15px; background: linear-gradient(45deg, #ff9a9e, #ff758c); color: white; border: none; padding: 15px 30px; border-radius: 50px; font-family: 'Mali'; font-weight: bold; font-size: 18px; box-shadow: 0 5px 15px rgba(255, 117, 140, 0.4); width: 100%; }
        
        #video-modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0, 0, 0, 0.9); z-index: 200; justify-content: center; align-items: center; flex-direction: column; }
        #video-modal video { width: 95%; max-width: 400px; border-radius: 15px; }
        .close-video { color: white; font-size: 20px; cursor: pointer; margin-top: 25px; background: rgba(255,255,255,0.2); padding: 10px 20px; border-radius: 30px; }

        .heart-fall { position: fixed; top: -10vh; animation: fall linear forwards; pointer-events: none; z-index: 5; }
        @keyframes fall { to { transform: translateY(110vh) rotate(360deg); } }
    </style>
</head>
<body>

    <audio id="bgMusic" loop preload="auto"><source src="song.mp3" type="audio/mpeg"></audio>

    <div id="lock-screen">
        <div class="lock-box">
            <h1 style="font-size: 50px; margin: 0;">🔒</h1>
            <h2 style="font-family:'Mali'; font-size: 1.2rem;">เป็นแฟนกันวันไหนนะ??</h2>
            <input type="password" id="passwordInput" placeholder="DDMMYYYY" maxlength="8" inputmode="numeric">
            <button class="btn-confirm" onclick="checkPassword()">พร้อมแล้วจิ้มมม ✨</button>
        </div>
    </div>

    <div id="main-content">
        <div class="photo-frame">
            <img src="photo1.jpg" class="slide active">
            <img src="photo2.jpg" class="slide">
            <img src="photo3.jpg" class="slide">
            <img src="photo4.jpg" class="slide">
            <img src="photo5.jpg" class="slide">
            <img src="photo6.jpg" class="slide">
            <img src="photo7.jpg" class="slide">
        </div>
        <h2 style="color: var(--primary-pink); font-family: 'Mali'; font-size: 1.4rem; margin: 5px 0;">Happy 7 Months! 🎉</h2>
        <div id="timer-box">
            <div style="font-size: 0.8rem; color: #888;">เราเป็นแฟนกันมาแล้ว...</div>
            <div id="timer"></div>
        </div>
        <div class="message-area" id="typewriter"></div>
        <button id="video-btn" onclick="openVideo()">🎬</button>
    </div>

    <div id="video-modal">
        <video id="ourVideo" playsinline controls>
            <source src="our-video.mp4" type="video/mp4">
        </video>
        <div class="close-video" onclick="closeVideo()">× กลับหน้าหลัก (รักนะครับ)</div>
    </div>

    <script>
        const correctPass = "01072025";
        const startDate = new Date(2025, 6, 1, 0, 0, 0); 
        const input = document.getElementById('passwordInput');
        const typewriterElement = document.getElementById('typewriter');
        const videoBtn = document.getElementById('video-btn');
        const music = document.getElementById('bgMusic');
        
        const messageText = "เย้้้้!! ใส่รหัสถูกด้วยยย คุณเก่งที่สุดในโลกเลยยย \n\nสิ่งแรกที่อยากจะบอกเลย ขอบคุณที่อยู่กับนิวมาจนถึงวันนี้นะครับบ \n\n7 เดือนแล้วนะครับคุณณ เวลาผ่านไปเร็วมากก แล้วก็เวลาที่ผ่านมามันมีความหมายกับนิวมากก ขอบคุณที่เป็นความสุขให้นิวในทุกๆวันนะะ ขอบคุณที่อยู่กับนิวนะะ นิวมีคุณแล้วนิวมีความสุขมากๆๆๆๆ อยู่ให้นิวรักไปนานๆนะครับ ตั้งแต่วันแรกจนถึงวันนี้คุณน่ารักไม่เปลี่ยนเลยย น่ารักมากขึ้นๆทุกวันด้วยย คนอะไร ไอ้ขี้โกงเอ้ยย รักนะครับ รักมากขึ้นๆทุกวันเลยย อยู่กับนิวไปนานนะ!! 💖";

        function checkPassword() {
            if (input.value === correctPass) {
                unlock();
            } else {
                alert("ไม่ถูกน้าา! ลองใหม่นะคนดีห์ 🥺");
                input.value = ""; 
            }
        }

        function unlock() {
            // ปลดล็อกเพลงสำหรับ iOS/Android
            music.volume = 0.3;
            music.play().then(() => {
                console.log("Music playing");
            }).catch(e => {
                console.log("Auto-play blocked, waiting for touch");
            });

            document.getElementById('lock-screen').style.opacity = '0';
            setTimeout(() => {
                document.getElementById('lock-screen').style.display = 'none';
                document.getElementById('main-content').style.display = 'block';
                startTypewriter();
                startSlideshow();
                updateTimer();
                setInterval(updateTimer, 1000);
                setInterval(createHeart, 600);
            }, 1000);
        }

        function updateTimer() {
            const now = new Date();
            const diff = now - startDate;
            const days = Math.floor(diff / (1000 * 60 * 60 * 24));
            const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
            const mins = Math.floor((diff / (1000 * 60)) % 60);
            const secs = Math.floor((diff / 1000) % 60);
            document.getElementById('timer').innerHTML = `${days} วัน ${hours} ชม. ${mins} นาที ${secs} วิ.`;
        }

        function startTypewriter() {
            let i = 0; typewriterElement.innerHTML = "";
            function type() {
                if (i < messageText.length) {
                    typewriterElement.innerHTML += messageText.charAt(i) === "\n" ? "<br>" : messageText.charAt(i);
                    i++; 
                    // ปรับความเร็วให้มือถืออ่านง่ายขึ้น
                    setTimeout(type, 50); 
                } else { 
                    videoBtn.style.display = "block";
                    // เลื่อนหน้าจอลงมาให้เห็นปุ่มวิดีโออัตโนมัติ
                    document.getElementById('main-content').scrollTo({top: 500, behavior: 'smooth'});
                }
            }
            type();
        }

        function openVideo() { 
            document.getElementById('video-modal').style.display = 'flex'; 
            document.getElementById('ourVideo').play(); 
            music.volume = 0.1; 
        }
        
        function closeVideo() { 
            document.getElementById('video-modal').style.display = 'none'; 
            document.getElementById('ourVideo').pause(); 
            music.volume = 0.3; 
        }

        function startSlideshow() {
            let current = 0; const slides = document.querySelectorAll('.slide');
            setInterval(() => { slides[current].classList.remove('active'); current = (current + 1) % slides.length; slides[current].classList.add('active'); }, 3000);
        }

        function createHeart() {
            const heart = document.createElement('div'); heart.classList.add('heart-fall');
            heart.innerHTML = ['❤️','💖','✨'][Math.floor(Math.random()*3)];
            heart.style.left = Math.random() * 90 + 'vw'; 
            heart.style.fontSize = Math.random() * 15 + 10 + 'px';
            heart.style.animationDuration = Math.random() * 3 + 3 + 's';
            document.body.appendChild(heart); setTimeout(() => heart.remove(), 6000);
        }

        input.addEventListener("keypress", (e) => { if (e.key === "Enter") checkPassword(); });
    </script>
</body>
</html>
