<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>Chúc mừng sinh nhật ✨</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@400;600&display=swap');
    html, body {
      margin: 0;
      padding: 0;
      background: #000;
      overflow: hidden;
      height: 100vh;
      width: 100vw;
      font-family: 'Quicksand', sans-serif;
    }
    .moon-icon {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      font-size: 80px;
      color: gold;
      text-shadow: 0 0 12px gold, 0 0 24px yellow;
      z-index: 3;
      animation: glow 3s ease-in-out infinite alternate;
      pointer-events: none;
    }
    @keyframes glow {
      from { text-shadow: 0 0 10px gold; }
      to { text-shadow: 0 0 25px yellow, 0 0 35px orange; }
    }
    .star {
      position: absolute;
      font-size: 8px;
      z-index: 1;
      color: white;
      animation: moveStar 10s linear infinite;
      text-shadow: 0 0 4px white;
      pointer-events: none;
    }
    @keyframes moveStar {
      0% { transform: translateY(0) translateX(0); opacity: 0.3; }
      50% { transform: translateY(-100px) translateX(40px); opacity: 1; }
      100% { transform: translateY(-200px) translateX(-40px); opacity: 0; }
    }
    .message {
      position: absolute;
      font-weight: 600;
      max-width: 300px;
      line-height: 2.5;
      word-break: break-word;
      white-space: normal;
      z-index: 2;
      opacity: 0.9;
      user-select: none;
      animation: float 16s ease-in-out infinite;
      text-shadow:
        0 0 6px currentColor,
        0 0 12px currentColor,
        0 0 18px currentColor;
      pointer-events: none;
    }
    @keyframes float {
      0% { transform: translate(0, 0); opacity: 0; }
      20% { opacity: 1; }
      100% { transform: translate(-40px, -120vh); opacity: 0; }
    }
    audio {
      position: absolute;
      bottom: 10px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 5;
      width: 250px;
    }
  </style>
</head>
<body>

  <div class="moon-icon">🌙</div>

  <audio id="bg-music" controls autoplay loop>
    <source src="nhac.mp3" type="audio/mpeg">
  </audio>

  <script>
    const stars = ['✦', '✧', '✨', '⭐'];
    function createStar() {
      const star = document.createElement('div');
      star.className = 'star';
      star.textContent = stars[Math.floor(Math.random() * stars.length)];
      star.style.left = Math.random() * window.innerWidth + 'px';
      star.style.top = Math.random() * window.innerHeight + 'px';
      star.style.fontSize = (4 + Math.random() * 4) + 'px';
      star.style.animationDuration = (8 + Math.random() * 4) + 's';
      document.body.appendChild(star);
      setTimeout(() => star.remove(), 12000);
    }
    setInterval(createStar, 200);

    const messages = [
      "chúc cậu sinh nhật vui vẻ", "tuổi mới mạnh khỏe tự tin", "7.5 IELTS nhaa", "mong cậu có thêm nhiều bạn mới", "chúc cậu vui vẻ yêu đời",
      "cảm ơn vì đã cố gắng cho bản thân cậu", "Tuổi mới không còn phải khóc", "Ăn được ngủ được là tiên", "Khỏe mạnh khỏe mạnh khỏe mạnh nghen", "Thi đậu đại học nữaa",
      "Thật ra là không biết you có xúc động hong nữa", "mà mong rằng chúng ta mãi là bạn tốt he", "suốt năm suôn sẻ 10 phân vẹn 10",
      "trong con đường sắp tới mong rằng cậu có cái đầu lạnh", "và đừng quên một trái tim ấm",
      "lâu lâu mà toi có rì không ổn cậu bỏ qua he", "lời thú nhận năm 17 tủi của alin:))",
      "chỉ là thật sự không còn nhỏ để thích làm gì thì làm", "nhưng đủ lớn để làm những điều mình muốn", "17 tuổi vui vẻeee"
    ];

    let colorIndex = 0;
    const colors = ["hotpink", "aqua"]; // Đan xanh-hồng

    function createMessage() {
      const msg = document.createElement('div');
      msg.className = 'message';
      msg.textContent = messages[Math.floor(Math.random() * messages.length)];
      msg.style.color = colors[colorIndex % 2];
      colorIndex++;
      msg.style.left = Math.random() * (window.innerWidth - 320) + 'px';
      msg.style.top = window.innerHeight + Math.random() * 100 + 'px';
      msg.style.fontSize = (15 + Math.random() * 4) + 'px';
      msg.style.animationDuration = (12 + Math.random() * 4) + 's';
      document.body.appendChild(msg);
      setTimeout(() => msg.remove(), 18000);
    }

    setInterval(createMessage, 350);
  </script>

</body>
</html>
