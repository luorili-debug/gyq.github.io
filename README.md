[gyq.html](https://github.com/user-attachments/files/23329363/gyq.html)
<!DOCTYPE html>
<html>

<head>
    <meta charset="UTF-8" <title>To 阿妍儿</title>
    <style>
        .tip-window {
            position: fixed;
            width: 250px;
            height: 180px;
            background-color: lavender;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: 'Microsoft YaHei', sans-serif;
            font-size: 16px;
            text-align: center;
            box-shadow: 0 3px 6px rgba(0, 0, 0, 0.2);
            z-index: 1000;
        }
    </style>
</head>

<body>
    <script>
        const tips = ["多吃水果少熬夜", "记得多喝水", "天冷了，注意保暖", "每天都要保持好心情", "期待下一次见面", "好好爱自己", "很喜欢你"];
        const bgColors = ["lavender", "plum", "coral", "lightpink", "skyblue", "lightgreen", "lightyellow", "bisque", "aquamarine", "mistyrose", "honeydew"];
        function createTipWindow() {
            const windowElement = document.createElement('div');
            windowElement.className = 'tip-window';

            // 随机位置
            const x = Math.random() * (window.innerWidth - 250);
            const y = Math.random() * (window.innerHeight - 180);

            // 随机内容和背景
            const tip = tips[Math.floor(Math.random() * tips.length)];
            const bgColor = bgColors[Math.floor(Math.random() * bgColors.length)];

            windowElement.textContent = tip;
            windowElement.style.backgroundColor = bgColor;
            windowElement.style.left = x + 'px';
            windowElement.style.top = y + 'px';

            document.body.appendChild(windowElement);

            // 点击关闭单个窗口
            windowElement.addEventListener('click', function () {
                this.remove();
            });
        }

        // 创建多个窗口
        for (let i = 0; i < 60; i++) {
            setTimeout(createTipWindow, i * 100);
        }

        // 按空格关闭所有窗口
        document.addEventListener('keydown', function (event) {
            if (event.code === 'Space') {
                const windows = document.querySelectorAll('.tip-window');
                windows.forEach(window => window.remove());
            }
        });
    </script>
</body>

</html>
