<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Вікна та Двері Переяслав - Продаж та встановлення</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Основные стили */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        
        :root {
            --primary-color: #1a3a5f;
            --secondary-color: #4da8da;
            --accent-color: #2ecc71;
            --text-color: #333;
            --light-bg: #f9f9f9;
        }
        
        body {
            line-height: 1.6;
            color: var(--text-color);
            overflow-x: hidden;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Шапка */
        header {
            background-color: var(--primary-color);
            color: white;
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            display: flex;
            align-items: center;
        }
        
        .logo i {
            margin-right: 10px;
            font-size: 1.8rem;
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 1.5rem;
        }
        
        nav ul li a {
            color: white;
            text-decoration: none;
            transition: color 0.3s;
            position: relative;
        }
        
        nav ul li a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background-color: var(--secondary-color);
            transition: width 0.3s;
        }
        
        nav ul li a:hover::after {
            width: 100%;
        }
        
        nav ul li a:hover {
            color: var(--secondary-color);
        }
        
        /* Герой секция */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1621905252507-b35492cc74b4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2069&q=80') no-repeat center center/cover;
            height: 80vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
        }
        
        .hero-content h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            transform: translateY(20px);
            opacity: 0;
            animation: fadeInUp 1s forwards 0.5s;
        }
        
        .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            transform: translateY(20px);
            opacity: 0;
            animation: fadeInUp 1s forwards 0.8s;
        }
        
        .btn {
            display: inline-block;
            background: var(--secondary-color);
            color: white;
            padding: 0.8rem 1.5rem;
            text-decoration: none;
            border-radius: 5px;
            transition: all 0.3s;
            font-weight: bold;
            transform: translateY(20px);
            opacity: 0;
            animation: fadeInUp 1s forwards 1.1s;
        }
        
        .btn:hover {
            background: var(--primary-color);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        /* Секции */
        section {
            padding: 5rem 0;
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s;
        }
        
        section.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        section:nth-child(even) {
            background-color: var(--light-bg);
        }
        
        h2 {
            text-align: center;
            margin-bottom: 3rem;
            color: var(--primary-color);
            font-size: 2.5rem;
            position: relative;
        }
        
        h2::after {
            content: '';
            position: absolute;
            width: 80px;
            height: 4px;
            background-color: var(--secondary-color);
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
        }
        
        /* О нас */
        .about-content {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
        }
        
        .about-text {
            flex: 1;
            min-width: 300px;
            padding-right: 2rem;
        }
        
        .about-text p {
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
            transition: transform 0.3s;
        }
        
        .about-text p:hover {
            transform: translateX(5px);
        }
        
        .about-image {
            flex: 1;
            min-width: 300px;
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        
        .about-image img {
            width: 100%;
            transition: transform 0.5s;
        }
        
        .about-image:hover img {
            transform: scale(1.05);
        }
        
        /* Процедура заказа */
        .order-steps {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
        }
        
        .step {
            flex: 0 0 calc(33.333% - 1rem);
            background: white;
            padding: 2rem;
            margin-bottom: 1.5rem;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }
        
        .step::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 5px;
            height: 0;
            background-color: var(--secondary-color);
            transition: height 0.5s;
        }
        
        .step:hover::before {
            height: 100%;
        }
        
        .step:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.1);
        }
        
        .step-number {
            position: absolute;
            top: 15px;
            right: 15px;
            background-color: var(--primary-color);
            color: white;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 1.2rem;
        }
        
        .step h3 {
            color: var(--primary-color);
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }
        
        /* Галерея с каруселью */
        .gallery-container {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        
        .gallery-carousel {
            display: flex;
            transition: transform 0.5s ease;
        }
        
        .gallery-item {
            min-width: 100%;
            height: 500px;
            position: relative;
            overflow: hidden;
        }
        
        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .carousel-btn {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background: rgba(255, 255, 255, 0.7);
            border: none;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            font-size: 1.5rem;
            cursor: pointer;
            transition: all 0.3s;
            z-index: 10;
        }
        
        .carousel-btn:hover {
            background: white;
            box-shadow: 0 0 10px rgba(0,0,0,0.2);
        }
        
        .prev-btn {
            left: 20px;
        }
        
        .next-btn {
            right: 20px;
        }
        
        .carousel-dots {
            position: absolute;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 10px;
        }
        
        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.5);
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .dot.active {
            background: white;
            transform: scale(1.2);
        }
        
        /* Контакты */
        .contact-info {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: flex-start;
            gap: 3rem;
        }
        
        .contact-details {
            flex: 1;
            min-width: 300px;
            padding: 1rem;
        }
        
        .contact-details p {
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
            display: flex;
            align-items: center;
            word-break: break-word;
        }
        
        .contact-details i {
            margin-right: 10px;
            color: var(--secondary-color);
            font-size: 1.2rem;
            width: 25px;
            flex-shrink: 0;
        }
        
        .contact-buttons {
            display: flex;
            gap: 15px;
            margin-top: 2rem;
            flex-wrap: wrap;
        }
        
        .contact-btn {
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 12px 20px;
            border-radius: 5px;
            text-decoration: none;
            color: white;
            font-weight: bold;
            transition: all 0.3s;
            flex: 1;
            min-width: 140px;
        }
        
        .contact-btn i {
            margin-right: 8px;
            font-size: 1.2rem;
        }
        
        .btn-telegram {
            background: #0088cc;
        }
        
        .btn-telegram:hover {
            background: #0077b5;
            transform: translateY(-3px);
        }
        
        .btn-call {
            background: var(--accent-color);
        }
        
        .btn-call:hover {
            background: #27ae60;
            transform: translateY(-3px);
        }
        
        .btn-viber {
            background: #7360F2;
        }
        
        .btn-viber:hover {
            background: #5a4bd1;
            transform: translateY(-3px);
        }
        
        .map-container {
            flex: 1;
            min-width: 300px;
            padding: 1rem;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            margin-left: 2rem; /* Додатковий зсув праворуч */
            max-width: 450px; /* Зменшена ширина для більшого простору */
        }
        
        .map-container iframe {
            width: 100%;
            height: 300px;
            border: none;
            border-radius: 10px;
        }
        
        /* Футер */
        footer {
            background: var(--primary-color);
            color: white;
            text-align: center;
            padding: 3rem 0;
        }
        
        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .social-links {
            display: flex;
            gap: 20px;
            margin: 1.5rem 0;
        }
        
        .social-links a {
            color: white;
            font-size: 1.5rem;
            transition: color 0.3s;
        }
        
        .social-links a:hover {
            color: var(--secondary-color);
        }
        
        /* Анимации */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        /* Адаптивность */
        @media (max-width: 992px) {
            .step {
                flex: 0 0 calc(50% - 1rem);
            }
            
            .map-container {
                margin-left: 0;
                max-width: 100%;
            }
        }
        
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
            }
            
            nav ul {
                margin-top: 1rem;
                flex-wrap: wrap;
                justify-content: center;
            }
            
            nav ul li {
                margin: 0.5rem;
            }
            
            .hero-content h1 {
                font-size: 2.2rem;
            }
            
            .step {
                flex: 0 0 100%;
            }
            
            .contact-buttons {
                flex-direction: column;
            }
            
            .gallery-item {
                height: 300px;
            }
            
            .contact-info {
                flex-direction: column;
                gap: 2rem;
            }
            
            .map-container {
                order: -1;
                width: 100%;
                margin-left: 0;
            }
        }
    </style>
</head>
<body>
    <!-- Шапка -->
    <header>
        <div class="container header-content">
            <div class="logo">
                <i class="fas fa-home"></i>
                Вікна та Двері Переяслав
            </div>
            <nav>
                <ul>
                    <li><a href="#about">Про нас</a></li>
                    <li><a href="#order">Як замовити</a></li>
                    <li><a href="#gallery">Галерея</a></li>
                    <li><a href="#contacts">Контакти</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Герой секция -->
    <section class="hero">
        <div class="container hero-content">
            <h1>Якісні вікна та двері у Переяславі</h1>
            <p>Професійний підбір, продаж та встановлення вікон і дверей</p>
            <a href="#contacts" class="btn">Зв'язатися з нами</a>
        </div>
    </section>

    <!-- О нас -->
    <section id="about">
        <div class="container">
            <h2>Про нас</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>Наш магазин працює за адресою:</p>
                    <p><strong>м. Переяслав, вул. Шкільна 44а, позиція 10</strong></p>
                    <p><strong>Графік роботи:</strong> Вт-Нд з 9:00 до 16:00</p>
                    <p>Ми спеціалізуємося на продажі та встановленні якісних вікон та дверей. Наша команда професіоналів допоможе вам підібрати оптимальні рішення для вашого дому чи офісу.</p>
                    <p>Ми пропонуємо широкий вибір моделей, кольорів та конфігурацій, щоб задовольнити будь-які потреби та смаки наших клієнтів.</p>
                </div>
                <div class="about-image">
                    <!-- ЗАМІНИТИ: Фото магазину ззовні або вивіски -->
                    <img src="https://images.unsplash.com/photo-1586023492125-27b2c045efd7?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1558&q=80" alt="Наш магазин">
                </div>
            </div>
        </div>
    </section>

    <!-- Процедура заказа -->
    <section id="order">
        <div class="container">
            <h2>Як замовити вікна чи двері</h2>
            <div class="order-steps">
                <div class="step">
                    <div class="step-number">1</div>
                    <h3>Орієнтовна ціна</h3>
                    <p>Ви можете самостійно приблизно виміряти свої вікна та ми зробимо прорахунок. Це допоможе вам зрозуміти бюджет замовлення.</p>
                </div>
                <div class="step">
                    <div class="step-number">2</div>
                    <h3>Точний замір</h3>
                    <p>Для точного розрахунку ціни знадобиться майстер. Послуга заміру оплачується окремо. У разі замовлення - замір, виготовлення, доставка враховуються у загальну вартість.</p>
                </div>
                <div class="step">
                    <div class="step-number">3</div>
                    <h3>Вибір параметрів</h3>
                    <p>Після заміру ви обираєте всі необхідні параметри: кількість камер, тип профілю, колір, відкривання, наявність москітної сітки та інші деталі.</p>
                </div>
                <div class="step">
                    <div class="step-number">4</div>
                    <h3>Оплата та договір</h3>
                    <p>Укладається договір з переліком вибраних параметрів, сумою оплати та іншими деталями. Оплачується мінімум 50% вартості замовлення.</p>
                </div>
                <div class="step">
                    <div class="step-number">5</div>
                    <h3>Виробництво та доставка</h3>
                    <p>Вікна виготовляються на заводі. По готовності вони доставляються до вас.</p>
                </div>
                <div class="step">
                    <div class="step-number">6</div>
                    <h3>Встановлення</h3>
                    <p>Майстер приїде в зручний для вас день для встановлення конструкції.</p>
                </div>
                <div class="step">
                    <div class="step-number">7</div>
                    <h3>Оплата решти</h3>
                    <p>Після завершення встановлення оплачується решта суми (50%), можливе відтермінування.</p>
                </div>
                <div class="step">
                    <div class="step-number">8</div>
                    <h3>Гарантія</h3>
                    <p>Ми надаємо гарантію від заводу. У разі необхідності, всі недоліки будуть оперативно усунені або замінено.</p>
                </div>
                <div class="step">
                    <div class="step-number">9</div>
                    <h3>Відгук</h3>
                    <p>Після завершення роботи ми будемо раді почути ваш відгук про нашу роботу. Ваша думка важлива для нас!</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Галерея -->
    <section id="gallery">
        <div class="container">
            <h2>Наші роботи</h2>
            <div class="gallery-container">
                <div class="gallery-carousel">
                    <!-- ЗАМІНИТИ: Фото встановлених вікон (екстер'єр) -->
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1558618666-fcd25856cd63?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Сучасні вікна">
                    </div>
                    <!-- ЗАМІНИТИ: Фото встановлених дверей (екстер'єр) -->
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1600585154340-6f2c0a19d9d4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Вхідні двері">
                    </div>
                    <!-- ЗАМІНИТИ: Фото балконних дверей -->
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1621905251189-08b45d6a269e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Балконні двері">
                    </div>
                    <!-- ЗАМІНИТИ: Фото міжкімнатних дверей -->
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1621905252507-b35492cc74b4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Міжкімнатні двері">
                    </div>
                    <!-- ЗАМІНИТИ: Фото енергоефективних вікон -->
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1600566753190-17f0baa2a6c3?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Енергоефективні вікна">
                    </div>
                    <!-- ЗАМІНИТИ: Фото вікон з москітними сітками -->
                    <div class="gallery-item">
                        <img src="https://images.unsplash.com/photo-1600585154526-990dced4db0d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1470&q=80" alt="Вікна з москітними сітками">
                    </div>
                </div>
                <button class="carousel-btn prev-btn"><i class="fas fa-chevron-left"></i></button>
                <button class="carousel-btn next-btn"><i class="fas fa-chevron-right"></i></button>
                <div class="carousel-dots">
                    <div class="dot active"></div>
                    <div class="dot"></div>
                    <div class="dot"></div>
                    <div class="dot"></div>
                    <div class="dot"></div>
                    <div class="dot"></div>
                </div>
            </div>
        </div>
    </section>

    <!-- Контакты -->
    <section id="contacts">
        <div class="container">
            <h2>Контакти</h2>
            <div class="contact-info">
                <div class="contact-details">
                    <p><i class="fas fa-envelope"></i><strong>Email:</strong> viknapereyaslavhm@gmail.com</p>
                    <p><i class="fas fa-phone"></i><strong>Телефон:</strong> +380 (63) 970 18 10</p>
                    <p><i class="fas fa-map-marker-alt"></i><strong>Адреса:</strong> м. Переяслав, вул. Шкільна 44а, поз. 10</p>
                    <p><i class="fas fa-clock"></i><strong>Графік роботи:</strong> Вт-Нд з 9:00 до 16:00</p>
                    
                    <div class="contact-buttons">
                        <a href="tel:+380639701810" class="contact-btn btn-call">
                            <i class="fas fa-phone"></i> Подзвонити
                        </a>
                        <a href="viber://chat?number=+380639701810" class="contact-btn btn-viber">
                            <i class="fab fa-viber"></i> Viber
                        </a>
                        <a href="https://t.me/your_telegram" class="contact-btn btn-telegram" target="_blank">
                            <i class="fab fa-telegram"></i> Telegram
                        </a>
                    </div>
                </div>
                <div class="map-container">
                    <!-- Карта магазина -->
                    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2537.123456789012!2d31.456789!3d50.123456!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2zNTDCsDA3JzI0LjQiTiAzMcKwMjcnMjQuNCJF!5e0!3m2!1suk!2sua!4v1234567890" allowfullscreen="" loading="lazy"></iframe>
                </div>
            </div>
        </div>
    </section>

    <!-- Футер -->
    <footer>
        <div class="container footer-content">
            <div class="logo" style="color: white; margin-bottom: 1rem;">
                <i class="fas fa-home"></i>
                Вікна та Двері Переяслав
            </div>
            <div class="social-links">
                <a href="#"><i class="fab fa-facebook"></i></a>
                <a href="#"><i class="fab fa-instagram"></i></a>
                <a href="https://t.me/your_telegram" target="_blank"><i class="fab fa-telegram"></i></a>
            </div>
            <p>&copy; 2023 Вікна та Двері Переяслав. Всі права захищені.</p>
        </div>
    </footer>

    <script>
        // Анимация появления элементов при прокрутке
        document.addEventListener('DOMContentLoaded', function() {
            const sections = document.querySelectorAll('section');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                    }
                });
            }, { threshold: 0.1 });
            
            sections.forEach(section => {
                observer.observe(section);
            });
            
            // Плавная прокрутка к якорям
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function(e) {
                    e.preventDefault();
                    
                    const targetId = this.getAttribute('href');
                    if (targetId === '#') return;
                    
                    const targetElement = document.querySelector(targetId);
                    if (targetElement) {
                        window.scrollTo({
                            top: targetElement.offsetTop - 80,
                            behavior: 'smooth'
                        });
                    }
                });
            });
            
            // Карусель галереи
            const carousel = document.querySelector('.gallery-carousel');
            const items = document.querySelectorAll('.gallery-item');
            const dots = document.querySelectorAll('.dot');
            const prevBtn = document.querySelector('.prev-btn');
            const nextBtn = document.querySelector('.next-btn');
            let currentIndex = 0;
            
            function updateCarousel() {
                carousel.style.transform = `translateX(-${currentIndex * 100}%)`;
                
                // Обновляем активную точку
                dots.forEach((dot, index) => {
                    dot.classList.toggle('active', index === currentIndex);
                });
            }
            
            nextBtn.addEventListener('click', () => {
                currentIndex = (currentIndex + 1) % items.length;
                updateCarousel();
            });
            
            prevBtn.addEventListener('click', () => {
                currentIndex = (currentIndex - 1 + items.length) % items.length;
                updateCarousel();
            });
            
            // Добавляем обработчики для точек
            dots.forEach((dot, index) => {
                dot.addEventListener('click', () => {
                    currentIndex = index;
                    updateCarousel();
                });
            });
            
            // Автопрокрутка карусели
            setInterval(() => {
                currentIndex = (currentIndex + 1) % items.length;
                updateCarousel();
            }, 5000);
        });
    </script>
</body>
</html>
