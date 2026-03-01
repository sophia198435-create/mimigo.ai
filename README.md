<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mimigo · 探索向导</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', 'PingFang SC', Roboto, 'Helvetica Neue', sans-serif;
            background-color: #0a0f1e;
            color: #fff;
            overflow-x: hidden;
            line-height: 1.6;
            min-height: 100vh;
            position: relative;
        }

        /* 星空背景层 */
        .stars, .twinkling, .clouds {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .stars {
            background: #0a0f1e url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMiIgaGVpZ2h0PSIyIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPjxjaXJjbGUgY3g9IjEiIGN5PSIxIiByPSIxIiBmaWxsPSIjZmZmIiBmaWxsLW9wYWNpdHk9IjAuMiIvPjwvc3ZnPg==') repeat;
            background-size: 2px 2px;
            animation: starPulse 8s infinite alternate;
        }

        @keyframes starPulse {
            0% { opacity: 0.6; }
            100% { opacity: 1; }
        }

        .twinkling {
            background: transparent url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNCIgaGVpZ2h0PSI0IiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPjxjaXJjbGUgY3g9IjIiIGN5PSIyIiByPSIxIiBmaWxsPSIjZmZmIiBmaWxsLW9wYWNpdHk9IjAuNiIvPjwvc3ZnPg==') repeat;
            background-size: 4px 4px;
            animation: twinkle 3s infinite;
        }

        @keyframes twinkle {
            0% { opacity: 0.3; }
            50% { opacity: 1; }
            100% { opacity: 0.3; }
        }

        .clouds {
            background: linear-gradient(125deg, #1a2f4e 0%, #0f1b2f 40%, transparent 80%);
            opacity: 0.3;
            mix-blend-mode: overlay;
            animation: drift 40s infinite linear;
        }

        @keyframes drift {
            0% { transform: translateX(0); }
            100% { transform: translateX(-10%); }
        }

        /* 主容器 */
        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 5vh 20px;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            position: relative;
            z-index: 2;
        }

        /* 标题大字 */
        .hero-title {
            font-size: clamp(2.8rem, 10vw, 5rem);
            font-weight: 800;
            letter-spacing: 2px;
            line-height: 1.2;
            margin-bottom: 0.8rem;
            background: linear-gradient(135deg, #fff 0%, #aaccff 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 10px 30px rgba(0,100,255,0.3);
            animation: fadeUp 1.2s ease-out;
        }

        /* 正文区域 */
        .hero-text {
            font-size: clamp(1.1rem, 3vw, 1.5rem);
            font-weight: 300;
            max-width: 700px;
            margin: 2rem auto 2.5rem;
            color: rgba(255,255,255,0.9);
            text-shadow: 0 2px 10px rgba(0,0,0,0.5);
            animation: fadeUp 1.2s 0.2s both;
        }

        .hero-text p {
            margin: 1.2rem 0;
        }

        .hero-text .highlight {
            font-size: 1.8rem;
            font-weight: 400;
            color: #ffd966;
            margin: 1.5rem 0;
        }

        /* 署名 */
        .signature {
            font-size: 1.2rem;
            font-weight: 400;
            color: #7aa5ff;
            margin-top: 1rem;
            margin-bottom: 2rem;
            letter-spacing: 2px;
            opacity: 0.8;
        }

        /* 按钮 */
        .btn {
            display: inline-block;
            padding: 1rem 2.8rem;
            margin: 0.5rem;
            font-size: 1.2rem;
            font-weight: 500;
            border-radius: 50px;
            text-decoration: none;
            transition: all 0.3s ease;
            border: 1px solid rgba(255,255,255,0.3);
            background: rgba(20,30,60,0.5);
            backdrop-filter: blur(8px);
            color: white;
            box-shadow: 0 8px 20px rgba(0,0,0,0.3);
            cursor: pointer;
        }

        .btn-primary {
            background: linear-gradient(145deg, #2b5a9c, #1a3f6e);
            border-color: #5f9eff;
            color: white;
        }

        .btn-primary:hover {
            background: linear-gradient(145deg, #346fc0, #23509c);
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(50,150,255,0.4);
            border-color: #a0c4ff;
        }

        .btn-outline:hover {
            background: rgba(255,255,255,0.1);
            transform: translateY(-3px);
            border-color: #fff;
        }

        .btn-group {
            margin: 2.5rem 0 3rem;
            animation: fadeUp 1.2s 0.4s both;
        }

        /* 社交链接 */
        .social-links {
            margin-top: 3rem;
            display: flex;
            gap: 1.2rem;
            justify-content: center;
            animation: fadeUp 1.2s 0.6s both;
        }

        .social-links a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 48px;
            height: 48px;
            background: rgba(255,255,255,0.05);
            backdrop-filter: blur(5px);
            border-radius: 50%;
            color: white;
            font-size: 1.5rem;
            transition: 0.3s;
            border: 1px solid rgba(255,255,255,0.2);
            text-decoration: none;
        }

        .social-links a:hover {
            background: #2b5a9c;
            transform: translateY(-5px) scale(1.1);
            border-color: #7aa5ff;
        }

        /* 底部小字 */
        .footer {
            margin-top: 4rem;
            font-size: 0.9rem;
            color: rgba(255,255,255,0.4);
            animation: fadeUp 1.2s 0.8s both;
        }

        @keyframes fadeUp {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* 流星划过效果（可选） */
        .shooting-star {
            position: fixed;
            top: 10%;
            left: -10%;
            width: 5px;
            height: 1px;
            background: linear-gradient(90deg, transparent, white, transparent);
            filter: blur(1px);
            opacity: 0;
            animation: shoot 10s infinite linear;
            z-index: 1;
        }

        @keyframes shoot {
            0% { left: -10%; top: 10%; opacity: 1; }
            20% { left: 110%; top: 30%; opacity: 0; }
            100% { opacity: 0; }
        }

        /* 响应式 */
        @media (max-width: 600px) {
            .hero-title {
                font-size: 2.4rem;
            }
            .hero-text {
                font-size: 1rem;
            }
            .btn {
                display: block;
                width: 80%;
                margin: 1rem auto;
            }
        }
    </style>
</head>
<body>
    <!-- 三层星空背景 -->
    <div class="stars"></div>
    <div class="twinkling"></div>
    <div class="clouds"></div>
    <!-- 流星效果（可选，点缀） -->
    <div class="shooting-star"></div>
    <div class="shooting-star" style="top: 30%; animation-delay: 3s;"></div>
    <div class="shooting-star" style="top: 60%; animation-delay: 6s;"></div>

    <div class="container">
        <!-- 主标题 -->
        <h1 class="hero-title">好奇心，是探索世界的起点。</h1>

        <!-- 正文内容 -->
        <div class="hero-text">
            <p>从深海的发光水母，到宇宙边缘的未知星系，<br>每一个“为什么”都在邀请你，向前迈出一步。</p>
            <p class="highlight">我是 Mimigo，<br>你的 AI 探索向导。</p>
            <p>我不替你寻找答案，<br>而是为你点亮前行的路：<br>让你看到问题背后的问题，<br>让你在知识的海洋里，找到属于自己的方向。</p>
            <p style="margin-top:2rem; font-size:1.4rem; font-weight:300;">世界很大，你的好奇刚好装得下它。</p>
        </div>

        <!-- 签名/呼唤 -->
        <div class="signature">—— 出发吧，探索者。</div>

        <!-- 行动按钮 -->
        <div class="btn-group">
            <button class="btn btn-primary" onclick="alert('探索之旅即将开启，敬请期待！')">开始探索</button>
            <a href="mailto:hello@mimigo.ai" class="btn btn-outline">联系向导</a>
        </div>

        <!-- 社交媒体图标（可自定义链接） -->
        <div class="social-links">
            <a href="#" title="微博">📘</a>
            <a href="#" title="微信">💬</a>
            <a href="#" title="GitHub">🐙</a>
            <a href="#" title="邮件">✉️</a>
        </div>

        <!-- 页脚 -->
        <div class="footer">
            © 2026 Mimigo · 探索无界
        </div>
    </div>

    <!-- 简单脚本（目前只有alert，可留空） -->
    <script>
        // 如果需要后续添加更多交互，可在此编写
    </script>
</body>
</html>
