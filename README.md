<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>أفلام One Piece - موقع ثلاثي الأبعاد</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body, html {
            height: 100%;
            font-family: 'Arial', sans-serif;
            background: black;
            color: white;
            overflow-x: hidden;
            scroll-behavior: smooth;
        }

        .religious-banner {
            position: fixed;
            top: 80px;
            width: 100%;
            z-index: 9;
            background: linear-gradient(90deg, rgba(0, 150, 0, 0.9), rgba(0, 100, 0, 0.9));
            padding: 0.8rem;
            text-align: center;
            backdrop-filter: blur(10px);
            border-bottom: 2px solid rgba(0, 212, 255, 0.3);
            box-shadow: 0 4px 15px rgba(0, 150, 0, 0.3);
        }

        .religious-banner p {
            color: white;
            font-size: 1.1rem;
            font-weight: bold;
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
            margin: 0.3rem 0;
        }

        .religious-banner .main-message {
            font-size: 1.2rem;
            color: #ffeb3b;
        }

        .religious-banner .prayer-message {
            font-size: 1rem;
            color: #e8f5e8;
        }

        header {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 10;
            background: rgba(0, 0, 0, 0.9);
            padding: 1rem;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
            display: flex;
            justify-content: space-between;
            align-items: center;
            backdrop-filter: blur(10px);
        }

        header h1 {
            font-size: 1.8rem;
            color: #00d4ff;
            text-shadow: 0 0 10px #00d4ff;
        }

        header nav {
            display: flex;
            gap: 1rem;
        }

        header nav a {
            color: white;
            text-decoration: none;
            font-size: 1rem;
            transition: all 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 20px;
        }

        header nav a:hover {
            color: #00d4ff;
            background: rgba(0, 212, 255, 0.1);
            box-shadow: 0 0 10px rgba(0, 212, 255, 0.3);
        }

        header nav a[href*="facebook"] {
            background: linear-gradient(90deg, #1877f2, #42a5f5);
            color: white;
        }

        header nav a[href*="facebook"]:hover {
            background: linear-gradient(90deg, #1565c0, #1877f2);
            transform: scale(1.05);
        }

        canvas {
            display: block;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .container {
            position: relative;
            z-index: 5;
            text-align: center;
            margin-top: 12rem;
            padding: 2rem;
        }

        .container h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            background: linear-gradient(90deg, #00d4ff, #ff00f7);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 20px rgba(0, 212, 255, 0.5);
        }

        .container p {
            font-size: 1.2rem;
            max-width: 600px;
            margin: 1rem auto;
            color: #ccc;
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
        }

        .search-container {
            margin: 2rem auto;
            max-width: 800px;
            position: relative;
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
            justify-content: center;
            align-items: center;
        }

        .search-input {
            flex: 1;
            min-width: 300px;
            padding: 1rem 1.5rem;
            font-size: 1.1rem;
            background: rgba(0, 0, 0, 0.7);
            border: 2px solid #00d4ff;
            border-radius: 30px;
            color: white;
            outline: none;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .search-input:focus {
            box-shadow: 0 0 20px rgba(0, 212, 255, 0.5);
            border-color: #ff00f7;
        }

        .search-input::placeholder {
            color: #999;
        }

        .sort-select {
            padding: 1rem 1.5rem;
            font-size: 1.1rem;
            background: rgba(0, 0, 0, 0.7);
            border: 2px solid #ff00f7;
            border-radius: 30px;
            color: white;
            outline: none;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            cursor: pointer;
            min-width: 200px;
        }

        .sort-select:focus {
            box-shadow: 0 0 20px rgba(255, 0, 247, 0.5);
            border-color: #00d4ff;
        }

        .sort-select option {
            background: #1a1a1a;
            color: white;
            padding: 0.5rem;
        }

        .movies-section {
            position: relative;
            z-index: 5;
            padding: 2rem;
            margin-top: 2rem;
            max-width: 1200px;
            margin-left: auto;
            margin-right: auto;
        }

        .movies-section h2 {
            font-size: 2.5rem;
            margin-bottom: 2rem;
            text-align: center;
            background: linear-gradient(90deg, #00d4ff, #ff00f7);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 20px rgba(0, 212, 255, 0.5);
        }

        .movies-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .movie-card {
            background: rgba(0, 0, 0, 0.8);
            border-radius: 15px;
            padding: 1.5rem;
            border: 1px solid rgba(0, 212, 255, 0.3);
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            position: relative;
            overflow: hidden;
        }

        .movie-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 212, 255, 0.1), transparent);
            transition: left 0.5s ease;
        }

        .movie-card:hover::before {
            left: 100%;
        }

        .movie-card:hover {
            transform: translateY(-10px);
            border-color: #00d4ff;
            box-shadow: 0 20px 40px rgba(0, 212, 255, 0.2);
        }

        .movie-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 1rem;
        }

        .movie-title {
            font-size: 1.4rem;
            color: #00d4ff;
            margin-bottom: 0.5rem;
            text-shadow: 0 0 10px rgba(0, 212, 255, 0.3);
        }

        .movie-year {
            background: linear-gradient(90deg, #ff00f7, #00d4ff);
            padding: 0.3rem 0.8rem;
            border-radius: 15px;
            font-size: 0.9rem;
            font-weight: bold;
        }

        .movie-info {
            margin-bottom: 1rem;
        }

        .movie-info span {
            color: #ff00f7;
            font-weight: bold;
        }

        .movie-summary {
            color: #ccc;
            line-height: 1.6;
            margin-bottom: 1.5rem;
            text-align: justify;
        }

        .movie-links {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-top: 1rem;
        }

        .movie-link {
            display: inline-block;
            padding: 0.5rem 1rem;
            background: linear-gradient(90deg, #00d4ff, #ff00f7);
            color: white;
            text-decoration: none;
            border-radius: 20px;
            font-size: 0.9rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .movie-link:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(0, 212, 255, 0.4);
        }

        .loading {
            text-align: center;
            padding: 2rem;
            color: #00d4ff;
            font-size: 1.2rem;
        }

        .no-results {
            text-align: center;
            padding: 3rem;
            color: #999;
            font-size: 1.2rem;
        }

        .scroll-indicator {
            position: fixed;
            bottom: 2rem;
            left: 50%;
            transform: translateX(-50%);
            z-index: 10;
            color: #00d4ff;
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateX(-50%) translateY(0);
            }
            40% {
                transform: translateX(-50%) translateY(-10px);
            }
            60% {
                transform: translateX(-50%) translateY(-5px);
            }
        }

        @media (max-width: 768px) {
            .religious-banner {
                top: 120px;
                padding: 0.6rem;
            }
            
            .religious-banner .main-message {
                font-size: 1rem;
            }
            
            .religious-banner .prayer-message {
                font-size: 0.9rem;
            }
            
            .container {
                margin-top: 14rem;
            }
            
            .container h1 {
                font-size: 2rem;
            }
            
            .search-container {
                flex-direction: column;
                max-width: 90%;
            }
            
            .search-input, .sort-select {
                min-width: unset;
                width: 100%;
            }
            
            .movies-grid {
                grid-template-columns: 1fr;
                gap: 1rem;
            }
            
            .movie-card {
                padding: 1rem;
            }
            
            header {
                flex-direction: column;
                gap: 1rem;
                text-align: center;
            }
            
            header h1 {
                font-size: 1.4rem;
            }
            
            header nav a {
                font-size: 0.9rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>🏴‍☠️ أفلام One Piece</h1>
        <nav>
            <a href="#movies">الأفلام</a>
            <a href="#search">البحث</a>
            <a href="#about">عن الموقع</a>
            <a href="https://www.facebook.com/habib.zahamani" target="_blank">📘 Facebook</a>
        </nav>
    </header>

    <div class="religious-banner">
        <p class="main-message">🕌 عزيزي الزائر - الصلاة المفروضة وأوصى بها الرسول 🕌</p>
        <p class="prayer-message">🤲 صلوا على رسولنا الكريم محمد صلى الله عليه وسلم 🤲</p>
    </div>

    <canvas id="bg"></canvas>

    <div class="container">
        <h1>مكتبة أفلام One Piece الشاملة</h1>
        <p>استكشف جميع أفلام أنمي One Piece مع تلخيصات مفصلة ومواقع المشاهدة المتاحة</p>
        
        <div class="search-container" id="search">
            <input type="text" class="search-input" id="searchInput" placeholder="ابحث عن فيلم...">
            <select class="sort-select" id="sortSelect">
                <option value="year-desc">الأحدث أولاً</option>
                <option value="year-asc">الأقدم أولاً</option>
                <option value="title-asc">ترتيب أبجدي (أ-ي)</option>
                <option value="title-desc">ترتيب أبجدي (ي-أ)</option>
                <option value="rating-desc">أعلى تقييم</option>
                <option value="rating-asc">أقل تقييم</option>
            </select>
        </div>
    </div>

    <div class="scroll-indicator">
        ⬇️ مرر لأسفل لاستكشاف الأفلام
    </div>

    <div class="movies-section" id="movies">
        <h2>مجموعة الأفلام</h2>
        <div id="loading" class="loading">جاري تحميل الأفلام...</div>
        <div id="moviesGrid" class="movies-grid" style="display: none;"></div>
        <div id="noResults" class="no-results" style="display: none;">
            لم يتم العثور على أي أفلام تطابق البحث
        </div>
    </div>

    <script>
        // بيانات أفلام One Piece - مكتملة
        const movies = [
            {
                id: 1,
                title: "One Piece: The Movie",
                englishTitle: "One Piece: The Movie",
                year: 2000,
                duration: "51 دقيقة",
                genre: "مغامرة، أكشن",
                rating: "7.1",
                summary: "في أول مغامرة سينمائية لطاقم قبعة القش، يصل لوفي ورفاقه إلى جزيرة الذهب حيث يلتقون بالفتاة توبيكا التي تبحث عن كنز والدها المفقود. يواجه الطاقم القرصان الشرير إلدورادو جونز الذي يسيطر على الجزيرة ويستعبد سكانها للبحث عن الذهب.",
                watchLinks: [
                    { name: "Crunchyroll", url: "https://www.crunchyroll.com" },
                    { name: "Funimation", url: "https://www.funimation.com" }
                ]
            },
            {
                id: 2,
                title: "أغنية الجزيرة الميكانيكية",
                englishTitle: "Clockwork Island Adventure",
                year: 2001,
                duration: "55 دقيقة",
                genre: "مغامرة، كوميديا",
                rating: "7.2",
                summary: "يستيقظ طاقم قبعة القش ليجدوا سفينتهم الحبيبة Going Merry قد سُرقت! يتبعون اللصوص إلى جزيرة الساعة الميكانيكية حيث يحكمها الأخوان ترامب. يجب على لوفي وطاقمه مواجهة آلات عملاقة وأعداء أقوياء لاستعادة سفينتهم والمساعدة في تحرير الجزيرة.",
                watchLinks: [
                    { name: "Crunchyroll", url: "https://www.crunchyroll.com" },
                    { name: "Netflix", url: "https://www.netflix.com" }
                ]
            },
            {
                id: 3,
                title: "مملكة تشوبر في جزيرة الحيوانات الغريبة",
                englishTitle: "Chopper's Kingdom on the Island of Strange Animals",
                year: 2002,
                duration: "56 دقيقة",
                genre: "مغامرة، عائلي",
                rating: "6.8",
                summary: "يجد تشوبر نفسه ملكاً على جزيرة مليئة بحيوانات غريبة وعجيبة. يساعده طاقم قبعة القش في حماية الجزيرة من القرصان الشرير باتلر الذي يريد الاستيلاء على قرن الوحيد السحري الذي يمنح قوة هائلة.",
                watchLinks: [
                    { name: "AnimeLab", url: "https://www.animelab.com" },
                    { name: "Funimation", url: "https://www.funimation.com" }
                ]
            },
            {
                id: 4,
                title: "مغامرة الصحراء الميتة",
                englishTitle: "Dead End Adventure",
                year: 2003,
                duration: "95 دقيقة",
                genre: "مغامرة، أكشن",
                rating: "7.5",
                summary: "يشارك طاقم قبعة القش في سباق بحري خطير عبر الصحراء الميتة. يواجهون قراصنة أقوياء ومخاطر طبيعية مدمرة. خلال هذه المغامرة، يكتشفون أسراراً مظلمة حول ماضي أحد المتسابقين وعليهم إيقاف مؤامرة شيطانية.",
                watchLinks: [
                    { name: "Crunchyroll", url: "https://www.crunchyroll.com" },
                    { name: "Hulu", url: "https://www.hulu.com" }
                ]
            },
            {
                id: 5,
                title: "لعنة السيف المقدس",
                englishTitle: "The Cursed Holy Sword",
                year: 2004,
                duration: "95 دقيقة",
                genre: "أكشن، خيال",
                rating: "7.0",
                summary: "يغادر زورو الطاقم بشكل مفاجئ وينضم إلى البحرية المحلية في جزيرة أسكا. يكتشف لوفي وأصدقاؤه أن الجزيرة تحت تأثير سيوف مقدسة ملعونة تسيطر على عقول الناس. يجب عليهم إنقاذ زورو وكسر اللعنة قبل فوات الأوان.",
                watchLinks: [
                    { name: "Netflix", url: "https://www.netflix.com" },
                    { name: "AnimeLab", url: "https://www.animelab.com" }
                ]
            }
        ];

        // متغيرات التحكم
        let filteredMovies = [...movies];
        let currentSort = 'year-desc';

        // وظائف العرض والفلترة
        function displayMovies(moviesToShow) {
            const moviesGrid = document.getElementById('moviesGrid');
            const loading = document.getElementById('loading');
            const noResults = document.getElementById('noResults');

            loading.style.display = 'none';
            
            if (moviesToShow.length === 0) {
                moviesGrid.style.display = 'none';
                noResults.style.display = 'block';
                return;
            }

            noResults.style.display = 'none';
            moviesGrid.style.display = 'grid';
            
            moviesGrid.innerHTML = moviesToShow.map(movie => `
                <div class="movie-card" data-movie-id="${movie.id}">
                    <div class="movie-header">
                        <div>
                            <h3 class="movie-title">${movie.title}</h3>
                            <p style="color: #999; font-size: 0.9rem;">${movie.englishTitle}</p>
                        </div>
                        <span class="movie-year">${movie.year}</span>
                    </div>
                    
                    <div class="movie-info">
                        <p><span>المدة:</span> ${movie.duration}</p>
                        <p><span>النوع:</span> ${movie.genre}</p>
                        <p><span>التقييم:</span> ${movie.rating}/10</p>
                    </div>
                    
                    <div class="movie-summary">
                        ${movie.summary}
                    </div>
                    
                    <div class="movie-links">
                        ${movie.watchLinks.map(link => 
                            `<a href="${link.url}" target="_blank" class="movie-link">مشاهدة على ${link.name}</a>`
                        ).join('')}
                    </div>
                </div>
            `).join('');
        }

        function sortMovies(movies, sortType) {
            const sorted = [...movies];
            
            switch(sortType) {
                case 'year-desc':
                    return sorted.sort((a, b) => b.year - a.year);
                case 'year-asc':
                    return sorted.sort((a, b) => a.year - b.year);
                case 'title-asc':
                    return sorted.sort((a, b) => a.title.localeCompare(b.title, 'ar'));
                case 'title-desc':
                    return sorted.sort((a, b) => b.title.localeCompare(a.title, 'ar'));
                case 'rating-desc':
                    return sorted.sort((a, b) => parseFloat(b.rating) - parseFloat(a.rating));
                case 'rating-asc':
                    return sorted.sort((a, b) => parseFloat(a.rating) - parseFloat(b.rating));
                default:
                    return sorted;
            }
        }

        function filterMovies(searchTerm) {
            if (!searchTerm.trim()) {
                filteredMovies = [...movies];
            } else {
                filteredMovies = movies.filter(movie => 
                    movie.title.toLowerCase().includes(searchTerm.toLowerCase()) ||
                    movie.englishTitle.toLowerCase().includes(searchTerm.toLowerCase()) ||
                    movie.summary.toLowerCase().includes(searchTerm.toLowerCase()) ||
                    movie.genre.toLowerCase().includes(searchTerm.toLowerCase()) ||
                    movie.year.toString().includes(searchTerm)
                );
  
