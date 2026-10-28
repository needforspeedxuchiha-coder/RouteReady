
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>RouteReady | Faculty of Syariah and Law</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: Arial, sans-serif;
      background: #f4f7f5;
      color: #183c2e;
      min-height: 100vh;
    }

    header {
      background: #164e3b;
      color: white;
      padding: 28px 20px;
      text-align: center;
    }

    .logo {
  font-size: 30px;
  font-weight: bold;
  letter-spacing: 1px;
  color: #ffffff;
    }

    header p {
      margin-top: 9px;
      font-size: 14px;
      line-height: 1.5;
      color: #d8e9df;
    }

    main {
      max-width: 650px;
      margin: 0 auto;
      padding: 28px 18px 40px;
    }

    .intro {
      text-align: center;
      margin-bottom: 25px;
    }

    .intro h1 {
      font-size: 24px;
      margin-bottom: 10px;
    }

    .intro p {
      color: #62756a;
      line-height: 1.6;
      font-size: 14px;
    }

    .destination {
      display: flex;
      align-items: center;
      gap: 15px;
      width: 100%;
      background: white;
      border: 1px solid #dce8df;
      border-radius: 16px;
      padding: 20px 17px;
      margin-bottom: 15px;
      text-align: left;
      color: #183c2e;
      cursor: pointer;
      box-shadow: 0 4px 12px rgba(20, 60, 40, 0.05);
      transition: transform 0.2s, border-color 0.2s;
    }

    .destination:active {
      transform: scale(0.98);
    }

    .destination:hover {
      border-color: #4c9270;
    }

    .destination .emoji {
      font-size: 30px;
      width: 48px;
      text-align: center;
      flex-shrink: 0;
    }

    .destination .details {
      flex: 1;
    }

    .destination h2 {
      font-size: 17px;
      margin-bottom: 7px;
    }

    .destination p {
      font-size: 13px;
      color: #718078;
      line-height: 1.5;
    }

    .arrow {
      font-size: 24px;
      color: #4b8768;
    }

    #videoPage {
      display: none;
    }

    .back-button {
      background: #e0ece4;
      color: #164e3b;
      border: none;
      padding: 12px 18px;
      border-radius: 10px;
      font-size: 15px;
      font-weight: bold;
      cursor: pointer;
      margin-bottom: 22px;
    }

    .video-title {
      font-size: 23px;
      line-height: 1.4;
      margin-bottom: 8px;
    }

    .video-description {
      color: #62756a;
      line-height: 1.6;
      margin-bottom: 20px;
      font-size: 14px;
    }

    .video-container {
      position: relative;
      width: 100%;
      aspect-ratio: 16 / 9;
      background: #10271d;
      border-radius: 14px;
      overflow: hidden;
      box-shadow: 0 8px 22px rgba(0, 0, 0, 0.12);
    }

    .video-container iframe {
      position: absolute;
      inset: 0;
      width: 100%;
      height: 100%;
      border: 0;
    }

    .tip {
      background: #e6f0e8;
      border-radius: 12px;
      padding: 15px;
      margin-top: 20px;
      color: #315d45;
      font-size: 13px;
      line-height: 1.6;
    }

    footer {
      text-align: center;
      padding: 20px;
      color: #829087;
      font-size: 12px;
    }

    @media (min-width: 600px) {
      header {
        padding: 35px 20px;
      }

      main {
        padding-top: 38px;
      }

      .destination {
        padding: 23px;
      }
    }
  </style>
</head>

<body>
  <header>
    <div class="logo">⌖ RouteReady</div>
    <p>FACULTY OF SYARIAH AND LAW</p>
    <p>Find your destination. Follow the route.</p>
  </header>

  <main>
    <section id="homePage">
      <div class="intro">
        <h1>Where would you like to go?</h1>
        <p>Select your destination below to watch the route video.</p>
      </div>

      <button class="destination" onclick="openVideo('office')">
        <span class="emoji">🏢</span>
        <span class="details">
          <h2>Administrative Office</h2>
          <p>Find the way to the administrative office.</p>
        </span>
        <span class="arrow">›</span>
      </button>

      <button class="destination" onclick="openVideo('dks')">
        <span class="emoji">🎓</span>
        <span class="details">
          <h2>Medium Lecture Halls (DKS)</h2>
          <p>DKS 1.1 – DKS 1.4</p>
        </span>
        <span class="arrow">›</span>
      </button>

      <button class="destination" onclick="openVideo('bts')">
        <span class="emoji">📚</span>
        <span class="details">
          <h2>Medium Tutorial Rooms (BTS)</h2>
          <p>BTS 1.1 – BTS 1.7</p>
        </span>
        <span class="arrow">›</span>
      </button>
    </section>

    <section id="videoPage">
      <button class="back-button" onclick="goBack()">← Back</button>

      <h1 class="video-title" id="videoTitle"></h1>
      <p class="video-description" id="videoDescription"></p>

      <div class="video-container">
        <iframe
          id="videoFrame"
          src=""
          title="RouteReady navigation video"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          referrerpolicy="strict-origin-when-cross-origin"
          allowfullscreen>
        </iframe>
      </div>

      <div class="tip">
        <strong>Navigation Tip</strong><br>
        Watch the route video carefully to help you find your destination.
      </div>
    </section>
  </main>

  <footer>
    RouteReady · Faculty of Syariah and Law
  </footer>

  <script>
    const destinations = {
      office: {
        title: "Administrative Office",
        description: "Watch the route video to find the administrative office.",
        video: "Im4z1pXZ60g"
      },
      dks: {
        title: "Medium Lecture Halls (DKS)",
        description: "Route video for DKS 1.1 to DKS 1.4.",
        video: "Zne9Z8JADi4"
      },
      bts: {
        title: "Medium Tutorial Rooms (BTS)",
        description: "Route video for BTS 1.1 to BTS 1.7.",
        video: "7fZbrUTcdME"
      }
    };

    function openVideo(destination) {
      const item = destinations[destination];

      document.getElementById("homePage").style.display = "none";
      document.getElementById("videoPage").style.display = "block";

      document.getElementById("videoTitle").textContent = item.title;
      document.getElementById("videoDescription").textContent =
        item.description;

      document.getElementById("videoFrame").src =
        "https://www.youtube-nocookie.com/embed/" +
        item.video + "?rel=0";

      window.scrollTo(0, 0);
    }

    function goBack() {
      document.getElementById("videoFrame").src = "";
      document.getElementById("videoPage").style.display = "none";
      document.getElementById("homePage").style.display = "block";

      window.scrollTo(0, 0);
    }
  </script>
</body>
</html>
