<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>mimigo · 探索者 AI</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Quicksand', 'Segoe UI', sans-serif;
            background: #fdf9f2;
            color: #3a2c3b;
            line-height: 1.6;
        }

        /* 装饰性背景 */
        .bg-dots {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: radial-gradient(#e0d6cd 1px, transparent 1px);
            background-size: 30px 30px;
            opacity: 0.4;
            z-index: -1;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 24px;
        }

        /* 导航 */
        .nav {
            padding: 32px 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .logo {
            font-size: 2rem;
            font-weight: 700;
            background: linear-gradient(135deg, #f9a8d4, #b8a1d9);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            gap: 32px;
        }

        .nav-links a {
            text-decoration: none;
            color: #5e4b5e;
            font-weight: 500;
            transition: color 0.2s;
            font-size: 1.1rem;
        }

        .nav-links a:hover {
            color: #d88c9a;
        }

        /* 英雄区 */
        .hero {
            display: flex;
            align-items: center;
            gap: 60px;
            margin: 40px 0 80px;
            flex-wrap: wrap;
        }

        .hero-content {
            flex: 1;
            min-width: 300px;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 700;
            line-height: 1.2;
            margin-bottom: 24px;
            color: #3a2c3b;
        }

        .hero h1 span {
            background: linear-gradient(135deg, #f9a8d4, #b8a1d9);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p {
            font-size: 1.3rem;
            color: #6b5e6b;
            margin-bottom: 32px;
        }

        .hero-illustration {
            flex: 1;
            min-width: 300px;
            text-align: center;
        }

        .hero-illustration svg {
            max-width: 100%;
            height: auto;
        }

        /* 信念卡片 */
        .belief-card {
            background: white;
            padding: 40px;
            border-radius: 60px 60px 60px 20px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.05);
            margin: 60px 0;
            border: 2px solid #f3e5de;
            position: relative;
        }

        .belief-card::before {
            content: "“";
            font-size: 8rem;
            color: #f9a8d4;
            opacity: 0.3;
            position: absolute;
            top: -20px;
            left: 20px;
            font-family: serif;
        }

        .belief-card p {
            font-size: 2rem;
            font-weight: 400;
            color: #4a3b4a;
            line-height: 1.4;
            text-align: center;
            margin-bottom: 16px;
        }

        .belief-card small {
            display: block;
            text-align: right;
            color: #b8a1d9;
            font-size: 1.2rem;
        }

        /* 探索卡片网格 */
        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin: 80px 0 40px;
            color: #3a2c3b;
        }

        .card-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }

        .card {
            background: white;
            padding: 36px 24px;
            border-radius: 40px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.03);
            text-align: center;
            transition: transform 0.2s;
            border: 2px solid #f3e5de;
        }

        .card:hover {
            transform: translateY(-8px);
        }

        .card-emoji {
            font-size: 3.5rem;
            margin-bottom: 20px;
        }

        .card h3 {
            font-size: 1.6rem;
            margin-bottom: 12px;
            color: #4a3b4a;
        }

        .card p {
            color: #7a6b7a;
        }

        /* 家长评价 */
        .testimonials {
            background: #f8efe8;
            padding: 60px 0;
            border-radius: 100px 100px 0 0;
            margin: 80px 0 0;
        }

        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }

        .testimonial {
            background: white;
            padding: 32px;
            border-radius: 40px;
            border: 2px solid #e8d9d1;
        }

        .testimonial p {
            font-size: 1.1rem;
            color: #4a3b4a;
            margin-bottom: 16px;
        }

        .testimonial-author {
            color: #d88c9a;
            font-weight: 600;
        }

        /* 联系区 */
        .contact {
            text-align: center;
            padding: 60px 0;
        }

        .contact h2 {
            font-size: 2.5rem;
            margin-bottom: 24px;
        }

        .contact-email {
            font-size: 1.5rem;
            background: white;
            padding: 16px 40px;
            display: inline-block;
            border-radius: 60px;
            border: 2px solid #f3e5de;
            color: #d88c9a;
            text-decoration: none;
            margin: 20px 0;
        }

        /* 页脚 */
        .footer {
            text-align: center;
            padding: 40px 0;
            color: #9a8b9a;
            border-top: 2px solid #f3e5de;
        }

        /* 响应式 */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            .belief-card p {
                font-size: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <div class="bg-dots"></div>
    
    <div class="container">
        <nav class="nav">
            <a href="/" class="logo">mimigo.ai</a>
            <div class="nav-links">
                <a href="#explore">探索</a>
                <a href="#stories">故事</a>
                <a href="#contact">联系</a>
            </div>
        </nav>

        <div class="hero">
            <div class="hero-content">
                <h1>和 <span>mimigo</span> 一起，<br>探索世界的奇妙</h1>
                <p>一个温暖的 AI 伙伴，专为 6–15 岁孩子设计。<br>我们不直接给答案，而是用启发式提问陪孩子成长。</p>
            </div>
            <div class="hero-illustration">
                <svg width="300" height="300" viewBox="0 0 300 300">
                    <circle cx="150" cy="150" r="120" fill="#f9e2d7" />
                    <circle cx="120" cy="120" r="15" fill="#f9a8d4" />
                    <circle cx="180" cy="120" r="15" fill="#f9a8d4" />
                    <path d="M110 180 Q150 220,190 180" stroke="#b8a1d9" stroke-width="8" fill="none" stroke-linecap="round" />
                    <circle cx="150" cy="180" r="10" fill="#d88c9a" />
                </svg>
            </div>
        </div>

        <div class="belief-card">
            <p>每个孩子天生都是探索家。<br>好奇心，是最好的老师。</p>
            <small>—— mimigo 的信念</small>
        </div>

        <h2 class="section-title" id="explore">✨ 探索主题</h2>
        <div class="card-grid">
            <div class="card">
                <div class="card-emoji">🌊</div>
                <h3>海洋奥秘</h3>
                <p>为什么海水是咸的？深海里有什么？和 mimigo 一起潜入蓝色星球。</p>
            </div>
            <div class="card">
                <div class="card-emoji">🔭</div>
                <h3>仰望星空</h3>
                <p>星星为什么会眨眼？黑洞是什么？满足每个孩子对宇宙的好奇。</p>
            </div>
            <div class="card">
                <div class="card-emoji">🤔</div>
                <h3>启发提问</h3>
                <p>遇到难题时，先问“你觉得第一步该做什么？”培养独立思考的习惯。</p>
            </div>
            <div class="card">
                <div class="card-emoji">📚</div>
                <h3>爱上学习</h3>
                <p>让学习像寻宝一样有趣，在探索中收获知识和自信。</p>
            </div>
        </div>

        <div class="testimonials" id="stories">
            <div class="container">
                <h2 class="section-title">👪 家长说</h2>
                <div class="testimonial-grid">
                    <div class="testimonial">
                        <p>“孩子以前遇到难题就直接放弃，现在会自己先想想，还会跑来跟我说‘妈妈，mimigo 让我先找找题目里的线索’。”</p>
                        <div class="testimonial-author">—— 小宇妈妈</div>
                    </div>
                    <div class="testimonial">
                        <p>“mimigo 就像孩子的一个知识朋友，陪他聊恐龙、聊太空，我明显感觉他提问变多了。”</p>
                        <div class="testimonial-author">—— 乐乐爸爸</div>
                    </div>
                </div>
            </div>
        </div>

        <div class="contact" id="contact">
            <h2>🚀 即将上线</h2>
            <p style="color: #6b5e6b; max-width: 500px; margin: 0 auto 24px;">我们正在精心准备第一批探索主题，很快就会和你见面。</p>
            <a href="mailto:hello@mimigo.ai" class="contact-email">📧 hello@mimigo.ai</a>
        </div>

        <footer class="footer">
            © 2026 mimigo.ai · 陪孩子发现世界的奇妙
        </footer>
    </div>
</body>
</html>
