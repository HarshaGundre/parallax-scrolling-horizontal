<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Parallax Website - Horizontal</title>
  <style>
    html, body {
      margin: 0;
      padding: 0;
      font-family: "Lato", sans-serif;
      font-size: 16px;
      line-height: 1.8em;
      color: #666;
      overflow-x: auto;
      overflow-y: hidden;
      height: 100vh;
      white-space: nowrap;
    }

    .container {
      display: flex;
      flex-direction: row;
      height: 100vh;
      width: max-content;
    }

    .parallax, section {
      flex: 0 0 100vw;
      height: 100vh;
      position: relative;
      display: inline-block;
      vertical-align: top;
      white-space: normal;
    }

    .parallax {
      background-attachment: fixed; /* Fixed for actual parallax effect */
      background-position: center;
      background-repeat: no-repeat;
      background-size: cover;
    }

    .pimg1 {
      background-image: url(data:image/jpeg;base64,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);
    }

    .pimg2 {
      background-image: url(https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ-eopPniIMp_p19y6N-Zz-1kxDApkXjyVmjA&s);
    }

    .pimg3 {
      background-image: url(https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ_8kpAvxJExhsGM1Gz_mYUl11UawAkC67zNQ&s);
    }

    .ptext {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      text-align: center;
      color: black;
      font-size: 27px;
      letter-spacing: 8px;
      text-transform: uppercase;
    }

    .textbg {
      background-color: #313534;
      color: #fff;
      padding: 10px;
    }

    section {
      padding: 50px 20px;
      text-align: center;
    }

    .section-light {
      background-color: #f4f4f4;
      color: #666;
    }

    .section-dark {
      background-color: #282e34;
      color: #ddd;
    }
  </style>
</head>
<body>

  <div class="container">
    <div class="parallax pimg1">
      <div class="ptext"><span class="textbg">Kohli in T20</span></div>
    </div>

    <section class="section section-dark">
      <h2>achievements</h2>
      <p>First Asian batter to score 100 half-centuries.</p>
      <p>First Indian to Score 13,000 T20 Runs.</p>  
      <p>He has won seven awards, more than any other player.</p>
    </section>

    <div class="parallax pimg2">
      <div class="ptext"><span class="textbg">Kohli in ODI</span></div>
    </div>

    <section class="section section-light">
      <h2>achievements</h2>
      <p>Fastest player to reach 14,000 ODI runs.</p>
      <p>Achieved 890 rating points in the ICC ODI rankings.</p>  
      <p>Highest annual runs by a captain in 2017: 1,460.</p>
      <p>First player to score 50 ODI centuries.</p>  
    </section>

    <div class="parallax pimg3">
      <div class="ptext"><span class="textbg">Kohli in Test</span></div>
    </div>

    <section class="section section-dark">
      <h2>achievements</h2>
      <p>Fastest to 25 Test centuries.</p>
      <p>Record for most Test double centuries by an Indian.</p>
      <p>Achieved 922 rating points, the highest for any Indian player.</p>
      <p>1,000+ runs in three consecutive years (2017–2019).</p>
    </section>
  </div>

  <script>
    const scrollSpeed = 2; // Pixels per frame for smooth movement
    let scrolling = true; // Flag to control scrolling

    function scrollHorizontally() {
      if (scrolling && document.body.scrollLeft + window.innerWidth < document.body.scrollWidth) {
        document.body.scrollLeft += scrollSpeed;
        requestAnimationFrame(scrollHorizontally);
      }
    }

    // Start scrolling on load
    window.onload = () => {
      setTimeout(() => {
        requestAnimationFrame(scrollHorizontally);
      }, 1000);
    };

    // Stop scrolling when the user interacts with scrolling
    window.addEventListener("wheel", () => scrolling = false);
    window.addEventListener("keydown", () => scrolling = false);
  </script>

</body>
</html>
