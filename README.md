<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Invitation to Chef Damian's Graduation</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        .hat-container {
            position: absolute;
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
        }
    </style>
</head>
<body class="bg-slate-900 min-h-screen flex items-center justify-center p-4">

    <div class="relative w-full max-w-md">
        
        <!-- Graduation Hat Icon -->
        <div class="hat-container text-5xl z-20">🎓</div>

        <div class="bg-white w-full rounded-3xl shadow-2xl overflow-hidden mt-6">
            <!-- Header -->
            <div class="bg-amber-400 p-8 flex justify-center items-center flex-col">
                <div class="bg-white p-6 rounded-full shadow-lg mt-2">
                    <i class="fas fa-bell text-4xl text-amber-500"></i>
                </div>
                <h2 class="text-slate-700 font-semibold tracking-widest mt-6 uppercase text-sm">You Are Invited To</h2>
            </div>

            <!-- Main Content -->
            <div class="p-6">
                <h1 class="text-3xl font-bold text-slate-800 text-center mb-2">Chef Damian's</h1>
                <p class="text-2xl font-bold text-amber-600 text-center mb-6">Graduation</p>

                <!-- Added Photo -->
                <div class="rounded-2xl overflow-hidden mb-8 shadow-lg border-4 border-amber-100">
                    <img src="23222_2.jpg" alt="Chef Damian" class="w-full h-auto object-cover">
                </div>

                <!-- Details -->
                <div class="bg-slate-50 p-5 rounded-2xl space-y-4 mb-8">
                    <div class="flex items-center gap-3">
                        <i class="fas fa-calendar-alt text-amber-500 w-6"></i>
                        <span class="text-slate-700"><strong>Date:</strong> Friday, July 10, 2026</span>
                    </div>
                    <div class="flex items-center gap-3">
                        <i class="fas fa-clock text-amber-500 w-6"></i>
                        <span class="text-slate-700"><strong>Time:</strong> 08:00 AM EAT</span>
                    </div>
                    <div class="flex items-center gap-3">
                        <i class="fas fa-map-marker-alt text-amber-500 w-6"></i>
                        <span class="text-slate-700"><strong>Location:</strong> Taita Taveta National Polytechnic, Main Campus, Voi</span>
                    </div>
                    <div class="flex items-center gap-3">
                        <i class="fas fa-award text-amber-500 w-6"></i>
                        <span class="text-slate-700"><strong>Achievement:</strong> Food and beverage production (Culinary Arts)</span>
                    </div>
                </div>

                <!-- Video Section -->
                <div class="rounded-2xl overflow-hidden mb-8 shadow-lg">
                    <video controls class="w-full h-auto">
                        <source src="cooking-video.mp4" type="video/mp4">
                        Your browser does not support the video tag.
                    </video>
                </div>

                <!-- Message Card -->
                <div class="bg-amber-50 p-6 rounded-2xl border border-amber-100 text-center mb-8">
                    <h3 class="font-bold text-amber-900 mb-2"><i class="fas fa-graduation-cap mr-2"></i>To Our Favorite Chef! <i class="fas fa-party-horn ml-1"></i></h3>
                    <p class="text-sm text-slate-600 italic">"Your incredible dedication, flavor, and culinary artistry have brought you to this spectacular milestone! We are immensely proud of your hard work. May your kitchen always be warm, your plates flawlessly crafted, and your future filled with endless success! 👨‍🍳🔥🥂🌟"</p>
                </div>

                <!-- CTA -->
                <button onclick="sendWhatsApp()" class="w-full bg-green-500 hover:bg-green-600 text-white font-bold py-4 rounded-xl transition duration-300 shadow-lg transform hover:scale-[1.02]">
                    Send Congratulations
                </button>
            </div>
        </div>
    </div>

    <script>
        window.onload = function() {
            var duration = 3 * 1000;
            var animationEnd = Date.now() + duration;
            var defaults = { startVelocity: 30, spread: 360, ticks: 60, zIndex: 100 };
            function randomInRange(min, max) { return Math.random() * (max - min) + min; }
            var interval = setInterval(function() {
                var timeLeft = animationEnd - Date.now();
                if (timeLeft <= 0) return clearInterval(interval);
                var particleCount = 50 * (timeLeft / duration);
                confetti(Object.assign({}, defaults, { particleCount, origin: { x: randomInRange(0.1, 0.3), y: Math.random() - 0.2 } }));
                confetti(Object.assign({}, defaults, { particleCount, origin: { x: randomInRange(0.7, 0.9), y: Math.random() - 0.2 } }));
            }, 250);
        };

        function sendWhatsApp() {
            const phoneNumber = "254720975663";
            const message = "Congratulations on your graduation, Chef Damian! 👨‍🍳🎉 Bright futures ahead! 🥂"; 
            const whatsappUrl = `https://wa.me/${phoneNumber}?text=${encodeURIComponent(message)}`;
            window.open(whatsappUrl, '_blank');
        }
    </script>
</body>
</html>
