<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Eğlenceli Patlama Oyunu</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: 'Roboto', sans-serif;
            background-color: #1d1f20; /* Eski arka plan rengi */
            transition: background-color 0.3s ease;
        }
        canvas {
            display: block;
            border: 10px solid rgba(255, 255, 255, 0.3);
            box-shadow: 0 0 30px rgba(255, 255, 255, 0.5);
        }
        .puan-panesi {
            position: absolute;
            top: 10px;
            left: 10px;
            font-size: 24px;
            color: #ff69b4;
            background: rgba(0, 0, 0, 0.6);
            border: 2px solid #ff69b4;
            padding: 10px 20px;
            border-radius: 8px;
            display: flex;
            align-items: center;
            z-index: 1;
        }
        .fps-panesi {
            position: absolute;
            top: 10px;
            right: 10px;
            font-size: 24px;
            color: #00ff00;
            background: rgba(0, 0, 0, 0.6);
            border: 2px solid #00ff00;
            padding: 10px 20px;
            border-radius: 8px;
            display: flex;
            align-items: center;
            z-index: 1;
        }
        .mesaj {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 36px;
            color: white;
            font-weight: bold;
            z-index: 2;
            display: none;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.9);
        }
    </style>
</head>
<body>
    <canvas id="explosionCanvas"></canvas>
    <div class="puan-panesi" style="display: flex;">
        Puan: <span class="score">0</span>
    </div>
    <div class="fps-panesi">
        <span class="fps">0</span>
    </div>
    <div class="mesaj" id="message"></div>

    <script>
        const canvas = document.getElementById('explosionCanvas');
        const ctx = canvas.getContext('2d');
        const scoreElement = document.querySelector('.score');
        const fpsElement = document.querySelector('.fps');
        const messageElement = document.getElementById('message');
        let particles = [];
        let score = 0;
        let explosionCount = 0;
        let difficulty = 'easy'; // Başlangıç zorluk seviyesi
        let lastFrameTime = performance.now();
        let frameCount = 0;
        let fps = 0;

        // Renk paleti
        const colors = ['#ffb3b3', '#f39cbb', '#d187d1']; // Pembe tonları

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        window.addEventListener('resize', resizeCanvas);

        // Oyun başlangıcı
        canvas.style.display = 'block';
        document.querySelector('.puan-panesi').style.display = 'flex';
        resizeCanvas();
        mesajGoster('Oyun Başladı!');
        setTimeout(() => messageElement.style.display = 'none', 2000);
        update();

        // Patlama tıklaması
        canvas.addEventListener('click', (event) => {
            createExplosion(event.clientX, event.clientY);
            incrementScore(1);
        });

        function createExplosion(x, y) {
            increaseDifficulty();
            const numParticles = 100 + explosionCount * (difficulty === "hard" ? 20 : 10); // Patlamadaki parçacık sayısını ayarlama
            const explosionPower = 10 + explosionCount + (difficulty === "hard" ? 5 : 0); // Patlamanın gücü

            // Parçacıkların yaratılması
            for (let i = 0; i < numParticles; i++) {
                const angle = Math.random() * 2 * Math.PI; // Her parçacık için rastgele yön
                const speed = Math.random() * explosionPower; // Rastgele hız
                const shape = ['ring', 'square', 'triangle', 'x', 'star'][Math.floor(Math.random() * 5)]; // Parçacık şekli
                particles.push({
                    x: x,
                    y: y,
                    speedX: Math.cos(angle) * speed, // X eksenindeki hız
                    speedY: Math.sin(angle) * speed, // Y eksenindeki hız
                    size: Math.random() * 5 + 10, // Parçacık boyutu
                    alpha: 1, // Opaklık (şeffaflık)
                    color: `hsl(${Math.random() * 60 + 30}, 100%, 50%)`, // Parçacık rengi
                    shape: shape, // Parçacık şekli
                    lifetime: Math.random() * 5 + 1 // Parçacığın ömrü (ne kadar süreyle görünür olacak)
                });
            }
            explosionCount++;
        }

        function increaseDifficulty() {
            if (explosionCount > 30 && difficulty === 'easy') {
                difficulty = 'medium';
                mesajGoster('Zorluk Orta Seviyeye Geçti!');
            } else if (explosionCount > 60 && difficulty === 'medium') {
                difficulty = 'hard';
                mesajGoster('Zorluk Zor Seviyeye Geçti!');
            }
        }

        function update() {
            const currentTime = performance.now();
            const deltaTime = currentTime - lastFrameTime;
            lastFrameTime = currentTime;
            frameCount++;

            if (frameCount >= 60) { // FPS ölçümü her saniyede bir yapılır
                fps = Math.round(1000 / deltaTime);
                frameCount = 0;
            }

            fpsElement.textContent = fps;

            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles = particles.filter(p => p.alpha > 0.05);

            // Eski arka plan renkleri
            const gradient = ctx.createRadialGradient(canvas.width / 2, canvas.height / 2, canvas.width / 4, canvas.width / 2, canvas.height / 2, canvas.width);
            gradient.addColorStop(0, "rgba(0, 0, 0, 0.2)");
            gradient.addColorStop(1, "rgba(0, 0, 0, 0.8)");
            ctx.fillStyle = gradient;
            ctx.fillRect(0, 0, canvas.width, canvas.height);

            for (const particle of particles) {
                particle.x += particle.speedX;
                particle.y += particle.speedY;
                particle.speedX *= 0.99;
                particle.speedY *= 0.99;
                particle.alpha *= 0.98;

                ctx.globalAlpha = particle.alpha;
                ctx.strokeStyle = particle.color;
                ctx.lineWidth = 2;

                switch (particle.shape) {
                    case 'ring':
                        ctx.beginPath();
                        ctx.arc(particle.x, particle.y, particle.size / 2, 0, 2 * Math.PI);
                        ctx.stroke();
                        break;
                    case 'square':
                        ctx.beginPath();
                        ctx.rect(particle.x - particle.size / 2, particle.y - particle.size / 2, particle.size, particle.size);
                        ctx.stroke();
                        break;
                    case 'triangle':
                        ctx.beginPath();
                        ctx.moveTo(particle.x, particle.y - particle.size / 2);
                        ctx.lineTo(particle.x - particle.size / 2, particle.y + particle.size / 2);
                        ctx.lineTo(particle.x + particle.size / 2, particle.y + particle.size / 2);
                        ctx.closePath();
                        ctx.stroke();
                        break;
                    case 'x':
                        ctx.beginPath();
                        ctx.moveTo(particle.x - particle.size / 2, particle.y - particle.size / 2);
                        ctx.lineTo(particle.x + particle.size / 2, particle.y + particle.size / 2);
                        ctx.moveTo(particle.x + particle.size / 2, particle.y - particle.size / 2);
                        ctx.lineTo(particle.x - particle.size / 2, particle.y + particle.size / 2);
                        ctx.stroke();
                        break;
                    case 'star':
                        ctx.beginPath();
                        for (let i = 0; i < 5; i++) {
                            const angle = i * 2 * Math.PI / 5;
                            ctx.lineTo(particle.x + Math.cos(angle) * particle.size / 2, particle.y + Math.sin(angle) * particle.size / 2);
                        }
                        ctx.closePath();
                        ctx.stroke();
                        break;
                }
            }

            requestAnimationFrame(update);
        }

        function incrementScore(points) {
            score += points;
            scoreElement.textContent = score;
        }

        function mesajGoster(mesaj) {
            messageElement.textContent = mesaj;
            messageElement.style.display = 'block';
            setTimeout(() => messageElement.style.display = 'none', 2000);
        }
    </script>
</body>
</html>
