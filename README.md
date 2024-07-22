<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lucky Wheel</title>
    <style>
        #wheel {
            width: 300px;
            height: 300px;
            border: 10px solid #333;
            border-radius: 50%;
            position: relative;
            overflow: hidden;
        }
        #wheel div {
            width: 100%;
            height: 100%;
            position: absolute;
            transform-origin: 50% 50%;
        }
        .segment {
            width: 50%;
            height: 50%;
            background-color: #f39c12;
            transform-origin: 100% 100%;
        }
        #spinButton {
            margin-top: 20px;
        }
    </style>
</head>
<body>

<div id="wheel">
    <div class="segment" style="transform: rotate(0deg);"></div>
    <div class="segment" style="transform: rotate(45deg);"></div>
    <div class="segment" style="transform: rotate(90deg);"></div>
    <div class="segment" style="transform: rotate(135deg);"></div>
    <div class="segment" style="transform: rotate(180deg);"></div>
    <div class="segment" style="transform: rotate(225deg);"></div>
    <div class="segment" style="transform: rotate(270deg);"></div>
    <div class="segment" style="transform: rotate(315deg);"></div>
</div>
<button id="spinButton">Spin!</button>

<script>
    const wheel = document.getElementById('wheel');
    const spinButton = document.getElementById('spinButton');

    spinButton.addEventListener('click', () => {
        const randomSpin = Math.floor(Math.random() * 3600);
        wheel.style.transition = 'transform 4s ease-out';
        wheel.style.transform = `rotate(${randomSpin}deg)`;
    });
</script>

</body>
</html>
