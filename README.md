<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Генератор кошмаров</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background-color: black;
            color: white;
            font-family: 'Arial', sans-serif;
        }
        .eye {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: red;
            position: absolute;
            transition: transform 0.1s;
        }
        .text {
            position: absolute;
            font-size: 30px;
            opacity: 0.7;
            pointer-events: none;
        }
        .fobies {
            position: absolute;
            left: 10px;
            top: 10px;
            font-size: 20px;
            max-width: 300px;
        }
    </style>
</head>
<body>
    <div class="eye"></div>
    <div class="text">Кошмар...</div>
    <div class="fobies">
        <p>1. Агорафобия - страх открытых пространств.</p>
        <p>2. Клаустрофобия - страх замкнутых пространств.</p>
        <p>3. Нозофобия - страх болезни.</p>
        <p>4. Арахнофобия - страх пауков.</p>
        <p>5. Топофобия - страх определенных мест.</p>
    </div>

    <script>
        const eye = document.querySelector('.eye');
        const text = document.querySelector('.text');

        document.addEventListener('mousemove', (e) => {
            eye.style.left = e.pageX + 'px';
            eye.style.top = e.pageY + 'px';

            // Анимация текста
            const randomX = (Math.random() - 0.5) * 20;
            const randomY = (Math.random() - 0.5) * 20;
            text.style.transform = `translate(${randomX}px, ${randomY}px)`;
        });

        // Изменение шрифта и цвета текста
        setInterval(() => {
            text.style.fontSize = Math.random() * 40 + 'px';
            text.style.color = '#' + Math.floor(Math.random()*16777215).toString(16);
        }, 500);
    </script>
</body>
</html>
