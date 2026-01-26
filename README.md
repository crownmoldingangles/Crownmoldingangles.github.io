<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Google tag (gtag.js) -->
    <script async src="https://www.googletagmanager.com"></script>
    <script>
      window.dataLayer = window.dataLayer || [];
      function gtag(){dataLayer.push(arguments);}
      gtag('js', new Date());
      gtag('config', 'G-XTNZ9QLRTG');
    </script>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0">
    <title>Crown Molding Angle Calculator</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 10px;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            overflow: hidden;
        }
        .header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 30px;
            text-align: center;
        }
        .content {
            display: grid;
            grid-template-columns: 1fr;
            gap: 20px;
            padding: 20px;
        }
        @media (min-width: 900px) { .content { grid-template-columns: 1fr 1fr; } }
        
        .calculator-section, .diagram-section {
            background: #f8f9fa;
            padding: 25px;
            border-radius: 15px;
        }
        .input-group { margin-bottom: 20px; }
        label { display: block; margin-bottom: 8px; font-weight: 600; color: #333; }
        input, select {
            width: 100%;
            padding: 12px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
        }
        .radio-group { display: flex; gap: 15px; margin-bottom: 20px; }
        .radio-option {
            flex: 1;
            padding: 10px;
            background: white;
            border: 2px solid #ddd;
            border-radius: 8px;
            text-align: center;
            cursor: pointer;
        }
        .radio-option input { width: auto; margin-right: 5px; }
        
        button {
            width: 100%;
            padding: 16px;
            background: #764ba2;
            color: white;
            border: none;
            border-radius: 8px;
            font-weight: bold;
            cursor: pointer;
            font-size: 1.1em;
        }

        .results {
            margin-top: 20px;
            padding: 15px;
            background: #eef2ff;
            border-left: 5px solid #667eea;
            border-radius: 8px;
        }
        .result-value { font-size: 2em; color: #764ba2; font-weight: bold; }

        /* Visualizer Styles */
        .visual-box {
            background: white;
            border: 1px solid #ddd;
            border-radius: 10px;
            padding: 15px;
            text-align: center;
        }
        #sawBlade {
            transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
            transform-origin: center;
        }
        .cut-comparison {
            display: flex;
            justify-content: space-around;
            margin-top: 20px;
        }
        .wood-preview {
            width: 120px;
            height: 40px;
            background: #d2b48c;
            border: 1px solid #a68a64;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 12px;
            font-weight: bold;
            transition: clip-path 0.5s;
        }
    </style>
</head>
<body>

<div class="container">
    <div class="header">
        <h1>Crown Molding Calculator</h1>
        <p>Precise Miter & Bevel Angles for Perfect Corners</p>
    </div>

    <div class="content">
        <!-- Input Section -->
        <div class="calculator-section">
            <div class="input-group">
                <label>Wall Angle (Degrees)</label>
                <input type="number" id="wallAngle" value="90" step="0.1">
                <small>Standard corner is 90°</small>
            </div>

            <div class="input-group">
                <label>Spring Angle (Molding Type)</label>
                <select id="springAngle">
                    <option value="38">38° (Standard/Most Common)</option>
                    <option value="45">45°</option>
                    <option value="52">52°</option>
                </select>
            </div>

            <label>Corner Type</label>
            <div class="radio-group">
                <label class="radio-option">
                    <input type="radio" name="cornerType" value="inside" checked> Inside
                </label>
                <label class="radio-option">
                    <input type="radio" name="cornerType" value="outside"> Outside
                </label>
            </div>

            <button onclick="calculate()">Calculate Settings</button>

            <div class="results" id="resultArea">
                <div>Miter Angle: <span id="miterOut" class="result-value">0.00°</span></div>
                <div>Bevel Angle: <span id="bevelOut" class="result-value">0.00°</span></div>
            </div>
        </div>

        <!-- Visual Section -->
        <div class="diagram-section">
            <h2 style="color:#764ba2; margin-bottom:15px;">Miter Saw Setup</h2>
            <div class="visual-box">
                <svg viewBox="0 0 200 120" width="100%">
                    <!-- Saw Table Top Down View -->
                    <rect x="20" y="80" width="160" height="30" fill="#e0e0e0" />
                    <rect x="20" y="40" width="160" height="10" fill="#999" /> <!-- Fence -->
                    
                    <!-- Wood Stock -->
                    <rect x="50" y="50" width="100" height="30" fill="#d2b48c" fill-opacity="0.6" />
                    
                    <!-- Blade Line -->
                    <line id="sawBlade" x1="100" y1="30" x2="100" y2="100" stroke="#ff4444" stroke-width="4" />
                </svg>
                <p id="instructionText" style="font-size: 0.9em; margin-top: 10px; color: #555;">
                    Adjust the saw to the angles shown.
                </p>
            </div>

            <div class="cut-comparison">
                <div>
                    <p><small>Stock Piece</small></p>
                    <div class="wood-preview">BEFORE</div>
                </div>
                <div>
                    <p><small>Calculated Cut</small></p>
                    <div id="afterPreview" class="wood-preview" style="background: #c19a6b;">AFTER</div>
                </div>
            </div>
        </div>
    </div>
</div>

<script>
function calculate() {
    const angle = parseFloat(document.getElementById('wallAngle').value);
    const spring = parseFloat(document.getElementById('springAngle').value);
    const type = document.querySelector('input[name="cornerType"]:checked').value;

    // Convert to radians for Math functions
    const radWall = (angle / 2) * (Math.PI / 180);
    const radSpring = spring * (Math.PI / 180);

    // Standard Compound Miter Formulas
    let miter = Math.atan(Math.sin(radSpring) / Math.tan(radWall)) * (180 / Math.PI);
    let bevel = Math.asin(Math.cos(radSpring) * Math.cos(radWall)) * (180 / Math.PI);

    // Display Data
    document.getElementById('miterOut').innerText = miter.toFixed(2) + "°";
    document.getElementById('bevelOut').innerText = bevel.toFixed(2) + "°";

    // Update Visuals
    const blade = document.getElementById('sawBlade');
    const afterPreview = document.getElementById('afterPreview');
    const instruction = document.getElementById('instructionText');

    // Visual rotation logic
    let visualRotation = type === 'inside' ? -miter : miter;
    blade.style.transform = `rotate(${visualRotation}deg)`;

    if (type === 'inside') {
        afterPreview.style.clipPath = "polygon(0 0, 100% 0, 75% 100%, 0% 100%)";
        instruction.innerHTML = "<strong>Inside Corner:</strong> Swing saw <strong>Left</strong>. Crown flat on table, top against fence.";
    } else {
        afterPreview.style.clipPath = "polygon(0 0, 75% 0, 100% 100%, 0% 100%)";
        instruction.innerHTML = "<strong>Outside Corner:</strong> Swing saw <strong>Right</strong>. Crown flat on table, top against fence.";
    }
}

// Run once on load
calculate();
</script>

</body>
</html>
