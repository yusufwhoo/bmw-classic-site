# bmw-classic-site
BMW cars information website
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BMW Mukammal Sayt</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&display=swap');
        
        body {
            font-family: 'Playfair Display', serif;
            text-align: center;
            background: black;
            color: white;
            margin: 0;
            padding: 0;
            overflow-x: hidden;
        }
        header {
            font-size: 50px;
            font-weight: bold;
            text-shadow: 4px 4px 8px rgba(255, 215, 0, 0.5);
            padding: 30px;
            background: rgba(0, 0, 0, 0.8);
            border-bottom: 2px solid gold;
        }
        .container {
            margin-top: 50px;
            padding: 20px;
            animation: fadeIn 2s ease-in-out;
        }
        .btn {
            padding: 15px 30px;
            font-size: 22px;
            font-weight: bold;
            background: gold;
            color: black;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            box-shadow: 0px 5px 15px rgba(255, 215, 0, 0.5);
            transition: transform 0.2s;
        }
        .btn:hover {
            transform: scale(1.1);
        }
        .animated-section {
            opacity: 0;
            transform: translateY(50px);
            transition: all 1s ease-in-out;
            padding: 50px;
            font-size: 24px;
        }
        .visible {
            opacity: 1;
            transform: translateY(0);
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        .bmw-image {
            width: 80%;
            max-width: 1000px;
            border-radius: 20px;
            box-shadow: 0px 10px 30px rgba(255, 215, 0, 0.5);
            transition: transform 0.5s;
        }
        .bmw-image:hover {
            transform: scale(1.05);
        }
        .slideshow-container {
            position: relative;
            max-width: 1000px;
            margin: auto;
            overflow: hidden;
        }
        .slides {
            display: none;
        }
        .prev, .next {
            cursor: pointer;
            position: absolute;
            top: 50%;
            width: auto;
            padding: 16px;
            color: white;
            font-size: 24px;
            transition: 0.6s ease;
            user-select: none;
        }
        .next { right: 0; }
        .prev:hover, .next:hover { color: gold; }
        .bmw-info {
            margin-top: 50px;
            padding: 20px;
            background: rgba(255, 215, 0, 0.1);
            border-radius: 10px;
        }
    </style>
</head>
<body>
    <header>BMW - Klassika va Innovatsiya 🚀</header>
    <div class="container">
        <p class="animated-section">BMW avtomobillari – mukammallik va zamonaviy texnologiyaning uyg‘unligi!</p>
        <button class="btn" onclick="showMessage()">BMW Haqida Batafsil</button>
    </div>
    
    <div class="slideshow-container">
        <img class="slides bmw-image" src="https://th.bing.com/th/id/OIP.RHoonZfmeYI9_GxugFmbQwHaEK?rs=1&pid=ImgDetMain.jpg" alt="BMW 3 Series">
        <img class="slides bmw-image" src="https://th.bing.com/th/id/R.72166d12543bfd11c6904e87ee3c15fc?rik=8duFJTLLft1hLA&pid=ImgRaw&r=0.jpg" alt="BMW M4">
        <img class="slides bmw-image" src="https://cdn.motor1.com/images/mgl/KgJmR/s1/4x3/bmw-x7.jpg" alt="BMW X7">
        <a class="prev" onclick="changeSlide(-1)">&#10094;</a>
        <a class="next" onclick="changeSlide(1)">&#10095;</a>
    </div>
    
    <div class="bmw-info">
        <h2>BMW Modellari</h2>
        <p><strong>BMW 3 Series:</strong> Ishonchli va qulay sedan.</p>
        <p><strong>BMW M4:</strong> Sportiv va yuqori tezlikka mos avtomobil.</p>
        <p><strong>BMW X7:</strong> Katta va hashamatli SUV.</p>
    </div>
    
    <script>
        function showMessage() {
            alert("BMW - mukammallik timsoli! 🎉");
        }
        function revealElements() {
            let elements = document.querySelectorAll('.animated-section');
            elements.forEach(el => {
                let position = el.getBoundingClientRect().top;
                let screenHeight = window.innerHeight;
                if (position < screenHeight - 100) {
                    el.classList.add('visible');
                }
            });
        }
        window.addEventListener('scroll', revealElements);
        let slideIndex = 0;
        function showSlides() {
            let slides = document.querySelectorAll(".slides");
            slides.forEach(slide => slide.style.display = "none");
            slideIndex++;
            if (slideIndex > slides.length) { slideIndex = 1 }
            slides[slideIndex - 1].style.display = "block";
            setTimeout(showSlides, 3000);
        }
        function changeSlide(n) {
            let slides = document.querySelectorAll(".slides");
            slideIndex += n;
            if (slideIndex > slides.length) { slideIndex = 1; }
            if (slideIndex < 1) { slideIndex = slides.length; }
            slides.forEach(slide => slide.style.display = "none");
            slides[slideIndex - 1].style.display = "block";
        }
        showSlides();
    </script>
</body>
</html>
