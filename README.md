<!DOCTYPE html><html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Neon Scroll</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-color: #000;
            color: #fff;
            font-family: Arial, sans-serif;
            overflow-x: hidden;
        }
        .container {
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 3rem;
            font-weight: bold;
            opacity: 0;
            transform: translateY(50px);
            transition: opacity 1s ease-out, transform 1s ease-out;
        }
        .visible {
            opacity: 1;
            transform: translateY(0);
        }
        .neon {
            text-shadow: 0 0 5px #0ff, 0 0 10px #0ff, 0 0 20px #0ff;
        }
    </style>
</head>
<body>
    <div class="container neon">Welcome to the Neon World</div>
    <div class="container neon">Scroll Down</div>
    <div class="container neon">More Neon Effects</div>
    <div class="container neon">Cool Animations</div>
    <div class="container neon">Enjoy!</div>
    <div class="container neon">バカ</div><script>
    const elements = document.querySelectorAll('.container');

    const observer = new IntersectionObserver(entries => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('visible');
            }
        });
    }, { threshold: 0.2 });

    elements.forEach(element => {
        observer.observe(element);
    });
</script>

</body>
</html>
