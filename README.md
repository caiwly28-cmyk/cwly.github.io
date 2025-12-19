# cwly.github.io
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>易烊千玺应援投票页</title>
    <style>
        /* 全局样式 */
        body {
            font-family: 'Microsoft YaHei', sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }

        /* 投票卡片 */
        .vote-card {
            background: white;
            width: 90%;
            max-width: 400px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            overflow: hidden;
            text-align: center;
            padding-bottom: 30px;
        }

        /* 顶部横幅 - 易烊千玺应援红 */
        .banner {
            background: linear-gradient(135deg, #d71920, #8b0000);
            height: 120px;
            position: relative;
        }

        /* 头像 */
        .avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            border: 5px solid white;
            margin-top: -60px;
            object-fit: cover;
            position: relative;
            background-color: #eee;
        }

        .name {
            font-size: 24px;
            font-weight: bold;
            color: #333;
            margin: 10px 0 5px;
        }

        .desc {
            font-size: 14px;
            color: #777;
            padding: 0 20px;
            line-height: 1.6;
        }

        /* 票数显示 */
        .vote-count {
            margin: 25px 0;
        }

        .number {
            font-size: 36px;
            font-weight: 800;
            color: #d71920;
            display: block;
        }

        .label {
            font-size: 14px;
            color: #999;
        }

        /* 进度条 */
        .progress-container {
            width: 80%;
            height: 10px;
            background: #eee;
            border-radius: 10px;
            margin: 0 auto 20px;
            overflow: hidden;
        }

        .progress-bar {
            width: 65%; /* 初始进度 */
            height: 100%;
            background: #d71920;
            transition: width 0.3s ease;
        }

        /* 投票按钮 */
        .vote-btn {
            background: #d71920;
            color: white;
            border: none;
            padding: 12px 50px;
            font-size: 18px;
            border-radius: 30px;
            cursor: pointer;
            transition: transform 0.2s, background 0.3s;
            box-shadow: 0 4px 15px rgba(215, 25, 32, 0.3);
        }

        .vote-btn:hover {
            background: #b3151a;
        }

        .vote-btn:active {
            transform: scale(0.95);
        }

        /* 底部语 */
        .footer {
            margin-top: 20px;
            font-size: 12px;
            color: #bbb;
        }

        /* 动画反馈 */
        @keyframes countUp {
            from { transform: translateY(10px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
        .pop { animation: countUp 0.3s ease-out; }
    </style>
</head>
<body>

<div class="vote-card">
    <div class="banner"></div>
    <!-- 替换此处的src为易烊千玺的实际图片链接 -->
    <img src="https://via.placeholder.com/150/d71920/ffffff?text=Jackson+Yee" alt="易烊千玺" class="avatar">
    
    <div class="name">易烊千玺</div>
    <p class="desc">青年演员、歌手。代表作《少年的你》、《送你一朵小红花》、《满江红》。</p>

    <div class="vote-count">
        <span class="label">当前人气值</span>
        <span class="number" id="voteNum">1128</span>
    </div>

    <div class="progress-container">
        <div class="progress-bar" id="progressBar"></div>
    </div>

    <button class="vote-btn" onclick="castVote()">投他一票</button>

    <div class="footer">一人一天限投一票 | 红色是永远的应援色</div>
</div>

<script>
    // 简单的投票逻辑
    let count = 1128;
    let hasVoted = false;

    function castVote() {
        if (hasVoted) {
            alert("今日已投票，明天再来为千玺助力吧！");
            return;
        }

        count++;
        hasVoted = true;

        // 更新数字
        const numElement = document.getElementById('voteNum');
        numElement.innerText = count;
        numElement.classList.add('pop');

        // 更新进度条（模拟效果）
        const bar = document.getElementById('progressBar');
        let currentWidth = 65;
        bar.style.width = (currentWidth + 1) + "%";

        // 按钮变色
        const btn = document.querySelector('.vote-btn');
        btn.innerText = "已投票";
        btn.style.background = "#999";
        btn.style.boxShadow = "none";

        alert("投票成功！感谢为易烊千玺应援！");
    }
</script>

</body>
</html>
