<h1 align="center">❤一个不会被拒绝的表白的网页❤</h1>
<p>随便做了一个告白的网页（还是无法拒绝的那种），不许骗人家妹妹，哒咩！感情到了才可以表白哦~</p>
<img src="https://github.com/user-attachments/assets/a1d5ad21-00d0-4c97-9885-63c27573666f" alt="告白网页截图">

<p>不可以是不可以按的，不许拒绝我，按了它就会跑到其他地方去</p>
<img src="https://github.com/user-attachments/assets/79d9fbb4-123e-4876-91f7-5b92de0c9402" alt="按钮效果截图">
<p>爱心做了动效，还做了樱花落下的特效，是不是还挺唯美的~</p>
<p>可以用这个域名https://love0721.online/</p>
<p>这就是我们柚子厨的实力Ciallo～(∠・ω< )⌒★</p>

## 一级页面

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>可以成为我的恋人吗？</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #ffb7c5; /* 樱花粉色 */
            position: relative;
            overflow: hidden;
        }

        h1 {
            margin-bottom: 50px;
            color: #fff;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
        }

        .buttons {
            position: relative;
            display: flex;
            gap: 20px;
        }

        #yesButton {
            padding: 15px 30px;
            font-size: 18px;
            cursor: pointer;
            background-color: #ff6f61; /* 珊瑚粉色 */
            color: white;
            border: none;
            border-radius: 12px;
            z-index: 1;
            transition: all 0.4s cubic-bezier(0.28, 0.84, 0.42, 1);
            transform: scale(1);
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        #yesButton:active {
            transform: scale(0.95);
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        #noButton {
            padding: 15px 30px;
            font-size: 18px;
            cursor: pointer;
            background-color: #ff6f61; /* 珊瑚粉色 */
            color: white;
            border: none;
            border-radius: 8px;
            position: relative;
            transition: transform 0.3s ease;
        }

        /* 樱花飘落动画 */
        .sakura {
            position: absolute;
            top: -50px;
            animation: fall linear infinite;
            color: #fff;
            font-size: 24px;
            user-select: none;
        }

        @keyframes fall {
            to {
                transform: translateY(100vh);
            }
        }
    </style>
</head>
<body>
    <h1>可以成为我的恋人吗？</h1>
    <div class="buttons">
        <button id="yesButton">可以</button> 
        <button id="noButton">不可以</button> 
    </div>

    <!-- 樱花飘落效果 -->
    <div class="sakura" style="left: 10%; animation-duration: 8s;">🌸</div>
    <div class="sakura" style="left: 20%; animation-duration: 10s;">🌸</div>
    <div class="sakura" style="left: 30%; animation-duration: 12s;">🌸</div>
    <div class="sakura" style="left: 40%; animation-duration: 9s;">🌸</div>
    <div class="sakura" style="left: 50%; animation-duration: 11s;">🌸</div>
    <div class="sakura" style="left: 60%; animation-duration: 7s;">🌸</div>
    <div class="sakura" style="left: 70%; animation-duration: 13s;">🌸</div>
    <div class="sakura" style="left: 80%; animation-duration: 8s;">🌸</div>
    <div class="sakura" style="left: 90%; animation-duration: 10s;">🌸</div>

    <script>
        const noButton = document.getElementById('noButton');
        const yesButton = document.getElementById('yesButton');
        const h1 = document.querySelector('h1');

        // 获取按钮的宽度和高度
        const buttonWidth = noButton.offsetWidth;
        const buttonHeight = noButton.offsetHeight;

        // 获取“可以”按钮的位置信息
        const yesButtonRect = yesButton.getBoundingClientRect();

        // 获取 <h1> 标签的位置信息
        const h1Rect = h1.getBoundingClientRect();

        // 随机位置函数，确保按钮在可视区域内且不与“可以”按钮或 <h1> 标签重叠
        function getRandomPosition() {
            const maxX = window.innerWidth - buttonWidth;
            const maxY = window.innerHeight - buttonHeight;

            let x, y;
            let attempts = 0; // 防止无限循环

            do {
                x = Math.random() * maxX;
                y = Math.random() * maxY;
                attempts++;
            } while (
                // 检查是否与“可以”按钮重叠
                (x < yesButtonRect.right &&
                 x + buttonWidth > yesButtonRect.left &&
                 y < yesButtonRect.bottom &&
                 y + buttonHeight > yesButtonRect.top) ||
                // 检查是否与 <h1> 标签重叠
                (x < h1Rect.right &&
                 x + buttonWidth > h1Rect.left &&
                 y < h1Rect.bottom &&
                 y + buttonHeight > h1Rect.top) &&
                attempts < 100 // 最多尝试 100 次
            );

            return { x, y };
        }

        // 点击“不可以”按钮时触发
        noButton.addEventListener('click', () => {
            // 获取随机位置
            const { x, y } = getRandomPosition();

            // 移动按钮到新位置
            noButton.style.position = 'fixed'; // 使用 fixed 定位
            noButton.style.left = `${x}px`;
            noButton.style.top = `${y}px`;
        });

        // 确认按钮事件：跳转到二级页面
        yesButton.addEventListener('click', () => {
            window.location.href = 'success.html';
        });
    </script>
</body>
</html>
```
## 二级页面

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>太好了！</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #ffb7c5; /* 樱花粉色 */
            color: #fff;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        h1 {
            font-size: 3rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
            margin-bottom: 20px;
        }

        /* 红色爱心样式 */
        .heart {
            color: #ff0000; /* 红色 */
            font-size: 3rem;
            display: inline-block;
            animation: beat 1s infinite;
        }

        @keyframes beat {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.2);
            }
        }

        /* 樱花飘落动画 */
        .sakura {
            position: absolute;
            top: -50px;
            animation: fall linear infinite;
            color: #fff;
            font-size: 24px;
            user-select: none;
        }

        @keyframes fall {
            to {
                transform: translateY(100vh);
            }
        }
    </style>
</head>
<body>
    <h1>
        <span class="heart">❤</span> 太好了，喜欢你!! ( >᎑<)⌒ <span class="heart">❤</span>
    </h1>

    <!-- 樱花飘落效果 -->
    <div class="sakura" style="left: 10%; animation-duration: 8s;">🌸</div>
    <div class="sakura" style="left: 20%; animation-duration: 10s;">🌸</div>
    <div class="sakura" style="left: 30%; animation-duration: 12s;">🌸</div>
    <div class="sakura" style="left: 40%; animation-duration: 9s;">🌸</div>
    <div class="sakura" style="left: 50%; animation-duration: 11s;">🌸</div>
    <div class="sakura" style="left: 60%; animation-duration: 7s;">🌸</div>
    <div class="sakura" style="left: 70%; animation-duration: 13s;">🌸</div>
    <div class="sakura" style="left: 80%; animation-duration: 8s;">🌸</div>
    <div class="sakura" style="left: 90%; animation-duration: 10s;">🌸</div>

    <script>
        // 检测页面是否是通过刷新加载的
        if (performance.navigation.type === 1) { // 1 表示页面是通过刷新加载的
            window.location.href = 'index.html'; // 跳转到一级页面
        }
    </script>
</body>
</html>
```
#### 文本和樱花动效都是可以修改的，你也可以按照自己的喜欢随意添加，祝愿表白成功~
我还做了另一个动效的版本index1.html,一开始我挺喜欢这种躲避的，但是发现在手机上点按就没啥效果了，如果喜欢的话也可以重新指向，其他效果暂时还没想出来，诶嘿~
