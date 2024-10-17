<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>个人博客</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css"> <!-- Font Awesome 图标 -->
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #FF69B4, #FF1493, #8A2BE2, #FFA500, #FFFF00); /* 高级糖果色渐变背景 */
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: flex-start;
        }

        .navbar {
            background-color: rgba(255, 255, 255, 0.9); /* 半透明背景 */
            padding: 10px 20px;
            display: flex;
            justify-content: space-around;
            align-items: center;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            flex-wrap: wrap; /* 允许换行以适应小屏幕 */
        }

        .navbar a {
            text-decoration: none;
            color: #333;
            margin: 5px 10px;
            font-weight: bold;
            display: flex;
            align-items: center;
        }

        .navbar a i {
            margin-right: 5px; /* 图标和文本之间的间距 */
        }

        .container {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .content {
            background-color: rgba(255, 255, 255, 0.9); /* 半透明背景 */
            padding: 250px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            max-width: 800px;
            width: 100%;
            margin: 20px 0; /* 增加内容区域之间的间距 */
            text-align: center;
        }

        .content h1, .content p {
            color: #333;
        }

        /* 每个部分的内容样式 */
        #home-content, #letter-content, #image-wall-content, #message-board-content {
            display: none; /* 默认隐藏所有内容 */
        }

        #home-content.active, #letter-content.active, #image-wall-content.active, #message-board-content.active {
            display: block; /* 点击导航项时显示对应内容 */
        }

        .content textarea {
            width: 100%;
            height: 150px;
            padding: 10px;
            border-radius: 8px;
            border: 1px solid #ccc;
            margin-top: 20px;
            font-size: 16px;
            resize: none; /* 禁止缩放 */
        }
    </style>
</head>
<body>
    <div class="navbar">
        <a href="#home-content"><i class="fas fa-home"></i>首页</a>
        <a href="#letter-content"><i class="fas fa-envelope"></i>写信</a>
        <a href="#image-wall-content"><i class="fas fa-images"></i>照片墙</a>
        <a href="#message-board-content"><i class="fas fa-comments"></i>留言板</a>
    </div>

    <div class="container">
        <div id="home-content" class="content active">
            <h1>欢迎来到你的世界</h1>
            <p>这里是我分享生活、工作和学习的地方。希望你在这里能找到有用的信息。</p>
            <p>想</p>
        </div>

        <div id="letter-content" class="content">
            <h1>写给我的信</h1>
            <p>请将你的想法和建议写在这里，我会认真阅读每一封信。</p>
            <textarea placeholder="在这里写下你的信..."></textarea>
        </div>

        <div id="image-wall-content" class="content">
            <h1>照片墙</h1>
            <p>这是我的照片墙，记录了我的生活点滴。</p>
            <div class="image-grid">
                <img src="image1.jpg" alt="Image 1" style="width: 100px; height: 100px; margin: 5px;">
                <img src="image2.jpg" alt="Image 2" style="width: 100px; height: 100px; margin: 5px;">
                <img src="image3.jpg" alt="Image 3" style="width: 100px; height: 100px; margin: 5px;">
                <!-- 可添加更多图片 -->
            </div>
        </div>

        <div id="message-board-content" class="content">
            <h1>留言板</h1>
            <p>欢迎在这里留下你的留言，我会尽快回复。</p>
            <textarea placeholder="在这里写下你的留言..."></textarea>
            <button style="margin-top: 10px;">提交留言</button>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const navLinks = document.querySelectorAll('.navbar a');
            const contents = document.querySelectorAll('.content');

            navLinks.forEach(link => {
                link.addEventListener('click', function(event) {
                    event.preventDefault();
                    const targetId = this.getAttribute('href').substring(1); // 获取链接的目标 ID（去掉 '#'）
                    const targetContent = document.getElementById(targetId + '-content');

                    // 隐藏所有内容
                    contents.forEach(content => {
                        content.style.display = 'none';
                    });

                    // 显示目标内容
                    if (targetContent) {
                        targetContent.style.display = 'block';
                        // 滚动到目标内容
                        targetContent.scrollIntoView({ behavior: 'smooth' });
                    }
                });
            });
        });
    </script>
</body>
</html>
