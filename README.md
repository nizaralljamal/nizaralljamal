<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>محمد - مطور ومتخصص مساحة جوية</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* أنماط عامة */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #2c3e50;
            --secondary: #3498db;
            --accent: #e74c3c;
            --light: #ecf0f1;
            --dark: #2c3e50;
        }
        
        body {
            background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
            color: var(--light);
            line-height: 1.6;
            overflow-x: hidden;
        }
        
        /* الشريط العلوي */
        header {
            background: rgba(44, 62, 80, 0.9);
            padding: 1.5rem;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--light);
            text-decoration: none;
            display: flex;
            align-items: center;
        }
        
        .logo i {
            margin-right: 10px;
            color: var(--secondary);
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 2rem;
        }
        
        .nav-links a {
            color: var(--light);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
            position: relative;
        }
        
        .nav-links a:hover {
            color: var(--secondary);
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--secondary);
            transition: width 0.3s;
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }
        
        /* الأقسام */
        section {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding-top: 80px;
            position: relative;
            overflow: hidden;
        }
        
        .hero-content {
            max-width: 800px;
            z-index: 2;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            background: linear-gradient(45deg, var(--secondary), var(--accent));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: gradientMove 5s infinite alternate;
        }
        
        @keyframes gradientMove {
            0% { background-position: 0% 50%; }
            100% { background-position: 100% 50%; }
        }
        
        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            color: var(--light);
        }
        
        .typewriter {
            border-right: 3px solid var(--secondary);
            white-space: nowrap;
            overflow: hidden;
            animation: typing 4s steps(30, end), blink-caret 0.7s step-end infinite;
        }
        
        @keyframes typing {
            from { width: 0; }
            to { width: 100%; }
        }
        
        @keyframes blink-caret {
            from, to { border-color: transparent; }
            50% { border-color: var(--secondary); }
        }
        
        .btn {
            display: inline-block;
            padding: 1rem 2rem;
            background: var(--secondary);
            color: white;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            text-decoration: none;
            box-shadow: 0 4px 15px rgba(52, 152, 219, 0.3);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(52, 152, 219, 0.4);
            background: #2980b9;
        }
        
        /* قسم عني */
        .about {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            margin: 2rem auto;
            backdrop-filter: blur(10px);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
        }
        
        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
            display: inline-block;
            left: 50%;
            transform: translateX(-50%);
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, var(--secondary), var(--accent));
            border-radius: 3px;
        }
        
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }
        
        .about-text h3 {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            color: var(--secondary);
        }
        
        .about-text p {
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
        }
        
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }
        
        .skill {
            background: rgba(255, 255, 255, 0.1);
            padding: 1.5rem;
            border-radius: 10px;
            text-align: center;
            transition: transform 0.3s, box-shadow 0.3s;
            cursor: pointer;
        }
        
        .skill:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            background: linear-gradient(135deg, var(--secondary), #1a5276);
        }
        
        .skill i {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--secondary);
        }
        
        .skill:hover i {
            color: white;
        }
        
        .skill h4 {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
        }
        
        /* قسم المشاريع */
        .projects {
            padding: 5rem 2rem;
        }
        
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }
        
        .project-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            overflow: hidden;
            transition: transform 0.3s, box-shadow 0.3s;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }
        
        .project-img {
            height: 200px;
            background: linear-gradient(45deg, #3498db, #2ecc71);
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .project-img i {
            font-size: 4rem;
            color: white;
        }
        
        .project-content {
            padding: 1.5rem;
        }
        
        .project-content h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--secondary);
        }
        
        .project-content p {
            margin-bottom: 1.5rem;
        }
        
        /* قسم الاتصال */
        .contact {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 5rem 2rem;
            margin: 2rem auto;
            backdrop-filter: blur(10px);
        }
        
        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
        }
        
        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
        }
        
        .contact-item i {
            font-size: 1.5rem;
            color: var(--secondary);
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 2rem;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: var(--light);
            font-size: 1.5rem;
            transition: all 0.3s;
        }
        
        .social-links a:hover {
            background: var(--secondary);
            transform: translateY(-5px);
        }
        
        /* الخلفية المتحركة */
        .background-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
        }
        
        .circle {
            position: absolute;
            border-radius: 50%;
            background: rgba(52, 152, 219, 0.1);
            animation: float 15s infinite linear;
        }
        
        .circle:nth-child(1) {
            width: 150px;
            height: 150px;
            top: 10%;
            left: 10%;
            animation-delay: 0s;
        }
        
        .circle:nth-child(2) {
            width: 200px;
            height: 200px;
            top: 50%;
            left: 70%;
            animation-delay: -2s;
        }
        
        .circle:nth-child(3) {
            width: 100px;
            height: 100px;
            top: 70%;
            left: 20%;
            animation-delay: -4s;
        }
        
        .circle:nth-child(4) {
            width: 180px;
            height: 180px;
            top: 30%;
            left: 60%;
            animation-delay: -6s;
        }
        
        .circle:nth-child(5) {
            width: 120px;
            height: 120px;
            top: 80%;
            left: 80%;
            animation-delay: -8s;
        }
        
        @keyframes float {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }
        
        /* تأثيرات التمرير */
        .fade-in {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.8s, transform 0.8s;
        }
        
        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        /* responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .about-content,
            .contact-content {
                grid-template-columns: 1fr;
            }
            
            .nav-links {
                display: none;
            }
        }
    </style>
</head>
<body>
    <!-- خلفية متحركة -->
    <div class="background-animation">
        <div class="circle"></div>
        <div class="circle"></div>
        <div class="circle"></div>
        <div class="circle"></div>
        <div class="circle"></div>
    </div>

    <!-- شريط التنقل -->
    <header>
        <nav>
            <a href="#" class="logo"><i class="fas fa-code"></i> محمد</a>
            <ul class="nav-links">
                <li><a href="#about">عنّي</a></li>
                <li><a href="#skills">المهارات</a></li>
                <li><a href="#projects">المشاريع</a></li>
                <li><a href="#contact">اتصل بي</a></li>
            </ul>
        </nav>
    </header>

    <!-- قسم البطل -->
    <section class="hero">
        <div class="hero-content">
            <h1>مرحباً، أنا محمد</h1>
            <p>مطور <span class="typewriter">Full Stack & متخصص مساحة جوية</span></p>
            <p>خريج جامعة النجاح الوطنية | أسعى لتحقيق التميز في البرمجة والمساحة الجوية</p>
            <a href="#contact" class="btn">تواصل معي <i class="fas fa-arrow-left"></i></a>
        </div>
    </section>

    <!-- قسم عني -->
    <section id="about" class="about">
        <h2 class="section-title">عنّي</h2>
        <div class="about-content">
            <div class="about-text fade-in">
                <h3>من أنا؟</h3>
                <p>أنا محمد، خريج جامعة النجاح الوطنية بتخصص المساحة والمساحة الجوية. لدي شغف كبير بتطوير الويب والتقنيات الحديثة، وأعمل حالياً على تطوير مهاراتي في مجال Full Stack Development.</p>
                <p>أجمع بين معرفتي التقنية في البرمجة وتخصصي في المساحة الجوية لإنشاء حلول مبتكرة تجمع بين العالمين.</p>
                <p>طموحي هو المساهمة في تطوير تطبيقات تستخدم تقنيات المساحة الجوية والاستشعار عن بعد لخدمة المجتمع وتطويره.</p>
            </div>
            <div class="about-skills fade-in">
                <h3>مهاراتي</h3>
                <div class="skills-container">
                    <div class="skill">
                        <i class="fab fa-html5"></i>
                        <h4>HTML5</h4>
                    </div>
                    <div class="skill">
                        <i class="fab fa-css3-alt"></i>
                        <h4>CSS3</h4>
                    </div>
                    <div class="skill">
                        <i class="fab fa-js"></i>
                        <h4>JavaScript</h4>
                    </div>
                    <div class="skill">
                        <i class="fab fa-react"></i>
                        <h4>React</h4>
                    </div>
                    <div class="skill">
                        <i class="fas fa-database"></i>
                        <h4>قواعد البيانات</h4>
                    </div>
                    <div class="skill">
                        <i class="fas fa-satellite"></i>
                        <h4>المساحة الجوية</h4>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- قسم المشاريع -->
    <section id="projects" class="projects">
        <h2 class="section-title">مشاريعي</h2>
        <div class="projects-grid">
            <div class="project-card fade-in">
                <div class="project-img">
                    <i class="fas fa-map-marked-alt"></i>
                </div>
                <div class="project-content">
                    <h3>نظام الخرائط التفاعلية</h3>
                    <p>نظام ويب تفاعلي للخرائط يجمع بين تقنيات الويب والمساحة الجوية</p>
                    <a href="#" class="btn">عرض المشروع</a>
                </div>
            </div>
            <div class="project-card fade-in">
                <div class="project-img">
                    <i class="fas drone fa-drone"></i>
                </div>
                <div class="project-content">
                    <h3>تحليل بيانات الطائرات بدون طيار</h3>
                    <p>تطبيق لتحليل ومعالجة البيانات الجوية المستخلصة من الطائرات بدون طيار</p>
                    <a href="#" class="btn">عرض المشروع</a>
                </div>
            </div>
            <div class="project-card fade-in">
                <div class="project-img">
                    <i class="fas fa-globe"></i>
                </div>
                <div class="project-content">
                    <h3>منصة GIS متكاملة</h3>
                    <p>منصة نظم المعلومات الجغرافية على الويب مع واجهة مستخدم تفاعلية</p>
                    <a href="#" class="btn">عرض المشروع</a>
                </div>
            </div>
        </div>
    </section>

    <!-- قسم الاتصال -->
    <section id="contact" class="contact">
        <h2 class="section-title">اتصل بي</h2>
        <div class="contact-content">
            <div class="contact-info">
                <div class="contact-item">
                    <i class="fas fa-envelope"></i>
                    <div>
                        <h3>البريد الإلكتروني</h3>
                        <p>mohamed@example.com</p>
                    </div>
                </div>
                <div class="contact-item">
                    <i class="fas fa-phone"></i>
                    <div>
                        <h3>الهاتف</h3>
                        <p>+970 599 000 000</p>
                    </div>
                </div>
                <div class="contact-item">
                    <i class="fas fa-map-marker-alt"></i>
                    <div>
                        <h3>الموقع</h3>
                        <p>فلسطين - نابلس</p>
                    </div>
                </div>
                <div class="social-links">
                    <a href="#"><i class="fab fa-github"></i></a>
                    <a href="#"><i class="fab fa-linkedin"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                </div>
            </div>
            <div class="contact-form fade-in">
                <form>
                    <input type="text" placeholder="اسمك" required>
                    <input type="email" placeholder="بريدك الإلكتروني" required>
                    <textarea placeholder="رسالتك" rows="5" required></textarea>
                    <button type="submit" class="btn">إرسال الرسالة <i class="fas fa-paper-plane"></i></button>
                </form>
            </div>
        </div>
    </section>

    <script>
        // تأثير التمرير للعناصر
        document.addEventListener('DOMContentLoaded', function() {
            const fadeElements = document.querySelectorAll('.fade-in');
            
            function checkFade() {
                fadeElements.forEach(element => {
                    const elementTop = element.getBoundingClientRect().top;
                    const elementBottom = element.getBoundingClientRect().bottom;
                    const isVisible = (elementTop < window.innerHeight - 100) && (elementBottom > 0);
                    
                    if (isVisible) {
                        element.classList.add('visible');
                    }
                });
            }
            
            // التحقق عند التحميل وعند التمرير
            checkFade();
            window.addEventListener('scroll', checkFade);
            
            // تأثير الكتابة
            const typewriter = document.querySelector('.typewriter');
            const text = typewriter.textContent;
            typewriter.textContent = '';
            let i = 0;
            
            function type() {
                if (i < text.length) {
                    typewriter.textContent += text.charAt(i);
                    i++;
                    setTimeout(type, 100);
                }
            }
            
            setTimeout(type, 1000);
        });
    </script>
</body>
</html>
