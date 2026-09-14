<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Студия массажа Молодечно | Забота о теле</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f5f0eb;
            color: #3d3d3d;
            line-height: 1.6;
        }

        /* Шапка */
        header {
            position: relative;
            background: linear-gradient(135deg, #d4c5b5 0%, #c9b8a8 100%);
            padding: 60px 20px;
            text-align: center;
        }

        .header-logo {
            position: absolute;
            top: 12px;
            left: 12px;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            object-fit: cover;
            background: #fff;
            padding: 3px;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.12);
            transition: transform 0.3s ease;
        }

        .header-logo:hover {
            transform: scale(1.1);
        }

        header h1 {
            font-size: 2.5rem;
            color: #4a3728;
            margin-bottom: 10px;
            letter-spacing: 2px;
        }

        header p {
            font-size: 1.1rem;
            color: #6b5b4f;
            font-style: italic;
        }

        /* Контейнер */
        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        section {
            background: #fff;
            border-radius: 16px;
            padding: 35px;
            margin-bottom: 30px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.06);
        }

        section h2 {
            font-size: 1.6rem;
            color: #4a3728;
            margin-bottom: 20px;
            border-bottom: 2px solid #e8ddd3;
            padding-bottom: 10px;
        }

        .about-text {
            font-size: 1.05rem;
            color: #5a5a5a;
        }

        /* Услуги */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .service-card {
            background: #faf6f2;
            border-radius: 12px;
            padding: 25px;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .service-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
        }

        .service-card h3 {
            font-size: 1.2rem;
            color: #4a3728;
            margin-bottom: 10px;
        }

        .service-card p {
            font-size: 0.95rem;
            color: #6b5b4f;
        }

        /* Прайс-лист */
        .price-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .price-img {
            width: 100%;
            height: auto;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
            cursor: pointer;
            display: block;
        }

        .price-img:hover {
            transform: scale(1.03);
        }

        /* Модальное окно */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            z-index: 9999;
            justify-content: center;
            align-items: center;
            padding: 20px;
            cursor: pointer;
            overflow: auto;
        }

        .modal.active {
            display: flex;
        }

        .modal-img {
            max-width: 100%;
            max-height: 95%;
            border-radius: 8px;
            box-shadow: 0 8px 40px rgba(0, 0, 0, 0.5);
            animation: zoomIn 0.3s ease;
            object-fit: contain;
        }

        .modal-close {
            position: fixed;
            top: 10px;
            right: 15px;
            font-size: 36px;
            color: #fff;
            cursor: pointer;
            font-weight: bold;
            z-index: 10000;
            line-height: 1;
            background: rgba(0, 0, 0, 0.5);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: transform 0.3s;
        }

        .modal-close:hover {
            transform: scale(1.1);
        }

        @keyframes zoomIn {
            from { transform: scale(0.8); opacity: 0; }
            to { transform: scale(1); opacity: 1; }
        }

        /* Контакты */
        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 1.05rem;
        }

        .contact-item .icon {
            font-size: 1.4rem;
        }

        .contact-item a {
            color: #4a3728;
            text-decoration: none;
            transition: color 0.3s;
        }

        .contact-item a:hover {
            color: #8b7355;
        }

        /* Кнопка */
        .btn {
            display: inline-block;
            background: linear-gradient(135deg, #8b7355 0%, #6b5b4f 100%);
            color: #fff;
            padding: 14px 35px;
            border-radius: 50px;
            text-decoration: none;
            font-size: 1.05rem;
            margin-top: 20px;
            transition: opacity 0.3s, transform 0.3s;
            border: none;
            cursor: pointer;
        }

        .btn:hover {
            opacity: 0.9;
            transform: scale(1.03);
        }

        /* Футер */
        footer {
            text-align: center;
            padding: 30px 20px;
            color: #9a8a7a;
            font-size: 0.9rem;
        }

        /* Телефон */
        @media (max-width: 600px) {
            header h1 {
                font-size: 1.8rem;
            }

            section {
                padding: 25px 20px;
            }

            .services-grid {
                grid-template-columns: 1fr;
            }

            .price-grid {
                grid-template-columns: 1fr;
            }

            .modal {
                padding: 5px;
                align-items: flex-start;
                padding-top: 50px;
            }

            .modal-img {
                max-height: none;
                width: 100%;
                height: auto;
            }

            .modal-close {
                top: 8px;
                right: 8px;
                font-size: 30px;
                width: 36px;
                height: 36px;
            }
        }
    </style>
</head>
<body>

    <!-- Шапка -->
    <header>
        <img src="images/logo.png" alt="Логотип" class="header-logo">
        <h1>Студия массажа</h1>
        <p>Молодечно · Забота о вашем теле</p>
    </header>

    <div class="container">

        <!-- О нас -->
        <section>
            <h2>О нас</h2>
            <p class="about-text">
                Мы — студия массажа в Молодечно, где каждый гость чувствует заботу с первого касания. 
                Наши мастера помогут снять напряжение, восстановить силы и вернуть лёгкость телу. 
                Работаем с классическими и авторскими техниками, подбираем программу индивидуально.
            </p>
            <a href="https://instagram.com/studia_massage_molo" class="btn" target="_blank">Записаться в Instagram</a>
        </section>

        <!-- Услуги -->
        <section>
            <h2>Наши услуги</h2>
            <div class="services-grid">
                <div class="service-card">
                    <h3>Классический массаж</h3>
                    <p>Понятная классика. Проработка всего тела. Свежесть и лёгкость после сеанса.</p>
                </div>
                <div class="service-card">
                    <h3>Креольский массаж</h3>
                    <p>Энергия, ритм и глубокая проработка. Начинается со стоп — запускает всё тело.</p>
                </div>
                <div class="service-card">
                    <h3>Массаж глубоких тканей</h3>
                    <p>Максимальная проработка. Для тех, кто хочет серьёзный результат.</p>
                </div>
                <div class="service-card">
                    <h3>Стоун-массаж</h3>
                    <p>Тепло горячих камней. Глубокое расслабление и гармония.</p>
                </div>
                <div class="service-card">
                    <h3>Массаж лица</h3>
                    <p>Сияние и лифтинг без инъекций. Деликатная проработка.</p>
                </div>
                <div class="service-card">
                    <h3>Баночный массаж</h3>
                    <p>Вакуум и глубина. Улучшает кровоток и убирает застои.</p>
                </div>
            </div>
        </section>

        <!-- Прайс-лист -->
        <section>
            <h2>Прайс-лист</h2>
            <p class="about-text" style="margin-bottom: 20px;">
                Актуальные цены на все услуги студии. Нажмите на фото, чтобы увеличить.
            </p>
            <div class="price-grid">
                <img src="images/price1.jpg" alt="Прайс-лист" class="price-img" onclick="openModal(this.src)">
            </div>
        </section>

        <!-- Контакты -->
        <section>
            <h2>Контакты</h2>
            <div class="contact-info">
                <div class="contact-item">
                    <span class="icon">📍</span>
                    <span>г. Молодечно, ул. Великий Гостинец, д. 87</span>
                </div>
                <div class="contact-item">
                    <span class="icon">📞</span>
                    <a href="tel:+375293059630">+375 (29) 305-96-30</a>
                </div>
                <div class="contact-item">
                    <span class="icon">📸</span>
                    <a href="https://instagram.com/studia_massage_molo" target="_blank">@studia_massage_molo</a>
                </div>
                <div class="contact-item">
                    <span class="icon">🕐</span>
                    <span>Исключительно по записи!</span>
                </div>
            </div>
        </section>

    </div>

    <!-- Футер -->
    <footer>
        <p>© 2026 Студия массажа Молодечно. Все права защищены.</p>
    </footer>

    <!-- Модальное окно -->
    <div id="priceModal" class="modal" onclick="closeModal()">
        <span class="modal-close">&times;</span>
        <img src="" alt="Прайс-лист" class="modal-img" id="modalImg">
    </div>

    <!-- JavaScript -->
    <script>
        function openModal(src) {
            document.getElementById('modalImg').src = src;
            document.getElementById('priceModal').classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closeModal() {
            document.getElementById('priceModal').classList.remove('active');
            document.body.style.overflow = 'auto';
        }

        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape') closeModal();
        });
    </script>

</body>
</html>
