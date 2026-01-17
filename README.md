# Crownmoldingangles.github.io
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <title>Crown Molding Angle Calculator – Miter & Bevel Cuts</title>

  <meta name="description" content="Free crown molding angle calculator for inside and outside corners. Instantly calculate exact miter and bevel angles for 38° and 45° spring angles with a visual saw diagram." />

  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f6f7f9;
      margin: 0;
      padding: 0;
      color: #222;
    }

    header {
      background: #1f2937;
      color: #fff;
      padding: 20px;
      text-align: center;
    }

    main {
      max-width: 900px;
      margin: auto;
      padding: 20px;
    }

    h1, h2 {
      margin-top: 0;
    }

    .card {
      background: #fff;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.08);
      margin-bottom: 20px;
    }

    label {
      font-weight: bold;
      display: block;
      margin-top: 12px;
    }

    input, select {
      width: 100%;
      padding: 10px;
      margin-top: 6px;
      font-size: 16px;
    }

    .radio-group {
      display: flex;
      gap: 20px;
      margin-top: 8px;
    }

    button {
      margin-top: 20px;
      width: 100%;
      padding: 14px;
      font-size: 18px;
      background: #2563eb;
      color: #fff;
      border: none;
      border-radius: 6px;
      cursor: pointer;
    }

    button:hover {
      background: #1e4ed8;
    }

    .results {
      margin-top: 20px;
      font-size: 18px;
    }

    .results strong {
      font-size: 22px;
    }

    .svg-wrap {
      text-align: center;
      margin-top: 20px;
    }

    footer {
      text-align: center;
      font-size: 14px;
      color: #666;
      margin-top: 40px;
    }

    .affiliate {
      background: #f1f5f9;
      padding: 15px;
      border-radius: 6px;
      margin-top: 20px;
      text-align: center;
    }
  </style>
</head>
<body>

<header>
  <h1>Crown Molding Angle Calculator</h1>
  <p>Instant miter & bevel angles for perfect crown molding cuts</p>
</header>

<main>

  <div class="card">
    <h2>Calculator</h2>

    <label>Wall Angle (degrees)</label>
    <input type="number" id="wallAngle" value="90" />

    <label>Spring Angle</label>
    <select id="springAngle">
      <option value="38">38°</option>
      <option value="45">45°</option>
    </select>

    <label>Corner Type</label>
    <div class="radio-group">
      <label><input type="radio" name="corner" value="inside" checked /> Inside</label>
      <label><input type="radio" name="corner" value="outside" /> Outside</label>
    </div>

    <button onclick="calculate()">Calculate Angles</button>

    <div class="results" id="results"></div>
  </div>

  <div class="card">
    <h2>Visual Saw Guide</h2>
    <div class="svg-wrap">
      <svg width="300" height="200" viewBox="0 0 300 200">
        <rect x="40" y="120" width="220" height="20" fill="#9ca3af" />
        <line id="blade" x1="150" y1="30" x2="150" y2="140" stroke="#dc2626" stroke-width="6" transform-origin="150px 140px"/>
      </svg>
    </div>
  </div>

  <div class="affiliate">
    <strong>Recommended Tools</strong><br>
    <p>
      👉 <em>Affiliate link placeholder</em><br>
      Miter Saw • Crown Stops • Digital Angle Finder
    </p>
  </div>

  <div class="card">
    <h2>How This Works</h2>
    <p>
      This crown molding calculator determines the correct miter and bevel angles
      based on wall angle, spring angle, and corner type. It removes guesswork and
      helps DIYers and professionals get clean, accurate cuts every time.
    </p>
  </div>

</main>

<footer>
  © 2026 Crown Molding Calculator • Free Tool
</footer>

<script>
function calculate() {
  const wallAngle = parseFloat(document.getElementById("wallAngle").value);
  const spring = parseFloat(document.getElementById("springAngle").value);
  const corner = document.querySelector('input[name="corner"]:checked').value;

  const wallRad = wallAngle * Math.PI / 180;
  const springRad = spring * Math.PI / 180;

  let miter = Math.atan(Math.sin(springRad) / Math.tan(wallRad / 2));
  let bevel = Math.asin(Math.cos(springRad) * Math.cos(wallRad / 2));

  miter = miter * 180 / Math.PI;
  bevel = bevel * 180 / Math.PI;

  if (corner === "outside") {
    miter = -miter;
  }

  document.getElementById("results").innerHTML =
    `<p>Miter Angle: <strong>${miter.toFixed(2)}°</strong></p>
     <p>Bevel Angle: <strong>${bevel.toFixed(2)}°</strong></p>`;

  document.getElementById("blade").setAttribute(
    "transform",
    `rotate(${miter},150,140)`
  );
}
</script>

</body>
</html>
