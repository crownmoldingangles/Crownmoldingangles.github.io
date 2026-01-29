<html lang="en">
<head>
    <!-- Google tag (gtag.js) -->
    <meta name="google-site-verification" content="3w4GC1azo_rciRXOXBDQY4z-SZOlDP8FvmKB1tkiiPA" />
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XTNZ9QLRTG"></script>
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
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 10px;
            overflow-x: hidden;
            width: 100%;
        }

        .container {
            max-width: 1200px;
            width: 100%;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 20px 15px;
            text-align: center;
        }

        .header h1 {
            font-size: clamp(1.3em, 5vw, 2.5em);
            margin-bottom: 8px;
            line-height: 1.2;
        }

        .header p {
            font-size: clamp(0.8em, 3vw, 1.1em);
            opacity: 0.95;
            line-height: 1.4;
        }

        .header a {
            color: white;
            text-decoration: underline;
        }

        .content {
            display: grid;
            grid-template-columns: 1fr;
            gap: 15px;
            padding: 15px;
            width: 100%;
            box-sizing: border-box;
        }

        .calculator-section, .diagram-section {
            background: #f8f9fa;
            padding: 20px 15px;
            border-radius: 15px;
            width: 100%;
            max-width: 100%;
            box-sizing: border-box;
            overflow: hidden;
        }

        h2 {
            color: #667eea;
            margin-bottom: 15px;
            font-size: clamp(1.2em, 4vw, 1.8em);
        }

        h3 {
            font-size: clamp(0.95em, 3vw, 1.2em);
        }

        .input-group {
            margin-bottom: 18px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            color: #333;
            font-weight: 600;
            font-size: clamp(0.9em, 2.5vw, 1em);
            line-height: 1.3;
        }

        input[type="number"], select {
            width: 100%;
            max-width: 100%;
            padding: 14px 12px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            transition: border-color 0.3s;
            -webkit-appearance: none;
            appearance: none;
            box-sizing: border-box;
        }

        select {
            background: white url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 12 12'%3E%3Cpath fill='%23333' d='M6 9L1 4h10z'/%3E%3C/svg%3E") no-repeat right 12px center;
            padding-right: 35px;
        }

        input[type="number"]:focus, select:focus {
            outline: none;
            border-color: #667eea;
        }

        small {
            font-size: clamp(0.75em, 2vw, 0.85em);
            line-height: 1.4;
            display: block;
            margin-top: 4px;
        }

        .radio-group {
            display: flex;
            flex-direction: column;
            gap: 10px;
            margin-top: 10px;
        }

        .radio-group label {
            display: flex;
            align-items: center;
            gap: 10px;
            font-weight: normal;
            padding: 12px;
            background: white;
            border-radius: 8px;
            border: 2px solid #ddd;
            cursor: pointer;
            transition: all 0.2s;
            margin-bottom: 0;
            min-height: 48px;
        }

        .radio-group label:has(input:checked) {
            border-color: #667eea;
            background: #f0f4ff;
        }

        input[type="radio"] {
            width: 20px;
            height: 20px;
            cursor: pointer;
            flex-shrink: 0;
        }

        button {
            width: 100%;
            padding: 16px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 8px;
            font-size: clamp(1em, 3vw, 1.125em);
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.2s, box-shadow 0.2s;
            -webkit-tap-highlight-color: transparent;
            min-height: 48px;
        }

        button:active {
            transform: scale(0.98);
        }

        button:hover {
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }

        .results {
            margin-top: 20px;
            padding: 18px 15px;
            background: white;
            border-radius: 10px;
            border-left: 4px solid #667eea;
        }

        .result-item {
            margin-bottom: 15px;
        }

        .result-label {
            font-weight: 600;
            color: #555;
            font-size: clamp(0.8em, 2.5vw, 0.875em);
            margin-bottom: 4px;
        }

        .result-value {
            font-size: clamp(1.8em, 6vw, 2em);
            color: #667eea;
            font-weight: bold;
            line-height: 1.2;
        }

        #sawPosition {
            font-size: clamp(0.9em, 2.5vw, 1em);
            line-height: 1.5;
        }

        .diagram-canvas {
            width: 100%;
            height: auto;
            background: white;
            border-radius: 10px;
            border: 2px solid #ddd;
            touch-action: pan-y pinch-zoom;
            display: block;
        }

        .instructions {
            margin-top: 20px;
            padding: 15px;
            background: #fff3cd;
            border-radius: 10px;
            border-left: 4px solid #ffc107;
        }

        .instructions h3 {
            color: #856404;
            margin-bottom: 10px;
        }

        .instructions ol {
            margin-left: 18px;
            color: #856404;
            padding-left: 0;
        }

        .instructions li {
            margin-bottom: 8px;
            font-size: clamp(0.85em, 2.5vw, 0.95em);
            line-height: 1.6;
            padding-left: 4px;
        }

        .info-box {
            margin-top: 20px;
            padding: 15px;
            background: white;
            border-radius: 10px;
        }

        .info-box p {
            color: #555;
            line-height: 1.7;
            font-size: clamp(0.85em, 2.5vw, 0.95em);
        }

        .info-box strong {
            display: block;
            margin-bottom: 5px;
            margin-top: 10px;
            color: #667eea;
        }

        .info-box strong:first-child {
            margin-top: 0;
        }

        .faq-section {
            background: #f8f9fa;
            padding: 20px 15px;
            border-radius: 15px;
            margin-top: 15px;
        }

        .faq-section h2 {
            color: #667eea;
            margin-bottom: 20px;
            font-size: clamp(1.2em, 4vw, 1.8em);
        }

        .faq-section h3 {
            color: #333;
            margin-top: 20px;
            margin-bottom: 10px;
            font-size: clamp(0.95em, 3vw, 1.2em);
        }

        .faq-section h3:first-of-type {
            margin-top: 0;
        }

        .faq-section p {
            color: #555;
            line-height: 1.7;
            font-size: clamp(0.85em, 2.5vw, 0.95em);
            margin-bottom: 15px;
        }

        @media (min-width: 768px) {
            body {
                padding: 20px;
            }

            .content {
                grid-template-columns: 1fr 1fr;
                gap: 30px;
                padding: 30px;
            }

            .calculator-section, .diagram-section {
                padding: 25px;
            }

            .header {
                padding: 30px;
            }

            .radio-group {
                flex-direction: row;
                gap: 15px;
            }

            .radio-group label {
                flex: 1;
            }

            .diagram-canvas {
                min-height: 450px;
                max-height: 600px;
            }

            .faq-section {
                padding: 25px 30px;
            }
        }

        @media (max-width: 480px) {
            body {
                padding: 8px;
            }

            .content {
                padding: 12px;
                gap: 12px;
            }

            .calculator-section, .diagram-section {
                padding: 15px 12px;
            }

            .header {
                padding: 15px 12px;
            }

            .input-group {
                margin-bottom: 16px;
            }

            .results {
                padding: 15px 12px;
            }

            .instructions, .info-box {
                padding: 12px;
            }

            .diagram-canvas {
                min-height: 300px;
            }

            .faq-section {
                padding: 15px 12px;
            }
        }

        @media (max-width: 360px) {
            .header h1 {
                font-size: 1.2em;
            }

            .diagram-canvas {
                min-height: 280px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🔨 Crown Molding Angle Calculator</h1>
            <p>Professional-grade calculations for perfect miter and bevel cuts</p>
            <p><a href="howto.html"> How to Cut Crown Molding: A Beginner's Guide </a></p>
        </div>

        <div class="content">
            <div class="calculator-section">
                <h2>Input Parameters</h2>
                
                <div class="input-group">
                    <label for="cornerAngle">Corner Angle (degrees)</label>
                    <input type="number" id="cornerAngle" value="90" min="1" max="180" step="0.1" inputmode="decimal">
                    <small style="color: #666;">Most corners are 90°, but measure if unsure</small>
                </div>

                <div class="input-group">
                    <label for="springAngle">Crown Molding Spring Angle</label>
                    <select id="springAngle">
                        <option value="38">38° (52/38 - Most Common)</option>
                        <option value="45">45° (45/45 - Standard)</option>
                        <option value="52">52° (38/52)</option>
                        <option value="custom">Custom Angle</option>
                    </select>
                </div>

                <div class="input-group" id="customAngleGroup" style="display: none;">
                    <label for="customSpringAngle">Custom Spring Angle (degrees)</label>
                    <input type="number" id="customSpringAngle" value="38" min="1" max="89" step="0.1" inputmode="decimal">
                </div>

                <div class="input-group">
                    <label>Corner Type</label>
                    <div class="radio-group">
                        <label>
                            <input type="radio" name="cornerType" value="inside" checked>
                            <span>Inside Corner</span>
                        </label>
                        <label>
                            <input type="radio" name="cornerType" value="outside">
                            <span>Outside Corner</span>
                        </label>
                    </div>
                </div>

                <div class="input-group">
                    <label>Cutting Position</label>
                    <div class="radio-group">
                        <label>
                            <input type="radio" name="cuttingPosition" value="flat" checked>
                            <span>Laying Flat</span>
                        </label>
                        <label>
                            <input type="radio" name="cuttingPosition" value="nested">
                            <span>Nested (Upright)</span>
                        </label>
                    </div>
                </div>

                <button onclick="calculate()">Calculate Angles</button>

                <div class="results" id="results" style="display: none;">
                    <div class="result-item">
                        <div class="result-label">MITER ANGLE</div>
                        <div class="result-value" id="miterAngle">--</div>
                    </div>
                    <div class="result-item">
                        <div class="result-label">BEVEL ANGLE</div>
                        <div class="result-value" id="bevelAngle">--</div>
                    </div>
                    <div class="result-item" id="sawPositionInfo">
                        <div class="result-label">SAW POSITION</div>
                        <div style="color: #333; margin-top: 5px;" id="sawPosition">--</div>
                    </div>
                </div>

                <div class="instructions">
                    <h3>Quick Guide:</h3>
                    <ol>
                        <li>Measure your corner angle (usually 90°)</li>
                        <li>Check your crown molding spring angle (usually 38° or 45°)</li>
                        <li>Select inside or outside corner</li>
                        <li>Choose how you'll cut (flat or nested)</li>
                        <li>Set your saw to the calculated angles</li>
                    </ol>
                </div>
            </div>

            <div class="diagram-section">
                <h2>Visual Cutting Guide</h2>
                <canvas id="diagramCanvas" class="diagram-canvas"></canvas>
                
                <div class="info-box">
                    <h3 style="color: #667eea; margin-bottom: 10px;">Understanding the Cuts:</h3>
                    <p>
                        <strong>Miter Angle:</strong> The angle you set on your miter saw's turntable (horizontal rotation).
                        
                        <strong>Bevel Angle:</strong> The angle you tilt your saw blade (vertical tilt).
                        
                        <strong>Laying Flat:</strong> Crown molding lies flat on the saw table. Requires both miter and bevel angles.
                        
                        <strong>Nested:</strong> Crown molding positioned against fence at spring angle. Only miter angle needed.
                    </p>
                </div>
            </div>
        </div>

        <div class="faq-section" style="max-width: 1200px; margin: 0 auto; padding: 20px 15px;">
            <h2>Frequently Asked Questions</h2>
            <h3>What miter angle do I use for crown molding?</h3>
            <p>
                The miter angle depends on the spring angle and corner type.
                For standard 38° or 45° crown molding, this calculator gives
                the exact miter and bevel angles automatically.
            </p>
            <h3>Do inside and outside corners use the same angles?</h3>
            <p>
                No. Inside and outside corners require mirrored miter settings.
                This calculator adjusts automatically based on corner type.
            </p>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('diagramCanvas');
        const ctx = canvas.getContext('2d');
        let animationFrame = null;
        let currentAngles = {
            miter: 45,
            bevel: 33.9,
            spring: 38,
            cornerType: 'inside',
            cuttingPosition: 'flat',
            cornerAngle: 90
        };
        
        function resizeCanvas() {
            const container = canvas.parentElement;
            const rect = container.getBoundingClientRect();
            const dpr = window.devicePixelRatio || 1;
            
            const width = rect.width;
            const height = width * 1.3;
            
            canvas.width = width * dpr;
            canvas.height = height * dpr;
            canvas.style.width = width + 'px';
            canvas.style.height = height + 'px';
            
            ctx.scale(dpr, dpr);
            
            if (document.getElementById('results').style.display !== 'none') {
                drawDiagram(currentAngles.miter, currentAngles.bevel, currentAngles.cornerType, 
                           currentAngles.cuttingPosition, currentAngles.spring, currentAngles.cornerAngle);
            }
        }

        window.addEventListener('resize', resizeCanvas);
        window.addEventListener('orientationchange', () => {
            setTimeout(resizeCanvas, 100);
        });
        resizeCanvas();

        document.getElementById('springAngle').addEventListener('change', function() {
            const customGroup = document.getElementById('customAngleGroup');
            customGroup.style.display = this.value === 'custom' ? 'block' : 'none';
        });

        function calculate() {
            const cornerAngle = parseFloat(document.getElementById('cornerAngle').value);
            const springAngleSelect = document.getElementById('springAngle').value;
            const springAngle = springAngleSelect === 'custom' 
                ? parseFloat(document.getElementById('customSpringAngle').value)
                : parseFloat(springAngleSelect);
            
            const cornerType = document.querySelector('input[name="cornerType"]:checked').value;
            const cuttingPosition = document.querySelector('input[name="cuttingPosition"]:checked').value;

            let miterAngle, bevelAngle, sawPosition;

            if (cuttingPosition === 'nested') {
                miterAngle = cornerAngle / 2;
                bevelAngle = 0;
                sawPosition = cornerType === 'inside' 
                    ? 'Position crown upside down against fence at spring angle'
                    : 'Position crown right-side up against fence at spring angle';
            } else {
                const cornerRad = cornerAngle * Math.PI / 180;
                const springRad = springAngle * Math.PI / 180;
                
                miterAngle = Math.atan(Math.cos(springRad) * Math.tan(cornerRad / 2)) * 180 / Math.PI;
                bevelAngle = Math.asin(Math.sin(springRad) * Math.sin(cornerRad / 2)) * 180 / Math.PI;
                
                if (cornerType === 'inside') {
                    sawPosition = 'Place crown flat, bottom edge against fence, top edge on table';
                } else {
                    sawPosition = 'Place crown flat, top edge against fence, bottom edge on table';
                }
            }

            document.getElementById('miterAngle').textContent = miterAngle.toFixed(2) + '°';
            document.getElementById('bevelAngle').textContent = bevelAngle.toFixed(2) + '°';
            document.getElementById('sawPosition').textContent = sawPosition;
            document.getElementById('results').style.display = 'block';

            currentAngles = {
                miter: miterAngle,
                bevel: bevelAngle,
                spring: springAngle,
                cornerType: cornerType,
                cuttingPosition: cuttingPosition,
                cornerAngle: cornerAngle
            };

            drawDiagram(miterAngle, bevelAngle, cornerType, cuttingPosition, springAngle, cornerAngle);
        }

        function drawDiagram(miterAngle, bevelAngle, cornerType, cuttingPosition, springAngle, cornerAngle) {
            const dpr = window.devicePixelRatio || 1;
            const w = canvas.width / dpr;
            const h = canvas.height / dpr;
            
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            const isMobile = w < 500;
            const isVerySmall = w < 360;
            
            // Stop any existing animation
            if (animationFrame) {
                cancelAnimationFrame(animationFrame);
            }
            
            let animationPhase = 0;
            
            function animateCut() {
                animationPhase = (animationPhase + 0.015) % 2;
                drawFrame(animationPhase);
                animationFrame = requestAnimationFrame(animateCut);
            }
            
            function drawFrame(phase) {
                ctx.clearRect(0, 0, canvas.width, canvas.height);
                
                const showCut = phase > 1;
                
                // Title with angle info
                ctx.fillStyle = '#333';
                ctx.font = `bold ${isVerySmall ? 14 : 18}px Arial`;
                ctx.textAlign = 'center';
                const titleText = showCut ? 'AFTER CUT' : 'BEFORE CUT';
                ctx.fillText(titleText, w/2, 25);
                
                // Subtitle showing the corner angle
                ctx.font = `${isVerySmall ? 10 : 12}px Arial`;
                ctx.fillStyle = '#666';
                ctx.fillText(`${cornerAngle.toFixed(1)}° ${cornerType} corner`, w/2, 42);
                
                // Draw miter saw
                const sawBaseY = h * 0.65;
                const sawCenterX = w / 2;
                
                // Base/Table
                ctx.fillStyle = '#555';
                ctx.fillRect(sawCenterX - 120, sawBaseY, 240, 20);
                ctx.strokeStyle = '#000';
                ctx.lineWidth = 2;
                ctx.strokeRect(sawCenterX - 120, sawBaseY, 240, 20);
                
                // Fence
                ctx.fillStyle = '#654321';
                ctx.fillRect(sawCenterX - 120, sawBaseY - 25, 240, 25);
                ctx.strokeStyle = '#000';
                ctx.lineWidth = 2;
                ctx.strokeRect(sawCenterX - 120, sawBaseY - 25, 240, 25);
                
                ctx.fillStyle = '#fff';
                ctx.font = `bold ${isVerySmall ? 9 : 11}px Arial`;
                ctx.fillText('FENCE', sawCenterX, sawBaseY - 10);
                
                // Turntable with dynamic miter rotation
                ctx.save();
                ctx.translate(sawCenterX, sawBaseY);
                ctx.rotate(-miterAngle * Math.PI / 180);
                
                // Rotating table surface
                ctx.fillStyle = '#888';
                ctx.beginPath();
                ctx.arc(0, 0, 80, 0, Math.PI * 2);
                ctx.fill();
                ctx.strokeStyle = '#333';
                ctx.lineWidth = 2;
                ctx.stroke();
                
                // Miter angle indicator lines
                ctx.strokeStyle = '#FFD700';
                ctx.lineWidth = 2;
                ctx.beginPath();
                ctx.moveTo(0, 0);
                ctx.lineTo(0, -75);
                ctx.stroke();
                
                // Draw miter arc
                ctx.strokeStyle = '#FFD700';
                ctx.lineWidth = 2;
                ctx.beginPath();
                ctx.arc(0, 0, 50, -Math.PI/2, -Math.PI/2 - (miterAngle * Math.PI / 180), true);
                ctx.stroke();
                
                // Saw arm pivot
                ctx.fillStyle = '#444';
                ctx.beginPath();
                ctx.arc(0, -60, 15, 0, Math.PI * 2);
                ctx.fill();
                
                // Saw arm
                ctx.fillStyle = '#666';
                ctx.fillRect(-10, -120, 20, 60);
                ctx.strokeStyle = '#000';
                ctx.lineWidth = 2;
                ctx.strokeRect(-10, -120, 20, 60);
                
                // Saw motor housing with dynamic bevel tilt
                ctx.save();
                ctx.translate(0, -120);
                ctx.rotate(-bevelAngle * Math.PI / 180);
                
                // Motor housing
                ctx.fillStyle = '#2E7D32';
                ctx.fillRect(-30, -40, 60, 40);
                ctx.strokeStyle = '#000';
                ctx.lineWidth = 2;
                ctx.strokeRect(-30, -40, 60, 40);
                
                // Bevel angle indicator (if bevel is not 0)
                if (Math.abs(bevelAngle) > 0.5) {
                    ctx.strokeStyle = '#FFA500';
                    ctx.lineWidth = 2;
                    ctx.beginPath();
                    ctx.arc(0, 0, 25, -Math.PI/2, -Math.PI/2 - (bevelAngle * Math.PI / 180), true);
                    ctx.stroke();
                }
                
                // Blade
                ctx.fillStyle = '#C0C0C0';
                ctx.beginPath();
                ctx.arc(0, 0, 35, 0, Math.PI * 2);
                ctx.fill();
                ctx.strokeStyle = '#333';
                ctx.lineWidth = 2;
                ctx.stroke();
                
                // Blade teeth
                ctx.strokeStyle = '#666';
                ctx.lineWidth = 2;
                for (let i = 0; i < 12; i++) {
                    const angle = (i * 30) * Math.PI / 180;
                    ctx.beginPath();
                    ctx.moveTo(Math.cos(angle) * 30, Math.sin(angle) * 30);
                    ctx.lineTo(Math.cos(angle) * 38, Math.sin(angle) * 38);
                    ctx.stroke();
                }
                
                ctx.restore();
                ctx.restore();
                
                // Miter adjustment knob with angle display
                ctx.fillStyle = '#FFD700';
                ctx.beginPath();
                ctx.arc(sawCenterX - 100, sawBaseY + 30, 12, 0, Math.PI * 2);
                ctx.fill();
                ctx.strokeStyle = '#000';
                ctx.lineWidth = 2;
                ctx.stroke();
                
                for (let i = 0; i < 6; i++) {
                    const angle = (i * 60 - miterAngle * 3) * Math.PI / 180;
                    ctx.beginPath();
                    ctx.moveTo(sawCenterX - 100 + Math.cos(angle) * 8, sawBaseY + 30 + Math.sin(angle) * 8);
                    ctx.lineTo(sawCenterX - 100 + Math.cos(angle) * 12, sawBaseY + 30 + Math.sin(angle) * 12);
                    ctx.stroke();
                }
                
                ctx.fillStyle = '#333';
                ctx.font = `bold ${isVerySmall ? 8 : 10}px Arial`;
                ctx.textAlign = 'center';
                ctx.fillText('MITER', sawCenterX - 100, sawBaseY + 50);
                ctx.fillText(miterAngle.toFixed(1) + '°', sawCenterX - 100, sawBaseY + 62);
                
                // Bevel adjustment knob with angle display
                ctx.fillStyle = '#FFD700';
                ctx.beginPath();
                ctx.arc(sawCenterX + 100, sawBaseY + 30, 12, 0, Math.PI * 2);
                ctx.fill();
                ctx.strokeStyle = '#000';
                ctx.lineWidth = 2;
                ctx.stroke();
                
                for (let i = 0; i < 6; i++) {
                    const angle = (i * 60 - bevelAngle * 3) * Math.PI / 180;
                    ctx.beginPath();
                    ctx.moveTo(sawCenterX + 100 + Math.cos(angle) * 8, sawBaseY + 30 + Math.sin(angle) * 8);
                    ctx.lineTo(sawCenterX + 100 + Math.cos(angle) * 12, sawBaseY + 30 + Math.sin(angle) * 12);
                    ctx.stroke();
                }
                
                ctx.fillStyle = '#333';
                ctx.font = `bold ${isVerySmall ? 8 : 10}px Arial`;
                ctx.textAlign = 'center';
                ctx.fillText('BEVEL', sawCenterX + 100, sawBaseY + 50);
                ctx.fillText(bevelAngle.toFixed(1) + '°', sawCenterX + 100, sawBaseY + 62);
                
                // Crown molding with dynamic angles
                const moldingY = sawBaseY - 40;
                
                if (cuttingPosition === 'flat') {
                    // Draw molding laying flat with accurate cut angle
                    ctx.save();
                    ctx.translate(sawCenterX, moldingY);
                    ctx.rotate(-miterAngle * Math.PI / 180);
                    
                    if (showCut) {
                        // Show cut piece with accurate angle
                        const cutDepth = 15 * Math.tan(bevelAngle * Math.PI / 180);
                        
                        ctx.fillStyle = '#DEB887';
                        ctx.beginPath();
                        ctx.moveTo(-60, -15);
                        ctx.lineTo(0, -15);
                        ctx.lineTo(cutDepth + 10, 0);
                        ctx.lineTo(0, 15);
                        ctx.lineTo(-60, 15);
                        ctx.closePath();
                        ctx.fill();
                        ctx.strokeStyle = '#000';
                        ctx.lineWidth = 2;
                        ctx.stroke();
                        
                        // Highlight the angled cut edge
                        ctx.strokeStyle = '#FF0000';
                        ctx.lineWidth = 3;
                        ctx.beginPath();
                        ctx.moveTo(0, -15);
                        ctx.lineTo(cutDepth + 10, 0);
                        ctx.lineTo(0, 15);
                        ctx.stroke();
                        
                        // Show the other piece moved away
                        ctx.globalAlpha = 0.5;
                        ctx.fillStyle = '#DEB887';
                        ctx.beginPath();
                        ctx.moveTo(cutDepth + 20, 0);
                        ctx.lineTo(cutDepth + 10, -15);
                        ctx.lineTo(80, -15);
                        ctx.lineTo(80, 15);
                        ctx.lineTo(cutDepth + 10, 15);
                        ctx.closePath();
                        ctx.fill();
                        ctx.globalAlpha = 1;
                    } else {
                        // Show full piece before cut
                        ctx.fillStyle = '#DEB887';
                        ctx.fillRect(-80, -15, 160, 30);
                        ctx.strokeStyle = '#000';
                        ctx.lineWidth = 2;
                        ctx.strokeRect(-80, -15, 160, 30);
                        
                        // Show cut line at angle
                        ctx.strokeStyle = '#FF0000';
                        ctx.lineWidth = 2;
                        ctx.setLineDash([5, 5]);
                        ctx.beginPath();
                        ctx.moveTo(0, -20);
                        ctx.lineTo(0, 20);
                        ctx.stroke();
                        ctx.setLineDash([]);
                    }
                    
                    ctx.restore();
                    
                    // Labels
                    ctx.fillStyle = '#0066FF';
                    ctx.font = `bold ${isVerySmall ? 9 : 11}px Arial`;
                    ctx.textAlign = 'left';
                    if (cornerType === 'inside') {
                        ctx.fillText('BOTTOM edge → fence', sawCenterX - 115, moldingY - 25);
                        ctx.fillText('TOP edge → table', sawCenterX - 115, moldingY + 35);
                    } else {
                        ctx.fillText('TOP edge → fence', sawCenterX - 115, moldingY - 25);
                        ctx.fillText('BOTTOM edge → table', sawCenterX - 115, moldingY + 35);
                    }
                    
                } else {
                    // Draw nested molding with accurate spring angle
                    ctx.save();
                    ctx.translate(sawCenterX, sawBaseY);
                    ctx.rotate(-miterAngle * Math.PI / 180);
                    
                    const springRad = springAngle * Math.PI / 180;
                    ctx.rotate(-springRad);
                    
                    if (showCut) {
                        // Show cut piece
                        ctx.fillStyle = '#DEB887';
                        ctx.beginPath();
                        ctx.moveTo(-12, -5);
                        ctx.lineTo(-12, -70);
                        ctx.lineTo(12, -70);
                        ctx.lineTo(12, -5);
                        ctx.lineTo(8, 0);
                        ctx.lineTo(-8, 0);
                        ctx.closePath();
                        ctx.fill();
                        ctx.strokeStyle = '#000';
                        ctx.lineWidth = 2;
                        ctx.stroke();
                        
                        // Show cut edge
                        ctx.strokeStyle = '#FF0000';
                        ctx.lineWidth = 3;
                        ctx.beginPath();
                        ctx.moveTo(-8, 0);
                        ctx.lineTo(0, -5);
                        ctx.lineTo(8, 0);
                        ctx.stroke();
                        
                        // Show other piece
                        ctx.globalAlpha = 0.5;
                        ctx.fillStyle = '#DEB887';
                        ctx.beginPath();
                        ctx.moveTo(-8, 10);
                        ctx.lineTo(-12, 15);
                        ctx.lineTo(-12, 80);
                        ctx.lineTo(12, 80);
                        ctx.lineTo(12, 15);
                        ctx.lineTo(8, 10);
                        ctx.closePath();
                        ctx.fill();
                        ctx.globalAlpha = 1;
                    } else {
                        // Show full piece
                        ctx.fillStyle = '#DEB887';
                        ctx.fillRect(-12, -80, 24, 80);
                        ctx.strokeStyle = '#000';
                        ctx.lineWidth = 2;
                        ctx.strokeRect(-12, -80, 24, 80);
                        
                        // Show cut line
                        ctx.strokeStyle = '#FF0000';
                        ctx.lineWidth = 2;
                        ctx.setLineDash([5, 5]);
                        ctx.beginPath();
                        ctx.moveTo(-15, 0);
                        ctx.lineTo(15, 0);
                        ctx.stroke();
                        ctx.setLineDash([]);
                    }
                    
                    ctx.restore();
                    
                    // Spring angle indicator with actual angle
                    ctx.strokeStyle = '#00AA00';
                    ctx.lineWidth = 3;
                    ctx.beginPath();
                    ctx.save();
                    ctx.translate(sawCenterX, sawBaseY);
                    ctx.rotate(-miterAngle * Math.PI / 180);
                    ctx.arc(0, 0, 40, -Math.PI/2, -Math.PI/2 - springRad, true);
                    ctx.stroke();
                    ctx.restore();
                    
                    ctx.fillStyle = '#00AA00';
                    ctx.font = `bold ${isVerySmall ? 10 : 12}px Arial`;
                    ctx.textAlign = 'left';
                    ctx.fillText(springAngle.toFixed(1) + '° spring', sawCenterX + 50, sawBaseY - 30);
                    
                    // Orientation label
                    ctx.fillStyle = '#0066FF';
                    ctx.font = `bold ${isVerySmall ? 9 : 11}px Arial`;
                    if (cornerType === 'inside') {
                        ctx.fillText('Position UPSIDE DOWN', sawCenterX - 115, sawBaseY - 100);
                    } else {
                        ctx.fillText('Position RIGHT-SIDE UP', sawCenterX - 115, sawBaseY - 100);
                    }
                }
                
                // Setup instructions box
                const instructY = 60;
                const boxHeight = isVerySmall ? 65 : 75;
                ctx.fillStyle = '#fff';
                ctx.fillRect(10, instructY, w - 20, boxHeight);
                ctx.strokeStyle = '#2196F3';
                ctx.lineWidth = 3;
                ctx.strokeRect(10, instructY, w - 20, boxHeight);
                
                ctx.fillStyle = '#1976D2';
                ctx.font = `bold ${isVerySmall ? 10 : 12}px Arial`;
                ctx.textAlign = 'left';
                ctx.fillText('SAW SETTINGS:', 20, instructY + 18);
                
                ctx.fillStyle = '#333';
                ctx.font = `${isVerySmall ? 9 : 11}px Arial`;
                ctx.fillText('1. Set MITER to ' + miterAngle.toFixed(1) + '°', 20, instructY + 35);
                ctx.fillText('2. Set BEVEL to ' + bevelAngle.toFixed(1) + '°', 20, instructY + 50);
                if (isVerySmall) {
                    ctx.fillText('3. Position molding & cut', 20, instructY + 65);
                } else {
                    ctx.fillText('3. Position molding as shown and cut', 20, instructY + 65);
                }
            }
            
            animateCut();
        }

        // Initial calculation with default values
        calculate();
    </script>
</body>
</html>
