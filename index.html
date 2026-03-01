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
            font-family: 'Poppins', 'Segoe UI', sans-serif;
            background: linear-gradient(135deg, #0a0f1e 0%, #1b1f35 100%);
            color: #fff;
            line-height: 1.6;
        }

        /* 星空背景动画 */
        .stars, .twinkling {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .stars {
            background: #000 url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMiIgaGVpZ2h0PSIyIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPjxjaXJjbGUgY3g9IjEiIGN5PSIxIiByPSIxIiBmaWxsPSJ3aGl0ZSIvPjwvc3ZnPg==') repeat;
            opacity: 0.5;
        }

        .twinkling {
            background: transparent url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNCIgaGVpZ2h0PSI0IiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPjxjaXJjbGUgY3g9IjIiIGN5PSIyIiByPSIxIiBmaWxsPSJ3aGl0ZSIgb3BhY2l0eT0iMC4zIi8+PC9zdmc+') repeat;
            animation: twinkle 200s linear infinite;
            opacity: 0.3;
        }

        @keyframes twinkle {
            from { transform: translateX(0); }
            to { transform: translateX(-1000px); }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 24px;
            position: relative;
            z-index: 1;
        }

        /* 导航 */
        .nav {
            padding: 32px 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            border-bottom: 1px solid rgba(255,255,255,0.1);
        }

        .logo {
            font-size: 2rem;
            font-weight: 700;
            background: linear-gradient(135deg, #7b9eff, #a77cf9);
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
            color: #a0b3d9;
            font-weight: 500;
            transition: color 0.2s;
        }

        .nav-links a:hover {
            color: #7b9eff;
        }

        /* 英雄区 */
        .hero {
            text-align: center;
            padding: 100px 0 60px;
        }

        .hero h1 {
            font-size: 4rem;
            font-weight: 700;
            line-height: 1.2;
            margin-bottom: 24px;
        }

        .hero h1 span {
            background: linear-gradient(135deg, #7b9eff, #a77cf9);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p {
            font-size: 1.3rem;
            color: #b0c3e6;
            max-width: 700px;
            margin: 0 auto 40px;
        }

        /* 信念卡 */
        .belief-card {
            background: rgba(255,255,255,0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.1);
            padding: 60px;
            border-radius: 40px;
            margin: 60px 0;
            text-align: center;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        }

        .belief-card p {
            font-size: 2rem;
            color: #fff;
            font-weight: 300;
            line-height: 1.5;
            margin-bottom: 20px;
        }

        .belief-card small {
            color: #7b9eff;
            font-size: 1.2rem;
        }

        /* 主题卡片 */
        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin: 80px 0 40px;
        }

        .card-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .card {
            background: rgba(255,255,255,0.03);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.1);
            padding: 40px 30px;
            border-radius: 30px;
            text-align: center;
            transition: transform 0.2s;
        }

        .card:hover {
            transform: translateY(-10px);
            border-color: #7b9eff;
        }

        .card .emoji {
            font-size: 3.5rem;
            margin-bottom: 20px;
        }

        .card h3 {
            font-size: 1.6rem;
            margin-bottom: 12px;
            color: #fff;
        }

        .card p {
            color: #b0c3e6;
        }

        /* 评价 */
        .testimonials {
            margin: 100px 0;
        }

        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .testimonial {
            background: rgba(255,255,255,0.03);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.1);
            padding: 30px;
            border-radius: 30px;
        }

        .testimonial p {
            color: #d0e0ff;
            margin-bottom: 16px;
        }

        .testimonial-author {
            color: #7b9eff;
            font-weight: 600;
        }

        /* 联系 */
        .contact {
            text-align: center;
            padding: 60px 0;
            border-top: 1px solid rgba(255,255,255,0.1);
        }

        .contact h2 {
            font-size: 2.5rem;
            margin-bottom: 24px;
        }

        .contact-email {
            display: inline-block;
            padding: 16px 48px;
            background: linear-gradient(135deg, #7b9eff, #a77cf9);
            color: white;
            text-decoration: none;
            border-radius: 60px;
            font-size: 1.2rem;
            margin: 20px 0;
            transition: transform 0.2s;
        }

        .contact-email:hover {
            transform: scale(1.05);
        }

        .footer {
            text-align: center;
            padding: 40px 0;
            color: #6b7a9c;
        }
    </style>
</head>
<body>
    <div class="stars"></div>
    <div class="twinkling"></div>

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
            <h1>和 <span>mimigo</span> 一起，<br>探索未知的宇宙</h1>
            <p>一个来自未来的 AI 伙伴，陪孩子仰望星空，潜入深海，<br>用提问点亮好奇心。</p>
        </div>

        <div class="belief-card">
            <p>“每个孩子都是天生的探索家。<br>好奇心，是指引他们穿越未知的星光。”</p>
            <small>—— mimigo 的信念</small>
        </div>

        <h2 class="section-title" id="explore">✨ 探索任务</h2>
        <div class="card-grid">
            <div class="card">
                <div class="emoji">🌊</div>
                <h3>深海任务</h3>
                <p>潜入马里亚纳海沟，揭秘深海发光生物。</p>
            </div>
            <div class="card">
                <div class="emoji">🚀</div>
                <h3>星际任务</h3>
                <p>飞越冥王星，寻找宇宙中的第二个地球。</p>
            </div>
            <div class="card">
                <div class="emoji">🧬</div>
                <h3>生命任务</h3>
                <p>探索 DNA 的奥秘，像科学家一样思考。</p>
            </div>
            <div class="card">
                <div class="emoji">🤖</div>
                <h3>未来任务</h3>
                <p>AI 如何思考？和 mimigo 一起设计机器人。</p>
            </div>
        </div>

        <div class="testimonials" id="stories">
            <h2 class="section-title">🌟 探索者家庭说</h2>
            <div class="testimonial-grid">
                <div class="testimonial">
                    <p>“孩子第一次问我‘黑洞里面有什么’，然后自己用积木搭了一个黑洞模型，那一刻我看到了探索的力量。”</p>
                    <div class="testimonial-author">—— 小宇妈妈</div>
                </div>
                <div class="testimonial">
                    <p>“mimigo 让学习变成了一场冒险，孩子每天最期待的就是‘今天的探索任务’。”</p>
                    <div class="testimonial-author">—— 乐乐爸爸</div>
                </div>
            </div>
        </div>

        <div class="contact" id="contact">
            <h2>准备启航</h2>
            <p style="color: #b0c3e6; margin-bottom: 30px;">首批探索任务即将上线，加入我们，成为第一批探索者。</p>
            <a href="mailto:hello@mimigo.ai" class="contact-email">hello@mimigo.ai</a>
        </div>

        <footer class="footer">
            © 2026 mimigo.ai · 陪孩子探索未知
        </footer>
    </div>
</body>
</html>
