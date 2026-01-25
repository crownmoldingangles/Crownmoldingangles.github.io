<html lang="en">
<head>
    <!-- Google tag (gtag.js) -->
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
            padding: 20px 15px;
            text-align: center;
        }

        .header h1 {
            font-size: clamp(1.5em, 5vw, 2.5em);
            margin-bottom: 10px;
            line-height: 1.2;
        }

        .header p {
            font-size: clamp(0.9em, 3vw, 1.1em);
            opacity: 0.9;
        }

        .content {
            display: grid;
            grid-template-columns: 1fr;
            gap: 20px;
            padding: 20px 15px;
        }

        .calculator-section, .diagram-section {
            background: #f8f9fa;
            padding: 20px 15px;
            border-radius: 15px;
        }

        h2 {
            color: #667eea;
            margin-bottom: 15px;
            font-size: clamp(1.3em, 4vw, 1.8em);
        }

        h3 {
            font-size: clamp(1em, 3vw, 1.2em);
        }

        .input-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            color: #333;
            font-weight: 600;
            font-size: clamp(0.9em, 2.5vw, 1em);
        }

        input[type="number"], select {
            width: 100%;
            padding: 14px 12px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            transition: border-color 0.3s;
            -webkit-appearance: none;
            appearance: none;
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
        }

        .radio-group {
            display: flex;
            flex-direction: column;
            gap: 12px;
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
        }

        .radio-group label:has(input:checked) {
            border-color: #667eea;
            background: #f0f4ff;
        }

        input[type="radio"] {
            width: 22px;
            height: 22px;
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
        }

        button:active {
            transform: scale(0.98);
        }

        button:hover {
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }

        .results {
            margin-top: 25px;
            padding: 20px 15px;
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
        }

        .result-value {
            font-size: clamp(1.5em, 5vw, 2em);
            color: #667eea;
            font-weight: bold;
        }

        #sawPosition {
            font-size: clamp(0.9em, 2.5vw, 1em);
            line-height: 1.4;
        }

        .diagram-canvas {
            width: 100%;
            height: auto;
            min-height: 400px;
            max-height: 600px;
            background: white;
            border-radius: 10px;
            border: 2px solid #ddd;
            touch-action: none;
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
            margin-left: 20px;
            color: #856404;
        }

        .instructions li {
            margin-bottom: 8px;
            font-size: clamp(0.85em, 2.5vw, 0.95em);
            line-height: 1.5;
        }

        .info-box {
            margin-top: 20px;
            padding: 15px;
            background: white;
            border-radius: 10px;
        }

        .info-box p {
            color: #555;
            line-height: 1.6;
            font-size: clamp(0.85em, 2.5vw, 0.95em);
        }

        .info-box strong {
            display: block;
            margin-bottom: 5px;
            color: #667eea;
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
                gap: 20px;
            }

            .radio-group label {
                padding: 8px 12px;
            }

            .diagram-canvas {
                height: 500px;
            }
        }

        @media (max-width: 480px) {
            .content {
                padding: 15px 10px;
            }

            .calculator-section, .diagram-section {
                padding: 15px 10px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🔨 Crown Molding Angle Calculator</h1>
            <p>Professional-grade calculations for perfect miter and bevel cuts</p>
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
                            Inside Corner
                        </label>
                        <label>
                            <input type="radio" name="cornerType" value="outside">
                            Outside Corner
                        </label>
                    </div>
                </div>

                <div class="input-group">
                    <label>Cutting Position</label>
                    <div class="radio-group">
                        <label>
                            <input type="radio" name="cuttingPosition" value="flat" checked>
                            Laying Flat
                        </label>
                        <label>
                            <input type="radio" name="cuttingPosition" value="nested">
                            Nested (Upright)
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
                        <strong>Miter Angle:</strong> The angle you set on your miter saw's turntable (horizontal rotation).<br><br>
                        <strong>Bevel Angle:</strong> The angle you tilt your saw blade (vertical tilt).<br><br>
                        <strong>Laying Flat:</strong> Crown molding lies flat on the saw table. Requires both miter and bevel angles.<br><br>
                        <strong>Nested:</strong> Crown molding positioned against fence at spring angle. Only miter angle needed.
                    </p>
                </div>
            </div>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('diagramCanvas');
        const ctx = canvas.getContext('2d');
        
        function resizeCanvas() {
            const container = canvas.parentElement;
            const rect = container.getBoundingClientRect();
            const dpr = window.devicePixelRatio || 1;
            
            canvas.width = rect.width * dpr;
            canvas.height = Math.min(600, Math.max(400, rect.width * 1.2)) * dpr;
            canvas.style.width = rect.width + 'px';
            canvas.style.height = (canvas.height / dpr) + 'px';
            
            ctx.scale(dpr, dpr);
            
            if (document.getElementById('results').style.display !== 'none') {
                calculate();
            }
        }

        window.addEventListener('resize', resizeCanvas);
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

            drawDiagram(miterAngle, bevelAngle, cornerType, cuttingPosition, springAngle);
        }

        function drawDiagram(miterAngle, bevelAngle, cornerType, cuttingPosition, springAngle) {
            const dpr = window.devicePixelRatio || 1;
            const w = canvas.width / dpr;
            const h = canvas.height / dpr;
            
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            const isMobile = w < 500;
            const scale = isMobile ? 0.7 : 1;
            const fontSize = isMobile ? 12 : 14;
            const titleSize = isMobile ? 14 : 18;

            // Title
            ctx.fillStyle = '#333';
            ctx.font = `bold ${titleSize}px Arial`;
            ctx.textAlign = 'center';
            ctx.fillText(cornerType.toUpperCase() + ' CORNER - ' + (cuttingPosition === 'flat' ? 'FLAT' : 'NESTED'), w/2, 25);
            ctx.textAlign = 'left';

            // Draw miter saw base (turntable)
            const centerX = w/2;
            const centerY = h/2 + (isMobile ? 20 : 50);
            const tableRadius = isMobile ? 80 : 120;
            
            // Saw table/base
            ctx.fillStyle = '#555';
            ctx.beginPath();
            ctx.arc(centerX, centerY, tableRadius + 20, 0, Math.PI * 2);
            ctx.fill();
            
            // Turntable (rotates for miter)
            ctx.save();
            ctx.translate(centerX, centerY);
            ctx.rotate(-miterAngle * Math.PI / 180);
            
            // Turntable disc
            ctx.fillStyle = '#777';
            ctx.beginPath();
            ctx.arc(0, 0, tableRadius, 0, Math.PI * 2);
            ctx.fill();
            ctx.strokeStyle = '#000';
            ctx.lineWidth = 2;
            ctx.stroke();
            
            // Scale markings
            ctx.strokeStyle = '#fff';
            ctx.lineWidth = 2;
            for (let i = 0; i < 360; i += 15) {
                const angle = i * Math.PI / 180;
                const r1 = tableRadius - 10;
                const r2 = tableRadius - 5;
                ctx.beginPath();
                ctx.moveTo(Math.cos(angle) * r1, Math.sin(angle) * r1);
                ctx.lineTo(Math.cos(angle) * r2, Math.sin(angle) * r2);
                ctx.stroke();
            }
            
            // Fence (back of saw)
            ctx.fillStyle = '#8b4513';
            ctx.fillRect(-tableRadius + 10, -tableRadius - 20, tableRadius * 2 - 20, 15);
            ctx.strokeStyle = '#333';
            ctx.lineWidth = 2;
            ctx.strokeRect(-tableRadius + 10, -tableRadius - 20, tableRadius * 2 - 20, 15);
            
            ctx.fillStyle = '#fff';
            ctx.font = `bold ${fontSize - 2}px Arial`;
            ctx.textAlign = 'center';
            ctx.fillText('FENCE', 0, -tableRadius - 8);
            
            // Crown molding on table
            const moldingWidth = isMobile ? 60 : 80;
            if (cuttingPosition === 'flat') {
                // Flat position
                ctx.fillStyle = '#f5deb3';
                ctx.fillRect(-moldingWidth, -tableRadius + 10, moldingWidth * 2, 40);
                ctx.strokeStyle = '#333';
                ctx.lineWidth = 3;
                ctx.strokeRect(-moldingWidth, -tableRadius + 10, moldingWidth * 2, 40);
                
                ctx.fillStyle = '#333';
                ctx.font = `bold ${fontSize - 3}px Arial`;
                if (cornerType === 'inside') {
                    ctx.fillText('BOTTOM edge', 0, -tableRadius + 5);
                    ctx.fillText('TOP on table', 0, -tableRadius + 60);
                } else {
                    ctx.fillText('TOP edge', 0, -tableRadius + 5);
                    ctx.fillText('BOTTOM on table', 0, -tableRadius + 60);
                }
            } else {
                // Nested position
                const springRad = springAngle * Math.PI / 180;
                
                ctx.save();
                ctx.translate(0, -tableRadius + 5);
                ctx.rotate(springRad);
                
                ctx.fillStyle = '#f5deb3';
                ctx.fillRect(-15, -70, 30, 70);
                ctx.strokeStyle = '#333';
                ctx.lineWidth = 3;
                ctx.strokeRect(-15, -70, 30, 70);
                
                ctx.restore();
                ctx.strokeStyle = '#4CAF50';
                ctx.lineWidth = 3;
                ctx.beginPath();
                ctx.arc(0, -tableRadius + 5, 40, -Math.PI/2, -Math.PI/2 + springRad, false);
                ctx.stroke();
                
                ctx.fillStyle = '#4CAF50';
                ctx.font = `bold ${fontSize}px Arial`;
                ctx.fillText(springAngle + '°', 50, -tableRadius + 20);
            }
            
            ctx.restore();
            
            // Draw blade assembly
            ctx.save();
            ctx.translate(centerX, centerY - (isMobile ? 30 : 50));
            
            ctx.fillStyle = '#333';
            ctx.beginPath();
            ctx.arc(0, 0, isMobile ? 25 : 35, 0, Math.PI * 2);
            ctx.fill();
            
            ctx.save();
            ctx.rotate(-bevelAngle * Math.PI / 180);
            
            const bladeRadius = isMobile ? 35 : 50;
            ctx.fillStyle = '#888';
            ctx.strokeStyle = '#000';
            ctx.lineWidth = 2;
            ctx.beginPath();
            ctx.arc(0, 0, bladeRadius, 0, Math.PI * 2);
            ctx.fill();
            ctx.stroke();
            
            ctx.strokeStyle = '#666';
            ctx.lineWidth = 3;
            for (let i = 0; i < 12; i++) {
                const angle = (i * 30) * Math.PI / 180;
                ctx.beginPath();
                ctx.moveTo(Math.cos(angle) * (bladeRadius - 5), Math.sin(angle) * (bladeRadius - 5));
                ctx.lineTo(Math.cos(angle) * (bladeRadius + 5), Math.sin(angle) * (bladeRadius + 5));
                ctx.stroke();
            }
            
            ctx.restore();
            ctx.restore();
            
            // Miter angle indicator
            ctx.strokeStyle = '#0066cc';
            ctx.lineWidth = 4;
            ctx.beginPath();
            ctx.arc(centerX, centerY, tableRadius + 35, -Math.PI/2, -Math.PI/2 - miterAngle * Math.PI / 180, true);
            ctx.stroke();
            
            ctx.save();
            ctx.translate(centerX, centerY);
            ctx.rotate(-miterAngle * Math.PI / 180 - Math.PI/2);
            ctx.fillStyle = '#0066cc';
            ctx.beginPath();
            ctx.moveTo(tableRadius + 35, 0);
            ctx.lineTo(tableRadius + 25, -8);
            ctx.lineTo(tableRadius + 25, 8);
            ctx.closePath();
            ctx.fill();
            ctx.restore();
            
            ctx.fillStyle = '#0066cc';
            ctx.font = `bold ${isMobile ? 16 : 20}px Arial`;
            ctx.textAlign = 'center';
            ctx.fillText('MITER: ' + miterAngle.toFixed(1) + '°', centerX, centerY - tableRadius - (isMobile ? 40 : 60));
            
            // Bevel angle indicator
            if (cuttingPosition === 'flat' && Math.abs(bevelAngle) > 0.5) {
                ctx.save();
                ctx.translate(centerX, centerY - (isMobile ? 30 : 50));
                
                ctx.strokeStyle = '#ff6600';
                ctx.lineWidth = 4;
                ctx.beginPath();
                ctx.arc(0, 0, isMobile ? 50 : 70, -Math.PI/2, -Math.PI/2 - bevelAngle * Math.PI / 180, bevelAngle < 0);
                ctx.stroke();
                
                ctx.rotate(-bevelAngle * Math.PI / 180 - Math.PI/2);
                ctx.fillStyle = '#ff6600';
                ctx.beginPath();
                ctx.moveTo(isMobile ? 50 : 70, 0);
                ctx.lineTo((isMobile ? 40 : 60), -6);
                ctx.lineTo((isMobile ? 40 : 60), 6);
                ctx.closePath();
                ctx.fill();
                
                ctx.restore();
                
                ctx.fillStyle = '#ff6600';
                ctx.font = `bold ${isMobile ? 14 : 20}px Arial`;
                ctx.textAlign = 'center';
                ctx.fillText('BEVEL: ' + bevelAngle.toFixed(1) + '°', isMobile ? centerX : centerX + 180, centerY - (isMobile ? 80 : 100));
            } else if (cuttingPosition === 'nested') {
                ctx.fillStyle = '#4CAF50';
                ctx.font = `bold ${isMobile ? 14 : 20}px Arial`;
                ctx.textAlign = 'center';
                ctx.fillText('BEVEL: 0°', isMobile ? centerX : centerX + 180, centerY - (isMobile ? 80 : 100));
            }
            
            // Instructions box
            const boxPadding = isMobile ? 10 : 30;
            const boxX = boxPadding;
            const boxY = h - (isMobile ? 140 : 180);
            const boxW = w - (boxPadding * 2);
            const boxH = isMobile ? 130 : 160;
            
            ctx.fillStyle = '#fffacd';
            ctx.fillRect(boxX, boxY, boxW, boxH);
            ctx.strokeStyle = '#333';
            ctx.lineWidth = 3;
            ctx.strokeRect(boxX, boxY, boxW, boxH);
            
            ctx.fillStyle = '#333';
            ctx.font = `bold ${isMobile ? 12 : 16}px Arial`;
            ctx.textAlign = 'left';
            ctx.fillText('SAW SETUP:', boxX + 10, boxY + 20);
            
            ctx.font = `${isMobile ? 10 : 14}px Arial`;
            let yPos = boxY + (isMobile ? 35 : 45);
            const lineHeight = isMobile ? 20 : 25;
            
            if (cuttingPosition === 'flat') {
                ctx.fillStyle = '#0066cc';
                ctx.fillText('1. Miter: ' + miterAngle.toFixed(1) + '°', boxX + 10, yPos);
                yPos += lineHeight;
                
                ctx.fillStyle = '#ff6600';
                ctx.fillText('2. Bevel: ' + bevelAngle.toFixed(1) + '°', boxX + 10, yPos);
                yPos += lineHeight;
                
                ctx.fillStyle = '#333';
                const text3 = cornerType === 'inside' ? '3. Bottom edge to fence' : '3. Top edge to fence';
                ctx.fillText(text3, boxX + 10, yPos);
                yPos += lineHeight;
                
                ctx.fillText('4. Make the cut', boxX + 10, yPos);
            } else {
                ctx.fillStyle = '#0066cc';
                ctx.fillText('1. Miter: ' + miterAngle.toFixed(1) + '°', boxX + 10, yPos);
                yPos += lineHeight;
                
                ctx.fillStyle = '#4CAF50';
                ctx.fillText('2. Bevel: 0° (no tilt)', boxX + 10, yPos);
                yPos += lineHeight;
                
                ctx.fillStyle = '#333';
                const text3 = cornerType === 'inside' ? '3. Upside down at ' + springAngle + '°' : '3. Right-side up at ' + springAngle + '°';
                ctx.fillText(text3, boxX + 10, yPos);
                yPos += lineHeight;
                
                ctx.fillText('4. Make the cut', boxX + 10, yPos);
            }
        }

        // Initial calculation and diagram
        calculate();
    </script>
</body>
</html>
