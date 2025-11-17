# Portfolio_Андрєєва
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Портфоліо вчителя математики - Андрєєва Світлана Володимирівна</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .floating-shapes {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
            overflow: hidden;
        }

        .shape {
            position: absolute;
            opacity: 0.1;
            animation: float 20s infinite ease-in-out;
        }

        .shape:nth-child(1) {
            width: 80px;
            height: 80px;
            background: white;
            border-radius: 50%;
            top: 10%;
            left: 10%;
            animation-delay: 0s;
        }

        .shape:nth-child(2) {
            width: 60px;
            height: 60px;
            background: white;
            top: 70%;
            right: 15%;
            animation-delay: 5s;
            clip-path: polygon(50% 0%, 100% 100%, 0% 100%);
        }

        .shape:nth-child(3) {
            width: 100px;
            height: 100px;
            background: white;
            border-radius: 20px;
            bottom: 10%;
            left: 20%;
            animation-delay: 10s;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-30px) rotate(180deg); }
        }

        .container {
            max-width: 1400px;
            margin: 30px auto;
            background: white;
            border-radius: 30px;
            overflow: hidden;
            box-shadow: 0 30px 80px rgba(0,0,0,0.3);
            position: relative;
            z-index: 1;
        }

        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 80px 40px 60px;
            position: relative;
            overflow: hidden;
        }

        .hero-pattern {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: 
                repeating-linear-gradient(45deg, transparent, transparent 35px, rgba(255,255,255,.05) 35px, rgba(255,255,255,.05) 70px);
            pointer-events: none;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            display: flex;
            align-items: center;
            gap: 50px;
            max-width: 1200px;
            margin: 0 auto;
            flex-wrap: wrap;
            justify-content: center;
        }

        .profile-section {
            text-align: center;
        }

        .profile-photo-wrapper {
            position: relative;
            width: 220px;
            height: 220px;
            margin: 0 auto 30px;
        }

        .profile-photo {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            border: 8px solid white;
            box-shadow: 0 15px 40px rgba(0,0,0,0.3);
            object-fit: cover;
            transition: transform 0.4s ease;
        }

        .profile-photo:hover {
            transform: scale(1.05);
        }

        .profile-ring {
            position: absolute;
            top: -15px;
            left: -15px;
            right: -15px;
            bottom: -15px;
            border: 3px dashed rgba(255,255,255,0.5);
            border-radius: 50%;
            animation: rotate 20s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .hero-text {
            flex: 1;
            min-width: 300px;
        }

        .hero-text h1 {
            font-size: 3em;
            margin-bottom: 15px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }

        .hero-text .subtitle {
            font-size: 1.5em;
            opacity: 0.95;
            margin-bottom: 25px;
        }

        .contact-info {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
            margin-bottom: 15px;
        }

        .contact-btn {
            background: white;
            color: #667eea;
            padding: 12px 25px;
            border-radius: 25px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .contact-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(0,0,0,0.3);
        }

        .stats-bar {
            background: rgba(255,255,255,0.15);
            backdrop-filter: blur(10px);
            padding: 30px;
            margin-top: 40px;
            border-radius: 20px;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 30px;
            text-align: center;
        }

        .stat-item {
            padding: 10px;
        }

        .stat-number {
            font-size: 2.5em;
            font-weight: bold;
            display: block;
            margin-bottom: 5px;
        }

        .stat-label {
            font-size: 0.95em;
            opacity: 0.9;
        }

        .nav-container {
            position: sticky;
            top: 0;
            background: white;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .nav-tabs {
            display: flex;
            max-width: 1200px;
            margin: 0 auto;
            overflow-x: auto;
            scrollbar-width: thin;
        }

        .nav-tab {
            padding: 25px 35px;
            cursor: pointer;
            border: none;
            background: none;
            font-size: 1.1em;
            font-weight: 600;
            color: #666;
            transition: all 0.3s;
            white-space: nowrap;
            border-bottom: 4px solid transparent;
            position: relative;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .nav-tab::before {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            transform: scaleX(0);
            transition: transform 0.3s;
        }

        .nav-tab:hover {
            color: #667eea;
        }

        .nav-tab.active {
            color: #667eea;
        }

        .nav-tab.active::before {
            transform: scaleX(1);
        }

        .content {
            padding: 60px 40px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .tab-content {
            display: none;
            animation: slideIn 0.5s ease;
        }

        .tab-content.active {
            display: block;
        }

        @keyframes slideIn {
            from { 
                opacity: 0; 
                transform: translateY(30px);
            }
            to { 
                opacity: 1; 
                transform: translateY(0);
            }
        }

        .section {
            margin-bottom: 50px;
        }

        .section-title {
            font-size: 2em;
            color: #667eea;
            margin-bottom: 30px;
            display: flex;
            align-items: center;
            gap: 15px;
            padding-bottom: 15px;
            border-bottom: 3px solid #667eea;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -3px;
            left: 0;
            width: 100px;
            height: 3px;
            background: #764ba2;
        }

        .grid-2 {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 25px;
        }

        .card {
            background: white;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            transition: all 0.3s ease;
            border: 2px solid #f0f0f0;
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 5px;
            height: 100%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            transform: scaleY(0);
            transition: transform 0.3s;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(102, 126, 234, 0.2);
            border-color: #667eea;
        }

        .card:hover::before {
            transform: scaleY(1);
        }

        .card h3 {
            color: #764ba2;
            font-size: 1.4em;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .card-icon {
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2em;
        }

        .achievement-card {
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.05) 0%, rgba(118, 75, 162, 0.05) 100%);
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 20px;
            border-left: 5px solid #667eea;
            transition: all 0.3s;
            cursor: pointer;
        }

        .achievement-card:hover {
            transform: translateX(10px);
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1) 0%, rgba(118, 75, 162, 0.1) 100%);
        }

        .achievement-card h4 {
            color: #667eea;
            font-size: 1.3em;
            margin-bottom: 12px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .badge {
            display: inline-block;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 6px 18px;
            border-radius: 20px;
            font-size: 0.85em;
            font-weight: 600;
            margin-right: 10px;
            box-shadow: 0 3px 10px rgba(102, 126, 234, 0.3);
        }

        .list-modern {
            list-style: none;
            padding: 0;
        }

        .list-modern li {
            padding: 15px;
            padding-left: 45px;
            position: relative;
            margin-bottom: 10px;
            background: #f8f9fa;
            border-radius: 10px;
            transition: all 0.3s;
        }

        .list-modern li:hover {
            background: rgba(102, 126, 234, 0.08);
            padding-left: 50px;
        }

        .list-modern li::before {
            content: "✓";
            position: absolute;
            left: 15px;
            top: 50%;
            transform: translateY(-50%);
            color: white;
            font-weight: bold;
            font-size: 1em;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            width: 25px;
            height: 25px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .timeline {
            position: relative;
            padding-left: 40px;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 3px;
            background: linear-gradient(180deg, #667eea 0%, #764ba2 100%);
        }

        .timeline-item {
            position: relative;
            margin-bottom: 30px;
            padding: 20px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
            transition: all 0.3s;
        }

        .timeline-item:hover {
            transform: translateX(10px);
            box-shadow: 0 8px 25px rgba(102, 126, 234, 0.2);
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -48px;
            top: 25px;
            width: 15px;
            height: 15px;
            border-radius: 50%;
            background: white;
            border: 4px solid #667eea;
            box-shadow: 0 0 0 4px white;
        }

        .quote-box {
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1) 0%, rgba(118, 75, 162, 0.1) 100%);
            padding: 40px;
            border-radius: 20px;
            font-size: 1.2em;
            line-height: 1.9;
            font-style: italic;
            position: relative;
            border-left: 6px solid #667eea;
            box-shadow: 0 5px 20px rgba(0,0,0,0.05);
        }

        .quote-box::before {
            content: '"';
            position: absolute;
            top: 10px;
            left: 15px;
            font-size: 4em;
            color: #667eea;
            opacity: 0.3;
            font-family: Georgia, serif;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .skill-item {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s;
            cursor: pointer;
        }

        .skill-item:hover {
            transform: translateY(-8px) scale(1.05);
            box-shadow: 0 15px 30px rgba(102, 126, 234, 0.4);
        }

        .skill-icon {
            font-size: 2.5em;
            margin-bottom: 10px;
        }

        .skill-name {
            font-size: 1.1em;
            font-weight: 600;
        }

        .filter-tabs {
            display: flex;
            gap: 15px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        .filter-btn {
            padding: 12px 25px;
            border: 2px solid #667eea;
            background: white;
            color: #667eea;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            font-size: 1em;
        }

        .filter-btn:hover {
            background: #667eea;
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.3);
        }

        .filter-btn.active {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .course-card {
            background: white;
            padding: 30px;
            border-radius: 20px;
            margin-bottom: 20px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.08);
            border-left: 6px solid #667eea;
            transition: all 0.3s;
        }

        .course-card:hover {
            transform: translateX(10px);
            box-shadow: 0 10px 30px rgba(102, 126, 234, 0.2);
            border-left-width: 10px;
        }

        .course-title {
            font-size: 1.4em;
            color: #667eea;
            font-weight: 700;
            margin-bottom: 15px;
        }

        .course-meta {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
            margin-bottom: 15px;
        }

        .hours-badge {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 8px 20px;
            border-radius: 20px;
            font-weight: 600;
            font-size: 0.95em;
        }

        .date-badge {
            background: #f8f9fa;
            color: #667eea;
            padding: 8px 20px;
            border-radius: 20px;
            font-weight: 600;
            font-size: 0.95em;
            border: 2px solid #667eea;
        }

        .course-type {
            display: inline-block;
            padding: 5px 12px;
            border-radius: 12px;
            font-size: 0.85em;
            font-weight: 600;
            margin-top: 10px;
        }

        .type-pk {
            background: rgba(102, 126, 234, 0.1);
            color: #667eea;
        }

        .type-methodical {
            background: rgba(118, 75, 162, 0.1);
            color: #764ba2;
        }

        .type-conference {
            background: rgba(52, 211, 153, 0.1);
            color: #059669;
        }

        .summary-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .summary-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 25px;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.3);
        }

        .summary-number {
            font-size: 3em;
            font-weight: bold;
            margin-bottom: 5px;
        }

        .summary-label {
            font-size: 1em;
            opacity: 0.95;
        }

        .year-divider {
            display: flex;
            align-items: center;
            gap: 20px;
            margin: 40px 0 30px;
        }

        .year-divider::before,
        .year-divider::after {
            content: '';
            flex: 1;
            height: 3px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        .year-label {
            font-size: 1.8em;
            font-weight: bold;
            color: #667eea;
            padding: 10px 30px;
            background: white;
            border: 3px solid #667eea;
            border-radius: 25px;
        }

        .scroll-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 50%;
            cursor: pointer;
            display: none;
            align-items: center;
            justify-content: center;
            font-size: 1.5em;
            box-shadow: 0 5px 20px rgba(102, 126, 234, 0.4);
            transition: all 0.3s;
            z-index: 1000;
        }

        .scroll-top:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(102, 126, 234, 0.6);
        }

        .scroll-top.visible {
            display: flex;
        }

        @media (max-width: 768px) {
            .hero {
                padding: 50px 20px 40px;
            }

            .hero-content {
                gap: 30px;
            }

            .hero-text h1 {
                font-size: 2em;
            }

            .hero-text .subtitle {
                font-size: 1.2em;
            }

            .profile-photo-wrapper {
                width: 180px;
                height: 180px;
            }

            .stats-bar {
                grid-template-columns: repeat(2, 1fr);
                padding: 20px;
            }

            .content {
                padding: 40px 20px;
            }

            .nav-tab {
                padding: 18px 25px;
                font-size: 1em;
            }

            .grid-2 {
                grid-template-columns: 1fr;
            }

            .section-title {
                font-size: 1.6em;
            }

            .timeline {
                padding-left: 30px;
            }

            .quote-box {
                padding: 30px 20px;
                font-size: 1.05em;
            }
        }
    </style>
</head>
<body>
    <div class="floating-shapes">
        <div class="shape"></div>
        <div class="shape"></div>
        <div class="shape"></div>
    </div>

    <div class="container">
        <div class="hero">
            <div class="hero-pattern"></div>
            <div class="hero-content">
                <div class="profile-section">
                    <div class="profile-photo-wrapper">
                        <div class="profile-ring"></div>
                        
                        <!-- ВАРІАНТ 1: Якщо ваше фото називається photo.jpg -->
                        <img src="photo.jpg" alt="Андрєєва Світлана Володимирівна" class="profile-photo">
                        
                        <!-- ВАРІАНТ 2: Якщо фото називається інакше, змініть назву нижче -->
                        <!-- <img src="ім'я_вашого_фото.jpg" alt="Андрєєва Світлана Володимирівна" class="profile-photo"> -->
                        
                        <!-- ВАРІАНТ 3: Використайте повний шлях до фото -->
                        <!-- <img src="C:/Users/ВашеІм'я/Desktop/photo.jpg" alt="Андрєєва Світлана Володимирівна" class="profile-photo"> -->
                    </div>
                </div>
                <div class="hero-text">
                    <h1>Андрєєва Світлана Володимирівна</h1>
                    <div class="subtitle">🎓 Вчитель математики та інформатики</div>
                    <div class="contact-info">
                        <a href="mailto:svetlanaburkatfndreeva@gmail.com" class="contact-btn">
                            📧 svetlanaburkatfndreeva@gmail.com
                        </a>
                    </div>
                    <div style="margin-bottom: 20px; font-size: 1.1em;">
                        📍 КЗО "Інгулецький ліцей "ДОР", м. Кривий Ріг
                    </div>
                    <div style="display: flex; gap: 15px; flex-wrap: wrap;">
                        <a href="https://svetlanaburkatfndreeva.blogspot.com/" target="_blank" class="contact-btn">
                            📝 Блог вчителя
                        </a>
                        <a href="https://andreeva2024.blogspot.com/" target="_blank" class="contact-btn">
                            📐 Кабінет математики
                        </a>
                        <a href="https://in4ma6ka.blogspot.com/" target="_blank" class="contact-btn">
                            💻 Кабінет інформатики
                        </a>
                    </div>
                    <div class="stats-bar">
                        <div class="stat-item">
                            <span class="stat-number">23+</span>
                            <span class="stat-label">років досвіду</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number">I</span>
                            <span class="stat-label">категорія</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number">45+</span>
                            <span class="stat-label">курсів ПК</span>
                        </div>
                        <div class="stat-item">
                            <span class="stat-number">608+</span>
                            <span class="stat-label">годин навчання</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="nav-container">
            <div class="nav-tabs">
                <button class="nav-tab active" onclick="showTab('about')">
                    👤 Про мене
                </button>
                <button class="nav-tab" onclick="showTab('achievements')">
                    🏆 Досягнення
                </button>
                <button class="nav-tab" onclick="showTab('professional')">
                    💼 Діяльність
                </button>
                <button class="nav-tab" onclick="showTab('courses')">
                    🎓 Курси ПК
                </button>
                <button class="nav-tab" onclick="showTab('philosophy')">
                    💡 Філософія
                </button>
            </div>
        </div>

        <div class="content">
            <div id="about" class="tab-content active">
                <div class="section">
                    <h2 class="section-title">🎓 Освіта та досвід</h2>
                    <div class="grid-2">
                        <div class="card">
                            <div class="card-icon">🎓</div>
                            <h3>Освіта</h3>
                            <p><strong>Криворізький державний педагогічний університет</strong></p>
                            <p>Факультет математики та інформатики</p>
                            <p class="badge">2004 рік</p>
                        </div>
                        <div class="card">
                            <div class="card-icon">🏅</div>
                            <h3>Кваліфікація</h3>
                            <p><strong>Перша кваліфікаційна категорія</strong></p>
                            <p>Вчитель математики та інформатики вищої категорії</p>
                        </div>
                    </div>
                </div>

                <div class="section">
                    <h2 class="section-title">💼 Досвід роботи</h2>
                    <div class="timeline">
                        <div class="timeline-item">
                            <h3>КЗО "Інгулецький ліцей "ДОР"</h3>
                            <p><span class="badge">2022 - теперішній час</span></p>
                            <p><strong>Вчитель математики та інформатики</strong></p>
                            <p>Підготовка учнів до олімпіад, проведення консультацій, експертна діяльність, ведення освітніх блогів</p>
                        </div>
                        <div class="timeline-item">
                            <h3>ЗОШ І-ІІІ ступенів № 59 м. Кривого Рогу</h3>
                            <p><span class="badge">2002 - 2022</span></p>
                            <p><strong>Вчитель математики</strong></p>
                            <p>20 років успішної педагогічної практики, підготовка призерів олімпіад</p>
                        </div>
                    </div>
                </div>

                <div class="section">
                    <h2 class="section-title">🌐 Онлайн-ресурси та блоги</h2>
                    <div class="grid-2">
                        <div class="card">
                            <div class="card-icon">📝</div>
                            <h3>Блог вчителя математики</h3>
                            <p>Особистий блог з методичними матеріалами, досвідом роботи, розробками уроків та цікавими знахідками для вчителів математики.</p>
                            <a href="https://svetlanaburkatfndreeva.blogspot.com/" target="_blank" style="display: inline-block; margin-top: 15px; padding: 10px 20px; background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; text-decoration: none; border-radius: 10px; font-weight: 600;">
                                Відвідати блог →
                            </a>
                        </div>

                        <div class="card">
                            <div class="card-icon">📐</div>
                            <h3>Кабінет математики</h3>
                            <p>Віртуальний кабінет математики з навчальними матеріалами, завданнями для учнів, презентаціями та корисними посиланнями.</p>
                            <a href="https://andreeva2024.blogspot.com/" target="_blank" style="display: inline-block; margin-top: 15px; padding: 10px 20px; background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; text-decoration: none; border-radius: 10px; font-weight: 600;">
                                Відвідати кабінет →
                            </a>
                        </div>

                        <div class="card">
                            <div class="card-icon">💻</div>
                            <h3>Кабінет інформатики</h3>
                            <p>Віртуальний кабінет інформатики з матеріалами для уроків, проектами учнів, посиланнями на корисні сервіси та ресурси.</p>
                            <a href="https://in4ma6ka.blogspot.com/" target="_blank" style="display: inline-block; margin-top: 15px; padding: 10px 20px; background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; text-decoration: none; border-radius: 10px; font-weight: 600;">
                                Відвідати кабінет →
                            </a>
                        </div>
                    </div>
                </div>

                <div class="section">
                    <h2 class="section-title">🎯 Ключові компетенції</h2>
                    <div class="skills-grid">
                        <div class="skill-item">
                            <div class="skill-icon">📊</div>
                            <div class="skill-name">Підготовка до олімпіад</div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-icon">💻</div>
                            <div class="skill-name">Цифрові технології</div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-icon">🎓</div>
                            <div class="skill-name">Методична робота</div>
                        </div>
                        <div class="skill-item">
                            <div class="skill-icon">👥</div>
                            <div class="skill-name">Робота з обдарованими</div>
                        </div>
                    </div>
                </div>
            </div>

            <div id="achievements" class="tab-content">
                <div class="section">
                    <h2 class="section-title">🏆 Олімпіадні досягнення учнів</h2>
                    
                    <div class="achievement-card">
                        <h4>🌟 Студникова Агнія</h4>
                        <p><span class="badge">2023</span><span class="badge">2024</span><span class="badge">2025</span></p>
                        <p><strong>Призер районних, міських та обласних турів Всеукраїнської олімпіади з математики</strong></p>
                        <ul class="list-modern">
                            <li>Стабільні результати протягом 3 років</li>
                            <li>Обласний рівень змагань</li>
                            <li>Систематична підготовка та високі досягнення</li>
                        </ul>
                    </div>

                    <div class="achievement-card">
                        <h4>⭐ Ткаченко Олеся</h4>
                        <p><span class="badge">2024</span></p>
                        <p><strong>Призер районного та міського турів Всеукраїнської олімпіади з математики</strong></p>
                        <ul class="list-modern">
                            <li>Успішний дебют на олімпіадах</li>
                            <li>Високий рівень підготовки</li>
                        </ul>
                    </div>
                </div>

                <div class="section">
                    <h2 class="section-title">🌐 Інтернет-олімпіади та конкурси</h2>
                    <div class="card">
                        <h3>💻 Постійна участь учнів у онлайн-змаганнях</h3>
                        <ul class="list-modern">
                            <li>Всеукраїнська інтернет-олімпіада «На Урок»</li>
                            <li>Олімпіада від Всеосвіти</li>
                            <li>Всеукраїнські шкільні олімпіади від JustClass</li>
                            <li>Математичні конкурси на платформі МійКлас</li>
                        </ul>
                    </div>
                </div>
            </div>

            <div id="professional" class="tab-content">
                <div class="section">
                    <h2 class="section-title">🎖️ Професійні досягнення</h2>
                    <div class="grid-2">
                        <div class="card">
                            <h3>🏅 Нагороди та відзнаки</h3>
                            <p>Численні грамоти та подяки районного та міського рівнів за:</p>
                            <ul class="list-modern">
                                <li>Якісну підготовку учнів</li>
                                <li>Внесок у розвиток математичної освіти</li>
                                <li>Професійну майстерність</li>
                            </ul>
                        </div>

                        <div class="card">
                            <h3>👨‍⚖️ Експертна діяльність</h3>
                            <p><strong>Член журі олімпіад:</strong></p>
                            <ul class="list-modern">
                                <li>Районний етап Всеукраїнської олімпіади</li>
                                <li>Міський етап Всеукраїнської олімпіади</li>
                                <li>Конкурс "Студія математичних ідей"</li>
                            </ul>
                        </div>
                    </div>
                </div>

                <div class="section">
                    <h2 class="section-title">📚 Методична та освітня робота</h2>
                    
                    <div class="achievement-card">
                        <h4>💻 Цифрова діяльність</h4>
                        <ul class="list-modern">
                            <li>Розміщення тестів та публікацій на сайті "Всеосвіта"</li>
                            <li>Ведення трьох тематичних блогів (математика, інформатика)</li>
                            <li>Активна участь у професійних онлайн-спільнотах</li>
                        </ul>
                    </div>

                    <div class="achievement-card">
                        <h4>🎓 Консультаційна діяльність</h4>
                        <ul class="list-modern">
                            <li>Проведення консультацій з математики для учнів 7 класів на міському освітньому порталі</li>
                            <li>Консультації для учнів з предметів базового компоненту освітньої програми</li>
                            <li>Індивідуальна підтримка обдарованих учнів</li>
                            <li>Підготовка до олімпіад та конкурсів</li>
                        </ul>
                    </div>

                    <div class="achievement-card">
                        <h4>✍️ Методичні розробки</h4>
                        <ul class="list-modern">
                            <li>Розробка дидактичних матеріалів</li>
                            <li>Впровадження інноваційних підходів до викладання</li>
                            <li>Підготовка учнів до олімпіад та конкурсів</li>
                        </ul>
                    </div>
                </div>
            </div>

            <div id="courses" class="tab-content">
                <div class="section">
                    <h2 class="section-title">🎓 Підвищення кваліфікації</h2>
                    
                    <div class="summary-stats">
                        <div class="summary-card">
                            <div class="summary-number">45+</div>
                            <div class="summary-label">Курсів 2021-2025</div>
                        </div>
                        <div class="summary-card">
                            <div class="summary-number">608+</div>
                            <div class="summary-label">Годин навчання</div>
                        </div>
                        <div class="summary-card">
                            <div class="summary-number">100%</div>
                            <div class="summary-label">Сертифіковано</div>
                        </div>
                    </div>

                    <div class="filter-tabs">
                        <button class="filter-btn active" onclick="filterCourses('all')">Всі курси</button>
                        <button class="filter-btn" onclick="filterCourses('2025')">2025 рік</button>
                        <button class="filter-btn" onclick="filterCourses('2024')">2024 рік</button>
                        <button class="filter-btn" onclick="filterCourses('2023')">2023 рік</button>
                    </div>

                    <div id="coursesContainer">
                        <div class="year-divider">
                            <div class="year-label">2025</div>
                        </div>

                        <div class="course-card" data-year="2025">
                            <div class="course-title">Організація освітнього процесу з математики та інформатики у НУШ</div>
                            <div class="course-meta">
                                <span class="date-badge">📅 13-24.10.2025</span>
                                <span class="hours-badge">⏱️ 60 годин</span>
                            </div>
                            <p><strong>Організатор:</strong> Дніпровська академія неперервної освіти</p>
                            <span class="course-type type-pk">Свідоцтво СПК</span>
                        </div>

                        <div class="course-card" data-year="2025">
                            <div class="course-title">Оновлення методичного інструментарію учителів інформатики</div>
                            <div class="course-meta">
                                <span class="date-badge">📅 22-26.09.2025</span>
                                <span class="hours-badge">⏱️ 30 годин</span>
                            </div>
                            <p><strong>Організатор:</strong> Дніпровська академія неперервної освіти</p>
                            <span class="course-type type-pk">Свідоцтво СПК</span>
                        </div>

                        <div class="year-divider">
                            <div class="year-label">2024</div>
                        </div>

                        <div class="course-card" data-year="2024">
                            <div class="course-title">Організація освітнього процесу з математики у 7-9 класах</div>
                            <div class="course-meta">
                                <span class="date-badge">📅 01.11.2024</span>
                                <span class="hours-badge">⏱️ 30 годин</span>
                            </div>
                            <p><strong>Організатор:</strong> Дніпровська академія неперервної освіти</p>
                            <span class="course-type type-pk">Свідоцтво СПК</span>
                        </div>

                        <div class="year-divider">
                            <div class="year-label">2023</div>
                        </div>

                        <div class="course-card" data-year="2023">
                            <div class="course-title">Наздоженемо: практичні аспекти подолання освітніх втрат з математики</div>
                            <div class="course-meta">
                                <span class="date-badge">📅 27.12.2023</span>
                                <span class="hours-badge">⏱️ 15 годин</span>
                            </div>
                            <p><strong>Організатор:</strong> ГС «Освіторія»</p>
                            <span class="course-type type-pk">Сертифікат</span>
                        </div>

                        <div class="card" style="margin-top: 40px;">
                            <h3>📊 Детальна статистика</h3>
                            <p><strong style="color: #667eea;">2025:</strong> 11 курсів (253+ годин)</p>
                            <p><strong style="color: #667eea;">2024:</strong> 10 курсів (131.5 годин)</p>
                            <p><strong style="color: #667eea;">2023:</strong> 10 курсів (95 годин)</p>
                            <p><strong style="color: #667eea;">2022:</strong> 5 курсів (27+ годин)</p>
                            <p><strong style="color: #667eea;">2021:</strong> 7 курсів (102+ годин)</p>
                            <p style="margin-top: 15px; font-weight: bold; color: #764ba2; font-size: 1.2em;">Загалом: 608+ годин професійного розвитку</p>
                        </div>
                    </div>
                </div>
            </div>

            <div id="philosophy" class="tab-content">
                <div class="section">
                    <h2 class="section-title">💡 Педагогічна філософія</h2>
                    <div class="quote-box">
                        Математика — це не лише формули та теореми, це спосіб мислення та інструмент для розуміння світу. Моє завдання — не просто навчити рахувати, а розвинути у дітей логічне мислення, аналітичні здібності та впевненість у своїх силах. Кожен учень здатен досягти успіху, якщо знайти правильний підхід та надати необхідну підтримку.
                    </div>
                </div>

                <div class="section">
                    <h2 class="section-title">🎯 Педагогічні принципи</h2>
                    <div class="grid-2">
                        <div class="card">
                            <h3>🌱 Індивідуальний підхід</h3>
                            <p>Кожна дитина унікальна. Прагну знайти особливий ключик до кожного учня, враховуючи його темп навчання, інтереси та здібності.</p>
                        </div>
                        <div class="card">
                            <h3>💪 Розвиток потенціалу</h3>
                            <p>Віра у можливості кожного учня. Створення умов для розкриття талантів та подолання труднощів у навчанні.</p>
                        </div>
                        <div class="card">
                            <h3>🔍 Критичне мислення</h3>
                            <p>Формування навичок аналізу, логічного мислення та вміння вирішувати нестандартні задачі.</p>
                        </div>
                        <div class="card">
                            <h3>🌟 Любов до предмета</h3>
                            <p>Прагну показати красу математики, її практичне застосування та важливість у повсякденному житті.</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <button class="scroll-top" id="scrollTop" onclick="scrollToTop()">
        ↑
    </button>

    <script>
        function showTab(tabId) {
            const tabs = document.querySelectorAll('.tab-content');
            const buttons = document.querySelectorAll('.nav-tab');
            
            tabs.forEach(tab => tab.classList.remove('active'));
            buttons.forEach(btn => btn.classList.remove('active'));
            
            document.getElementById(tabId).classList.add('active');
            event.target.closest('.nav-tab').classList.add('active');
            
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        }

        function filterCourses(year) {
            const cards = document.querySelectorAll('.course-card');
            const buttons = document.querySelectorAll('.filter-btn');
            
            buttons.forEach(btn => btn.classList.remove('active'));
            event.target.classList.add('active');
            
            cards.forEach(card => {
                if (year === 'all' || card.getAttribute('data-year') === year) {
                    card.style.display = 'block';
                } else {
                    card.style.display = 'none';
                }
            });
        }

        window.addEventListener('scroll', function() {
            const scrollTop = document.getElementById('scrollTop');
            if (window.pageYOffset > 300) {
                scrollTop.classList.add('visible');
            } else {
                scrollTop.classList.remove('visible');
            }
        });

        function scrollToTop() {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        }
    </script>
</body>
</html>
