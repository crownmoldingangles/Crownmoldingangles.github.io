
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
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
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
            padding: 20px;
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

        .header h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
        }

        .header p {
            font-size: 1.1em;
            opacity: 0.9;
        }

        .content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            padding: 30px;
        }

        .calculator-section, .diagram-section {
            background: #f8f9fa;
            padding: 25px;
            border-radius: 15px;
        }

        h2 {
            color: #667eea;
            margin-bottom: 20px;
            font-size: 1.8em;
        }

        .input-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            color: #333;
            font-weight: 600;
        }

        input[type="number"], select {
            width: 100%;
            padding: 12px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            transition: border-color 0.3s;
        }

        input[type="number"]:focus, select:focus {
            outline: none;
            border-color: #667eea;
        }

        .radio-group {
            display: flex;
            gap: 20px;
            margin-top: 10px;
        }

        .radio-group label {
            display: flex;
            align-items: center;
            gap: 8px;
            font-weight: normal;
        }

        input[type="radio"] {
            width: 20px;
            height: 20px;
            cursor: pointer;
        }

        button {
            width: 100%;
            padding: 15px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.2s, box-shadow 0.2s;
        }

        button:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }

        .results {
            margin-top: 25px;
            padding: 20px;
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
            font-size: 14px;
        }

        .result-value {
            font-size: 24px;
            color: #667eea;
            font-weight: bold;
        }

        .diagram-canvas {
            width: 100%;
            height: 500px;
            background: white;
            border-radius: 10px;
            border: 2px solid #ddd;
        }

        .instructions {
            margin-top: 20px;
            padding: 20px;
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
        }

        @media (max-width: 968px) {
            .content {
                grid-template-columns: 1fr;
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
                    <input type="number" id="cornerAngle" value="90" min="1" max="180" step="0.1">
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
                    <input type="number" id="customSpringAngle" value="38" min="1" max="89" step="0.1">
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
                
                <div style="margin-top: 20px; padding: 15px; background: white; border-radius: 10px;">
                    <h3 style="color: #667eea; margin-bottom: 10px;">Understanding the Cuts:</h3>
                    <p style="color: #555; line-height: 1.6;">
                        <strong>Miter Angle:</strong> The angle you set on your miter saw's turntable (horizontal rotation).<br>
                        <strong>Bevel Angle:</strong> The angle you tilt your saw blade (vertical tilt).<br><br>
                        <strong>Laying Flat:</strong> Crown molding lies flat on the saw table. Requires both miter and bevel angles.<br>
                        <strong>Nested:</strong> Crown molding positioned against fence at spring angle. Only miter angle needed.
                    </p>
                </div>
            </div>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('diagramCanvas');
        const ctx = canvas.getContext('2d');
        
        canvas.width = canvas.offsetWidth;
        canvas.height = canvas.offsetHeight;

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
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            
            const w = canvas.width;
            const h = canvas.height;

            // Title
            ctx.fillStyle = '#333';
            ctx.font = 'bold 18px Arial';
            ctx.textAlign = 'center';
            ctx.fillText(cornerType.toUpperCase() + ' CORNER - ' + (cuttingPosition === 'flat' ? 'FLAT' : 'NESTED') + ' METHOD', w/2, 30);
            ctx.textAlign = 'left';

            // Draw miter saw base (turntable)
            const centerX = w/2;
            const centerY = h/2 + 50;
            const tableRadius = 120;
            
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
            ctx.font = 'bold 12px Arial';
            ctx.textAlign = 'center';
            ctx.fillText('FENCE', 0, -tableRadius - 8);
            
            // Crown molding on table
            if (cuttingPosition === 'flat') {
                // Flat position
                ctx.fillStyle = '#f5deb3';
                ctx.fillRect(-80, -tableRadius + 10, 160, 40);
                ctx.strokeStyle = '#333';
                ctx.lineWidth = 3;
                ctx.strokeRect(-80, -tableRadius + 10, 160, 40);
                
                ctx.fillStyle = '#333';
                ctx.font = 'bold 11px Arial';
                if (cornerType === 'inside') {
                    ctx.fillText('BOTTOM edge', 0, -tableRadius + 5);
                    ctx.fillText('TOP edge on table', 0, -tableRadius + 60);
                } else {
                    ctx.fillText('TOP edge', 0, -tableRadius + 5);
                    ctx.fillText('BOTTOM edge on table', 0, -tableRadius + 60);
                }
            } else {
                // Nested position - crown standing up
                const springRad = springAngle * Math.PI / 180;
                
                ctx.save();
                ctx.translate(0, -tableRadius + 5);
                ctx.rotate(springRad);
                
                ctx.fillStyle = '#f5deb3';
                ctx.fillRect(-15, -70, 30, 70);
                ctx.strokeStyle = '#333';
                ctx.lineWidth = 3;
                ctx.strokeRect(-15, -70, 30, 70);
                
                // Spring angle label
                ctx.restore();
                ctx.strokeStyle = '#4CAF50';
                ctx.lineWidth = 3;
                ctx.beginPath();
                ctx.arc(0, -tableRadius + 5, 40, -Math.PI/2, -Math.PI/2 + springRad, false);
                ctx.stroke();
                
                ctx.fillStyle = '#4CAF50';
                ctx.font = 'bold 12px Arial';
                ctx.fillText(springAngle + '°', 50, -tableRadius + 20);
            }
            
            ctx.restore();
            
            // Draw blade assembly
            ctx.save();
            ctx.translate(centerX, centerY - 50);
            
            // Blade housing
            ctx.fillStyle = '#333';
            ctx.beginPath();
            ctx.arc(0, 0, 35, 0, Math.PI * 2);
            ctx.fill();
            
            // Blade (tilted for bevel)
            ctx.save();
            ctx.rotate(-bevelAngle * Math.PI / 180);
            
            ctx.fillStyle = '#888';
            ctx.strokeStyle = '#000';
            ctx.lineWidth = 2;
            ctx.beginPath();
            ctx.arc(0, 0, 50, 0, Math.PI * 2);
            ctx.fill();
            ctx.stroke();
            
            // Blade teeth
            ctx.strokeStyle = '#666';
            ctx.lineWidth = 3;
            for (let i = 0; i < 12; i++) {
                const angle = (i * 30) * Math.PI / 180;
                ctx.beginPath();
                ctx.moveTo(Math.cos(angle) * 45, Math.sin(angle) * 45);
                ctx.lineTo(Math.cos(angle) * 55, Math.sin(angle) * 55);
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
            
            // Miter angle arrow and label
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
            ctx.font = 'bold 20px Arial';
            ctx.textAlign = 'center';
            ctx.fillText('MITER: ' + miterAngle.toFixed(1) + '°', centerX, centerY - tableRadius - 60);
            
            // Bevel angle indicator
            if (cuttingPosition === 'flat' && Math.abs(bevelAngle) > 0.5) {
                ctx.save();
                ctx.translate(centerX, centerY - 50);
                
                ctx.strokeStyle = '#ff6600';
                ctx.lineWidth = 4;
                ctx.beginPath();
                ctx.arc(0, 0, 70, -Math.PI/2, -Math.PI/2 - bevelAngle * Math.PI / 180, bevelAngle < 0);
                ctx.stroke();
                
                // Bevel arrow
                ctx.rotate(-bevelAngle * Math.PI / 180 - Math.PI/2);
                ctx.fillStyle = '#ff6600';
                ctx.beginPath();
                ctx.moveTo(70, 0);
                ctx.lineTo(60, -6);
                ctx.lineTo(60, 6);
                ctx.closePath();
                ctx.fill();
                
                ctx.restore();
                
                ctx.fillStyle = '#ff6600';
                ctx.font = 'bold 20px Arial';
                ctx.textAlign = 'center';
                ctx.fillText('BEVEL: ' + bevelAngle.toFixed(1) + '°', centerX + 180, centerY - 100);
            } else if (cuttingPosition === 'nested') {
                ctx.fillStyle = '#4CAF50';
                ctx.font = 'bold 20px Arial';
                ctx.textAlign = 'center';
                ctx.fillText('BEVEL: 0° (NO TILT)', centerX + 180, centerY - 100);
            }
            
            // Instructions box
            const boxX = 30;
            const boxY = h - 180;
            const boxW = w - 60;
            const boxH = 160;
            
            ctx.fillStyle = '#fffacd';
            ctx.fillRect(boxX, boxY, boxW, boxH);
            ctx.strokeStyle = '#333';
            ctx.lineWidth = 3;
            ctx.strokeRect(boxX, boxY, boxW, boxH);
            
            ctx.fillStyle = '#333';
            ctx.font = 'bold 16px Arial';
            ctx.textAlign = 'left';
            ctx.fillText('HOW TO SET YOUR SAW:', boxX + 15, boxY + 25);
            
            ctx.font = '14px Arial';
            let yPos = boxY + 50;
            
            if (cuttingPosition === 'flat') {
                ctx.fillStyle = '#0066cc';
                ctx.fillText('1. Rotate turntable to ' + miterAngle.toFixed(1) + '° on the miter scale', boxX + 15, yPos);
                yPos += 25;
                
                ctx.fillStyle = '#ff6600';
                ctx.fillText('2. Tilt blade to ' + bevelAngle.toFixed(1) + '° on the bevel scale', boxX + 15, yPos);
                yPos += 25;
                
                ctx.fillStyle = '#333';
                if (cornerType === 'inside') {
                    ctx.fillText('3. Place crown FLAT: bottom edge against fence, top edge on table', boxX + 15, yPos);
                } else {
                    ctx.fillText('3. Place crown FLAT: top edge against fence, bottom edge on table', boxX + 15, yPos);
                }
                yPos += 25;
                
                ctx.fillText('4. Make the cut - both angles work together for perfect fit', boxX + 15, yPos);
            } else {
                ctx.fillStyle = '#0066cc';
                ctx.fillText('1. Rotate turntable to ' + miterAngle.toFixed(1) + '° on the miter scale', boxX + 15, yPos);
                yPos += 25;
                
                ctx.fillStyle = '#4CAF50';
                ctx.fillText('2. Keep blade at 0° - NO bevel tilt needed!', boxX + 15, yPos);
                yPos += 25;
                
                ctx.fillStyle = '#333';
                if (cornerType === 'inside') {
                    ctx.fillText('3. Hold crown UPSIDE DOWN against fence at ' + springAngle + '° spring angle', boxX + 15, yPos);
                } else {
                    ctx.fillText('3. Hold crown RIGHT-SIDE UP against fence at ' + springAngle + '° spring angle', boxX + 15, yPos);
                }
                yPos += 25;
                
                ctx.fillText('4. Make the cut - much simpler than flat method!', boxX + 15, yPos);
            }
        }

        // Initial calculation and diagram
        calculate();
    </script>
</body>
</html>
