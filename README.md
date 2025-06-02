<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>My SPA</title>
  <style>
    body {
      margin: 0;
      font-family: 'Helvetica', sans-serif;
    }

    .nav {
      display: flex;
      justify-content: center;
      background: #333;
      flex-wrap: wrap;
    }

    .nav a {
      color: white;
      padding: 1em;
      text-decoration: none;
    }

    .nav a:hover {
      background: #444;
    }

    main {
      padding: 1em;
    }

    footer {
      text-align: center;
      padding: 1em;
      background: #f0f0f0;
      font-size: 0.9em;
    }

    @media (max-width: 600px) {
      .nav {
        flex-direction: column;
      }

      .nav a {
        text-align: center;
        padding: 1em 0;
      }
    }
    .home-section {
  padding: 2em 1em;
  overflow: hidden;
}

.home-image-left {
  float: left;
  width: 300px;
  max-width: 100%;
  height: auto;
  margin-right: 1.5em;
  margin-bottom: 1em;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.home-text-right {
  overflow: hidden;
}

12345678

.military-section {
  padding: 2em 1em;
  overflow: hidden;
}

.military-image-left {
  float: left;
  width: 300px;
  max-width: 100%;
  height: auto;
  margin-right: 1.5em;
  margin-bottom: 1em;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.military-text-right {
  overflow: hidden;
}

@media (max-width: 768px) {
  .military-image-left {
    float: none;
    display: block;
    margin: 0 auto 1em auto;
  }

  .military-text-right {
    text-align: center;
  }
}
@media (max-width: 768px) {
  .military-image-left {
    float: none;
    display: block;
    margin: 0 auto 1em auto;
  }

  .military-text-right {
    text-align: center;
  }
}


    
  </style>
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
  <script>
    const pages = {
      home: `
      <section class="home-section">
      <h1>유석준</h1>
      <img src="main.jpg" alt="메인 이미지" class="home-image-left" />
      <div class="home-text-right">
        <hr>
        <br>
        <p>안녕하세요. 저는 강원대학교 컴퓨터공학과 22학번 유석준입니다.</p><br>
        <P>1999년에 강원도 원주에서 태어나 계속 살았으며 본가에 가기 편하게</P>
        <P>강원도에 있는 대학중에 강원대학교를 선택해 진학하게 되었습니다.</P><br>
        <P>저의 관심사는 게임개발 혹은 기획입니다. 어린시절부터 게임을 많이</P>
        <p>접함으로서 자연스래 게임쪽으로 진로를 결정하게 되었습니다.</p>
        <hr>
      </div>
      </section>
      `,

      about: `
        <section class="military-section">
        <h1>대학에 오기까지</h1>
        <img src="military.jpg" alt="군대 이미지" class="military-image-left" />
        <div class="military-text-right">
          <hr>
          <br>
          <p>제가 대학에 진학하게 된 이유는 군대에서의 차별대우가 있었기 때문입니다.</p><br>
          <p>2019년 4월 21살이었던 당시에 입대를 해서 배치되었던 부대에서 학벌에 대한 차별이 심했었는데</p>
          <p>당시에 대학을 진학하지 않았던 저는 학벌이 좋은 동기에 비해 차별대우를 받았습니다.</p><br>
          <p>그게 마음에 걸려서 전역 이후 모아둔 적금을 이용해서 재수를 하게되어 22학년도에</p>
          <p>강원대학교에 진학하게 되었고 관심사인 게임과 컴퓨터를 연관지어보니 컴퓨터공학과가</p>
          <p>적합하다고 생각되어 진학하게 되었습니다.</p>
          <hr>
        </div>
        <div style="clear: both;"></div>
        </section>
      `,
      contact: `
        <h1>연락처</h1>
        <a href="mailto:dkfks248@kangwon.ac.kr">문의사항이 있으면 이메일로 연락 주세요: dkfks248@kangwon.ac.kr</p>
      `
    };

    $(document).ready(function () {
      function loadPage(page) {
        $("#app").html(pages[page] || "<h1>페이지를 찾을 수 없습니다</h1>");
      }

      function getPageFromHash() {
        const hash = window.location.hash.replace("#", "");
        return hash || "home";
      }

      function render() {
        const page = getPageFromHash();
        loadPage(page);
      }

      $(window).on("hashchange", render);
      render();
    });
  </script>
</head>
<body>
  <header>
    <nav class="nav">
      <a href="#home">자기소개</a>
      <a href="#about">대학에 오기까지</a>
      <a href="#contact">연락처</a>
    </nav>
  </header>

  <main id="app">
    <!-- 페이지 내용이 여기에 동적으로 삽입됩니다 -->
  </main>

  <footer>
    <p>&copy; 2025 웹프 과제</p>
  </footer>
</body>
</html>
