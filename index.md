<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Яндекс Браузер — быстрый и безопасный браузер</title>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Yandex+Sans+Text:wght@400;500;700&display=swap">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        :root {
            --yandex-red: #FF0000;
            --yandex-blue: #2A7FFF;
            --yandex-dark-blue: #0057FF;
            --yandex-black: #000000;
            --yandex-gray-dark: #333333;
            --yandex-gray: #666666;
            --yandex-gray-light: #F5F5F5;
            --yandex-white: #FFFFFF;
            --yandex-border: #E6E6E6;
        }
        
        body {
            font-family: 'Yandex Sans Text', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            color: var(--yandex-gray-dark);
            line-height: 1.5;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }
        
        .container {
            max-width: 1240px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Шапка */
        .header {
            background-color: var(--yandex-white);
            border-bottom: 1px solid var(--yandex-border);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 64px;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
            text-decoration: none;
        }
        
        .logo-icon {
            width: 32px;
            height: 32px;
            background: linear-gradient(135deg, var(--yandex-red), var(--yandex-blue));
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 18px;
        }
        
        .logo-text {
            font-size: 20px;
            font-weight: 700;
            color: var(--yandex-black);
        }
        
        .nav {
            display: flex;
            gap: 32px;
        }
        
        .nav-link {
            text-decoration: none;
            color: var(--yandex-gray-dark);
            font-weight: 500;
            font-size: 15px;
            transition: color 0.2s;
        }
        
        .nav-link:hover {
            color: var(--yandex-blue);
        }
        
        .download-btn {
            background-color: var(--yandex-blue);
            color: white;
            border: none;
            border-radius: 8px;
            padding: 10px 24px;
            font-weight: 500;
            font-size: 15px;
            cursor: pointer;
            transition: background-color 0.2s;
            text-decoration: none;
            display: inline-block;
        }
        
        .download-btn:hover {
            background-color: var(--yandex-dark-blue);
        }
        
        /* Главный баннер */
        .hero {
            background-color: var(--yandex-gray-light);
            padding: 80px 0;
            position: relative;
            overflow: hidden;
        }
        
        .hero-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 60px;
        }
        
        .hero-text {
            flex: 1;
            max-width: 560px;
        }
        
        .hero-title {
            font-size: 48px;
            font-weight: 700;
            line-height: 1.1;
            margin-bottom: 24px;
            color: var(--yandex-black);
        }
        
        .hero-title span {
            color: var(--yandex-blue);
        }
        
        .hero-subtitle {
            font-size: 18px;
            color: var(--yandex-gray);
            margin-bottom: 32px;
            max-width: 480px;
        }
        
        .hero-cta {
            display: flex;
            align-items: center;
            gap: 16px;
            margin-bottom: 40px;
        }
        
        .hero-btn {
            background-color: var(--yandex-blue);
            color: white;
            border: none;
            border-radius: 10px;
            padding: 16px 32px;
            font-weight: 500;
            font-size: 17px;
            cursor: pointer;
            transition: background-color 0.2s;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }
        
        .hero-btn:hover {
            background-color: var(--yandex-dark-blue);
        }
        
        .hero-btn-secondary {
            background-color: transparent;
            color: var(--yandex-gray-dark);
            border: 1px solid var(--yandex-border);
        }
        
        .hero-btn-secondary:hover {
            background-color: rgba(0, 0, 0, 0.02);
        }
        
        .hero-image {
            flex: 1;
            max-width: 540px;
            position: relative;
        }
        
        .hero-image img {
            width: 100%;
            border-radius: 12px;
            box-shadow: 0 12px 48px rgba(0, 0, 0, 0.1);
        }
        
        .platforms {
            display: flex;
            align-items: center;
            gap: 24px;
        }
        
        .platform-icon {
            width: 24px;
            height: 24px;
            opacity: 0.7;
            transition: opacity 0.2s;
        }
        
        .platform-icon:hover {
            opacity: 1;
        }
        
        /* Преимущества */
        .features {
            padding: 100px 0;
        }
        
        .section-title {
            font-size: 36px;
            font-weight: 700;
            text-align: center;
            margin-bottom: 60px;
            color: var(--yandex-black);
        }
        
        .features-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 32px;
        }
        
        .feature-card {
            background-color: var(--yandex-white);
            border-radius: 12px;
            padding: 32px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.04);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .feature-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 32px rgba(0, 0, 0, 0.08);
        }
        
        .feature-icon {
            width: 56px;
            height: 56px;
            border-radius: 12px;
            background-color: rgba(42, 127, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 24px;
        }
        
        .feature-icon img {
            width: 28px;
            height: 28px;
        }
        
        .feature-title {
            font-size: 20px;
            font-weight: 700;
            margin-bottom: 12px;
            color: var(--yandex-black);
        }
        
        .feature-description {
            color: var(--yandex-gray);
            font-size: 15px;
        }
        
        /* Секция с Алисой */
        .alice-section {
            background-color: var(--yandex-gray-light);
            padding: 100px 0;
        }
        
        .alice-content {
            display: flex;
            align-items: center;
            gap: 80px;
        }
        
        .alice-image {
            flex: 1;
        }
        
        .alice-image img {
            width: 100%;
            max-width: 400px;
            border-radius: 12px;
        }
        
        .alice-text {
            flex: 1;
        }
        
        .alice-title {
            font-size: 36px;
            font-weight: 700;
            margin-bottom: 24px;
            color: var(--yandex-black);
        }
        
        .alice-description {
            font-size: 18px;
            color: var(--yandex-gray);
            margin-bottom: 32px;
        }
        
        .alice-features {
            display: flex;
            flex-direction: column;
            gap: 16px;
            margin-bottom: 40px;
        }
        
        .alice-feature {
            display: flex;
            align-items: center;
            gap: 12px;
        }
        
        .alice-feature-icon {
            width: 24px;
            height: 24px;
            color: var(--yandex-blue);
        }
        
        /* Секция безопасности */
        .security-section {
            padding: 100px 0;
        }
        
        .security-content {
            display: flex;
            align-items: center;
            gap: 80px;
        }
        
        .security-text {
            flex: 1;
        }
        
        .security-title {
            font-size: 36px;
            font-weight: 700;
            margin-bottom: 24px;
            color: var(--yandex-black);
        }
        
        .security-description {
            font-size: 18px;
            color: var(--yandex-gray);
            margin-bottom: 32px;
        }
        
        .security-image {
            flex: 1;
        }
        
        .security-image img {
            width: 100%;
            max-width: 400px;
            border-radius: 12px;
        }
        
        /* Секция загрузки */
        .download-section {
            background-color: var(--yandex-gray-light);
            padding: 100px 0;
            text-align: center;
        }
        
        .download-title {
            font-size: 36px;
            font-weight: 700;
            margin-bottom: 16px;
            color: var(--yandex-black);
        }
        
        .download-subtitle {
            font-size: 18px;
            color: var(--yandex-gray);
            margin-bottom: 48px;
            max-width: 560px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .download-card {
            background-color: var(--yandex-white);
            border-radius: 16px;
            padding: 48px;
            max-width: 800px;
            margin: 0 auto;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.06);
        }
        
        .download-card-title {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 32px;
            color: var(--yandex-black);
        }
        
        .download-options {
            display: flex;
            justify-content: center;
            gap: 24px;
            margin-bottom: 40px;
            flex-wrap: wrap;
        }
        
        .download-option {
            background-color: var(--yandex-gray-light);
            border-radius: 12px;
            padding: 24px;
            min-width: 160px;
            transition: background-color 0.2s;
            cursor: pointer;
            border: 2px solid transparent;
        }
        
        .download-option:hover {
            background-color: rgba(42, 127, 255, 0.05);
            border-color: var(--yandex-blue);
        }
        
        .download-option-icon {
            width: 48px;
            height: 48px;
            margin: 0 auto 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 24px;
        }
        
        .download-option-name {
            font-weight: 700;
            margin-bottom: 4px;
            color: var(--yandex-black);
        }
        
        .download-option-version {
            font-size: 14px;
            color: var(--yandex-gray);
        }
        
        .download-main-btn {
            background-color: var(--yandex-blue);
            color: white;
            border: none;
            border-radius: 10px;
            padding: 18px 40px;
            font-weight: 500;
            font-size: 18px;
            cursor: pointer;
            transition: background-color 0.2s;
            display: inline-flex;
            align-items: center;
            gap: 12px;
            margin-top: 16px;
        }
        
        .download-main-btn:hover {
            background-color: var(--yandex-dark-blue);
        }
        
        /* Футер */
        .footer {
            background-color: var(--yandex-black);
            color: var(--yandex-white);
            padding: 60px 0 40px;
        }
        
        .footer-content {
            display: flex;
            justify-content: space-between;
            margin-bottom: 40px;
        }
        
        .footer-logo {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 24px;
            text-decoration: none;
        }
        
        .footer-logo-icon {
            width: 32px;
            height: 32px;
            background: white;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--yandex-black);
            font-weight: bold;
            font-size: 18px;
        }
        
        .footer-logo-text {
            font-size: 20px;
            font-weight: 700;
            color: white;
        }
        
        .footer-description {
            color: rgba(255, 255, 255, 0.7);
            max-width: 300px;
            font-size: 14px;
        }
        
        .footer-links {
            display: flex;
            gap: 60px;
        }
        
        .footer-column {
            display: flex;
            flex-direction: column;
            gap: 16px;
        }
        
        .footer-column-title {
            font-weight: 700;
            margin-bottom: 8px;
            font-size: 15px;
        }
        
        .footer-link {
            color: rgba(255, 255, 255, 0.7);
            text-decoration: none;
            font-size: 14px;
            transition: color 0.2s;
        }
        
        .footer-link:hover {
            color: white;
        }
        
        .footer-bottom {
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            padding-top: 32px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: rgba(255, 255, 255, 0.5);
            font-size: 14px;
        }
        
        /* Адаптивность */
        @media (max-width: 1024px) {
            .features-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .hero-content, .alice-content, .security-content {
                flex-direction: column;
                gap: 40px;
            }
            
            .hero-text {
                text-align: center;
                max-width: 100%;
            }
            
            .hero-title {
                font-size: 40px;
            }
        }
        
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                height: auto;
                padding: 16px 0;
                gap: 16px;
            }
            
            .nav {
                gap: 20px;
            }
            
            .hero {
                padding: 60px 0;
            }
            
            .hero-title {
                font-size: 32px;
            }
            
            .features-grid {
                grid-template-columns: 1fr;
            }
            
            .section-title {
                font-size: 28px;
            }
            
            .alice-title, .security-title, .download-title {
                font-size: 28px;
            }
            
            .footer-content {
                flex-direction: column;
                gap: 40px;
            }
            
            .footer-links {
                flex-wrap: wrap;
                gap: 30px;
            }
            
            .download-card {
                padding: 32px 20px;
            }
            
            .download-options {
                flex-direction: column;
                align-items: center;
            }
            
            .download-option {
                width: 100%;
                max-width: 240px;
            }
        }
        
        @media (max-width: 480px) {
            .nav {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .hero-cta {
                flex-direction: column;
                align-items: center;
            }
            
            .hero-btn {
                width: 100%;
                justify-content: center;
            }
            
            .platforms {
                justify-content: center;
                flex-wrap: wrap;
            }
        }
    </style>
</head>
<body>
    <!-- Шапка -->
    <header class="header">
        <div class="container header-content">
            <a href="#" class="logo">
                <div class="logo-icon">Я</div>
                <div class="logo-text">Браузер</div>
            </a>
            <nav class="nav">
                <a href="#features" class="nav-link">Возможности</a>
                <a href="#alice" class="nav-link">Алиса</a>
                <a href="#security" class="nav-link">Безопасность</a>
                <a href="#download" class="nav-link">Скачать</a>
            </nav>
            <a href="#download" class="download-btn">Скачать</a>
        </div>
    </header>

    <!-- Главный баннер -->
    <section class="hero">
        <div class="container hero-content">
            <div class="hero-text">
                <h1 class="hero-title">Быстрый браузер <span>с Алисой</span></h1>
                <p class="hero-subtitle">Скачайте Яндекс Браузер бесплатно и насладитесь быстрым поиском информации! Простой, понятный и функциональный браузер для пользователей с любыми потребностями.</p>
                <div class="hero-cta">
                    <a href="#download" class="hero-btn">
                        <svg width="20" height="20" viewBox="0 0 20 20" fill="none" style="margin-right: 8px;">
                            <path d="M10 2.5V10M10 10L7.5 7.5M10 10L12.5 7.5M2.5 10.8333V12.5C2.5 14.1569 3.84315 15.5 5.5 15.5H14.5C16.1569 15.5 17.5 14.1569 17.5 12.5V10.8333" stroke="white" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                        </svg>
                        Скачать бесплатно
                    </a>
                    <a href="#features" class="hero-btn hero-btn-secondary">Узнать больше</a>
                </div>
                <div class="platforms">
                    <span style="color: var(--yandex-gray); font-size: 14px;">Доступно для:</span>
                    <svg class="platform-icon" width="24" height="24" viewBox="0 0 24 24" fill="none">
                        <path d="M18 3H6C4.34315 3 3 4.34315 3 6V18C3 19.6569 4.34315 21 6 21H18C19.6569 21 21 19.6569 21 18V6C21 4.34315 19.6569 3 18 3Z" stroke="currentColor" stroke-width="1.5"/>
                        <path d="M8 10H16M8 14H16M8 18H13" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
                    </svg>
                    <svg class="platform-icon" width="24" height="24" viewBox="0 0 24 24" fill="none">
                        <path d="M4 5C4 3.89543 4.89543 3 6 3H10V21H6C4.89543 21 4 20.1046 4 19V5Z" stroke="currentColor" stroke-width="1.5"/>
                        <path d="M10 3H14C15.1046 3 16 3.89543 16 5V19C16 20.1046 15.1046 21 14 21H10V3Z" stroke="currentColor" stroke-width="1.5"/>
                        <path d="M16 7H20C21.1046 7 22 7.89543 22 9V15C22 16.1046 21.1046 17 20 17H16V7Z" stroke="currentColor" stroke-width="1.5"/>
                    </svg>
                    <svg class="platform-icon" width="24" height="24" viewBox="0 0 24 24" fill="none">
                        <path d="M12 22C17.5228 22 22 17.5228 22 12C22 6.47715 17.5228 2 12 2C6.47715 2 2 6.47715 2 12C2 17.5228 6.47715 22 12 22Z" stroke="currentColor" stroke-width="1.5"/>
                        <path d="M15 9L9 15" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
                        <path d="M9 9L15 15" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
                    </svg>
                </div>
            </div>
            <div class="hero-image">
                <img src="https://images.unsplash.com/photo-1555099962-4199c345e5dd?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80" alt="Интерфейс Яндекс Браузера">
            </div>
        </div>
    </section>

    <!-- Преимущества -->
    <section id="features" class="features">
        <div class="container">
            <h2 class="section-title">Что умеет Яндекс Браузер</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">
                        <svg width="28" height="28" viewBox="0 0 28 28" fill="none">
                            <path d="M14 2.33333V25.6667M14 2.33333L8.16667 8.16667M14 2.33333L19.8333 8.16667" stroke="#2A7FFF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                        </svg>
                    </div>
                    <h3 class="feature-title">Режим Турбо</h3>
                    <p class="feature-description">Ускоряет загрузку страниц при медленном интернете и экономит трафик до 50%.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <svg width="28" height="28" viewBox="0 0 28 28" fill="none">
                            <path d="M24.5 14C24.5 19.799 19.799 24.5 14 24.5C8.20101 24.5 3.5 19.799 3.5 14C3.5 8.20101 8.20101 3.5 14 3.5C19.799 3.5 24.5 8.20101 24.5 14Z" stroke="#2A7FFF" stroke-width="2"/>
                            <path d="M10.5 14L12.8333 16.3333L17.5 11.6667" stroke="#2A7FFF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                        </svg>
                    </div>
                    <h3 class="feature-title">Защита Protect</h3>
                    <p class="feature-description">Проверяет файлы на вирусы и предупреждает о опасных сайтах. Защищает пароли и данные.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">
                        <svg width="28" height="28" viewBox="0 0 28 28" fill="none">
                            <path d="M25.6667 14C25.6667 20.4433 20.4433 25.6667 14 25.6667C7.55672 25.6667 2.33333 20.4433 2.33333 14C2.33333 7.55672 7.55672 2.33333 14 2.33333C20.4433 2.33333 25.6667 7.55672 25.6667 14Z" stroke="#2A7FFF" stroke-width="2"/>
                            <path d="M19.8333 10.5H8.16667C7.0621 10.5 6.16667 11.3954 6.16667 12.5V19.8333C6.16667 20.9379 7.0621 21.8333 8.16667 21.8333H19.8333C20.9379 21.8333 21.8333 20.9379 21.8333 19.8333V12.5C21.8333 11.3954 20.9379 10.5 19.8333 10.5Z" stroke="#2A7FFF" stroke-width="2"/>
                            <path d="M6.16667 12.5L14 16.9167L21.8333 12.5" stroke="#2A7FFF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                        </svg>
                    </div>
                    <h3 class="feature-title">Умная строка</h3>
                    <p class="feature-description">Понимает, что вы ищете. Просто введите вопрос или название сайта.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Секция с Алисой -->
    <section id="alice" class="alice-section">
        <div class="container alice-content">
            <div class="alice-image">
                <img src="https://images.unsplash.com/photo-1581094794329-c8112a89af12?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80" alt="Голосовой помощник Алиса">
            </div>
            <div class="alice-text">
                <h2 class="alice-title">Алиса в браузере</h2>
                <p class="alice-description">Встроенный голосовой помощник, который ответит на вопрос, включит музыку или поможет найти информацию в интернете.</p>
                <div class="alice-features">
                    <div class="alice-feature">
                        <svg class="alice-feature-icon" width="24" height="24" viewBox="0 0 24 24" fill="none">
                            <path d="M12 2C6.48 2 2 6.48 2 12C2 17.52 6.48 22 12 22C17.52 22 22 17.52 22 12C22 6.48 17.52 2 12 2Z" fill="#2A7FFF"/>
                            <path d="M12 6V12L16 14" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                        </svg>
                        <span>Работает в фоновом режиме</span>
                    </div>
                    <div class="alice-feature">
                        <svg class="alice-feature-icon" width="24" height="24" viewBox="0 0 24 24" fill="none">
                            <path d="M12 2C6.48 2 2 6.48 2 12C2 17.52 6.48 22 12 22C17.52 22 22 17.52 22 12C22 6.48 17.52 2 12 2Z" fill="#2A7FFF"/>
                            <path d="M9 12L11 14L15 10" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                        </svg>
                        <span>Понимает голосовые команды</span>
                    </div>
                    <div class="alice-feature">
                        <svg class="alice-feature-icon" width="24" height="24" viewBox="0 0 24 24" fill="none">
                            <path d="M12 2C6.48 2 2 6.48 2 12C2 17.52 6.48 22 12 22C17.52 22 22 17.52 22 12C22 6.48 17.52 2 12 2Z" fill="#2A7FFF"/>
                            <path d="M12 16V12M12 8H12.01" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                        </svg>
                        <span>Помогает в повседневных задачах</span>
                    </div>
                </div>
                <a href="#download" class="hero-btn">Скачать с Алисой</a>
            </div>
        </div>
    </section>

    <!-- Секция безопасности -->
    <section id="security" class="security-section">
        <div class="container security-content">
            <div class="security-text">
                <h2 class="security-title">Безопасность в приоритете</h2>
                <p class="security-description">Защита Protect проверяет все скачиваемые файлы на наличие вирусов, предупреждает о вредоносных сайтах и защищает пароли и данные.</p>
                <div class="alice-features">
                    <div class="alice-feature">
                        <svg class="alice-feature-icon" width="24" height="24" viewBox="0 0 24 24" fill="none">
                            <path d="M12 22C17.5228 22 22 17.5228 22 12C22 6.47715 17.5228 2 12 2C6.47715 2 2 6.47715 2 12C2 17.5228 6.47715 22 12 22Z" fill="#2A7FFF"/>
                            <path d="M9 12L11 14L15 10" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                        </svg>
                        <span>Защита онлайн-платежей</span>
                    </div>
                    <div class="alice-feature">
                        <svg class="alice-feature-icon" width="24" height="24" viewBox="0 0 24 24" fill="none">
                            <path d="M12 22C17.5228 22 22 17.5228 22 12C22 6.47715 17.5228 2 12 2C6.47715 2 2 6.47715 2 12C2 17.5228 6.47715 22 12 22Z" fill="#2A7FFF"/>
                            <path d="M9 12L11 14L15 10" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                        </svg>
                        <span>Проверка файлов на вирусы</span>
                    </div>
                    <div class="alice-feature">
                        <svg class="alice-feature-icon" width="24" height="24" viewBox="0 0 24 24" fill="none">
                            <path d="M12 22C17.5228 22 22 17.5228 22 12C22 6.47715 17.5228 2 12 2C6.47715 2 2 6.47715 2 12C2 17.5228 6.47715 22 12 22Z" fill="#2A7FFF"/>
                            <path d="M9 12L11 14L15 10" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                        </svg>
                        <span>Блокировка опасных сайтов</span>
                    </div>
                </div>
            </div>
            <div class="security-image">
                <img src="https://images.unsplash.com/photo-1550751827-4bd374c3f58b?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80" alt="Защита браузера">
            </div>
        </div>
    </section>

    <!-- Секция загрузки -->
    <section id="download" class="download-section">
        <div class="container">
            <h2 class="download-title">Скачать Яндекс Браузер</h2>
            <p class="download-subtitle">Установите последнюю версию Яндекс Браузера для вашей операционной системы</p>
            <div class="download-card">
                <h3 class="download-card-title">Выберите вашу платформу</h3>
                <div class="download-options">
                    <div class="download-option" onclick="selectPlatform('windows')">
                        <div class="download-option-icon">
                            <svg width="48" height="48" viewBox="0 0 48 48" fill="none">
                                <rect x="8" y="8" width="32" height="32" rx="4" stroke="#2A7FFF" stroke-width="2"/>
                                <path d="M16 16H32M16 20H32M16 24H26" stroke="#2A7FFF" stroke-width="2" stroke-linecap="round"/>
                            </svg>
                        </div>
                        <div class="download-option-name">Windows</div>
                        <div class="download-option-version">10 / 11 / 7</div>
                    </div>
                    <div class="download-option" onclick="selectPlatform('macos')">
                        <div class="download-option-icon">
                            <svg width="48" height="48" viewBox="0 0 48 48" fill="none">
                                <path d="M40 16C40 9.37258 34.6274 4 28 4C21.3726 4 16 9.37258 16 16C16 22.6274 21.3726 28 28 28C34.6274 28 40 22.6274 40 16Z" stroke="#2A7FFF" stroke-width="2"/>
                                <path d="M8 32L16 28L24 44L16 44L8 32Z" stroke="#2A7FFF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                                <path d="M32 32L40 28L48 44L40 44L32 32Z" stroke="#2A7FFF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                            </svg>
                        </div>
                        <div class="download-option-name">macOS</div>
                        <div class="download-option-version">10.12 и выше</div>
                    </div>
                    <div class="download-option" onclick="selectPlatform('linux')">
                        <div class="download-option-icon">
                            <svg width="48" height="48" viewBox="0 0 48 48" fill="none">
                                <path d="M24 44C35.0457 44 44 35.0457 44 24C44 12.9543 35.0457 4 24 4C12.9543 4 4 12.9543 4 24C4 35.0457 12.9543 44 24 44Z" stroke="#2A7FFF" stroke-width="2"/>
                                <path d="M16 16L32 32" stroke="#2A7FFF" stroke-width="2" stroke-linecap="round"/>
                                <path d="M32 16L16 32" stroke="#2A7FFF" stroke-width="2" stroke-linecap="round"/>
                            </svg>
                        </div>
                        <div class="download-option-name">Linux</div>
                        <div class="download-option-version">DEB / RPM</div>
                    </div>
                </div>
                <button class="download-main-btn" id="downloadBtn">
                    <svg width="20" height="20" viewBox="0 0 20 20" fill="none">
                        <path d="M10 2.5V10M10 10L7.5 7.5M10 10L12.5 7.5M2.5 10.8333V12.5C2.5 14.1569 3.84315 15.5 5.5 15.5H14.5C16.1569 15.5 17.5 14.1569 17.5 12.5V10.8333" stroke="white" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                    </svg>
                    Скачать для Windows
                </button>
                <p style="margin-top: 24px; font-size: 14px; color: var(--yandex-gray);">Размер установщика: ~85 МБ</p>
            </div>
        </div>
    </section>

    <!-- Футер -->
    <footer class="footer">
        <div class="container">
            <div class="footer-content">
                <div>
                    <a href="#" class="footer-logo">
                        <div class="footer-logo-icon">Я</div>
                        <div class="footer-logo-text">Браузер</div>
                    </a>
                    <p class="footer-description">Быстрый и безопасный браузер с голосовым помощником Алиса. Разработан для комфортного использования интернета.</p>
                </div>
                <div class="footer-links">
                    <div class="footer-column">
                        <div class="footer-column-title">Продукт</div>
                        <a href="#features" class="footer-link">Возможности</a>
                        <a href="#alice" class="footer-link">Алиса</a>
                        <a href="#security" class="footer-link">Безопасность</a>
                        <a href="#download" class="footer-link">Скачать</a>
                    </div>
                    <div class="footer-column">
                        <div class="footer-column-title">Поддержка</div>
                        <a href="#" class="footer-link">Справка</a>
                        <a href="#" class="footer-link">Сообщество</a>
                        <a href="#" class="footer-link">Обратная связь</a>
                    </div>
                    <div class="footer-column">
                        <div class="footer-column-title">Компания</div>
                        <a href="#" class="footer-link">О Яндекс</a>
                        <a href="#" class="footer-link">Блог</a>
                        <a href="#" class="footer-link">Вакансии</a>
                    </div>
                </div>
            </div>
            <div class="footer-bottom">
                <div>© 2023 Яндекс Браузер</div>
                <div>
                    <a href="#" class="footer-link" style="margin-right: 20px;">Условия использования</a>
                    <a href="#" class="footer-link">Политика конфиденциальности</a>
                </div>
            </div>
        </div>
    </footer>

    <script>
        // Выбор платформы для скачивания
        let selectedPlatform = 'windows';
        
        function selectPlatform(platform) {
            selectedPlatform = platform;
            
            // Удаляем выделение у всех опций
            document.querySelectorAll('.download-option').forEach(option => {
                option.style.backgroundColor = '';
                option.style.borderColor = '';
            });
            
            // Добавляем выделение выбранной опции
            const selectedOption = event.currentTarget;
            selectedOption.style.backgroundColor = 'rgba(42, 127, 255, 0.05)';
            selectedOption.style.borderColor = 'var(--yandex-blue)';
            
            // Обновляем текст кнопки
            const downloadBtn = document.getElementById('downloadBtn');
            let platformText = '';
            
            switch(platform) {
                case 'windows':
                    platformText = 'Windows';
                    break;
                case 'macos':
                    platformText = 'macOS';
                    break;
                case 'linux':
                    platformText = 'Linux';
                    break;
            }
            
            downloadBtn.innerHTML = `
                <svg width="20" height="20" viewBox="0 0 20 20" fill="none">
                    <path d="M10 2.5V10M10 10L7.5 7.5M10 10L12.5 7.5M2.5 10.8333V12.5C2.5 14.1569 3.84315 15.5 5.5 15.5H14.5C16.1569 15.5 17.5 14.1569 17.5 12.5V10.8333" stroke="white" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
                Скачать для ${platformText}
            `;
        }
        
        // Имитация скачивания
        document.getElementById('downloadBtn').addEventListener('click', function() {
            const platformNames = {
                'windows': 'Windows',
                'macos': 'macOS', 
                'linux': 'Linux'
            };
            
            alert(`Начинается загрузка Яндекс Браузера для ${platformNames[selectedPlatform]}. В реальной версии сайта файл начнет скачиваться автоматически.`);
        });
        
        // Плавная прокрутка к якорям
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
        
        // Выделяем первую опцию по умолчанию
        document.querySelector('.download-option').style.backgroundColor = 'rgba(42, 127, 255, 0.05)';
        document.querySelector('.download-option').style.borderColor = 'var(--yandex-blue)';
    </script>
</body>
</html>
