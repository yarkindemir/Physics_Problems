<h2>11. Animation: Two-Slit Interference</h2>

<p><strong>Wave equation:</strong></p>
<p>
u(r,t) = [A / |r - r₁|] sin(k|r - r₁| - &omega;t) + 
         [A / |r - r₂|] sin(k|r - r₂| - &omega;t)
</p>

<p><strong>Definitions:</strong></p>
<ul>
  <li>r₁, r₂ → positions of the two slits</li>
  <li>d = |r₁ - r₂| → distance between slits</li>
  <li>&lambda; → wavelength</li>
  <li>k = 2&pi;/&lambda;</li>
</ul>

<p><strong>Idea:</strong></p>
<p>
Each slit acts as a wave source. The waves spread and interfere.
The total wave is the sum of both waves.
</p>

<ul>
  <li>Constructive interference → bright regions</li>
  <li>Destructive interference → dark regions</li>
</ul>

<hr>

<p><strong>Interactive HTML Animation:</strong></p>

<canvas id="slitCanvas" width="720" height="400"></canvas>

<br>

<label>Slit distance (d):</label>
<input type="range" id="d" min="20" max="150" value="60">

<label>Wavelength (&lambda;):</label>
<input type="range" id="lambda2" min="20" max="120" value="50">

<p>Move sliders to change the interference pattern.</p>

<script>
const canvas2 = document.getElementById("slitCanvas");
const ctx2 = canvas2.getContext("2d");

function drawInterference(t) {
  const w = canvas2.width;
  const h = canvas2.height;

  const d = parseFloat(document.getElementById("d").value);
  const lambda = parseFloat(document.getElementById("lambda2").value);

  const k = 2 * Math.PI / lambda;

  const r1 = { x: 80, y: h/2 - d/2 };
  const r2 = { x: 80, y: h/2 + d/2 };

  const img = ctx2.createImageData(w, h);
  const data = img.data;

  for (let y = 0; y < h; y += 2) {
    for (let x = 0; x < w; x += 2) {

      const dx1 = x - r1.x;
      const dy1 = y - r1.y;
      const dx2 = x - r2.x;
      const dy2 = y - r2.y;

      const R1 = Math.sqrt(dx1*dx1 + dy1*dy1) + 1;
      const R2 = Math.sqrt(dx2*dx2 + dy2*dy2) + 1;

      const u =
        (1/R1) * Math.sin(k*R1 - t*0.02) +
        (1/R2) * Math.sin(k*R2 - t*0.02);

      let c = Math.floor(127 + 127*u);

      for (let dy2 = 0; dy2 < 2; dy2++) {
        for (let dx2 = 0; dx2 < 2; dx2++) {
          const i = 4 * ((y+dy2)*w + (x+dx2));
          data[i] = c;
          data[i+1] = 255 - c;
          data[i+2] = 180;
          data[i+3] = 255;
        }
      }
    }
  }

  ctx2.putImageData(img, 0, 0);

  // draw slits
  ctx2.fillStyle = "black";
  ctx2.beginPath();
  ctx2.arc(r1.x, r1.y, 4, 0, 2*Math.PI);
  ctx2.fill();

  ctx2.beginPath();
  ctx2.arc(r2.x, r2.y, 4, 0, 2*Math.PI);
  ctx2.fill();

  requestAnimationFrame(drawInterference);
}

requestAnimationFrame(drawInterference);
</script>

<p><strong>Explanation:</strong></p>
<p>
This animation simulates Young's double-slit experiment.
Changing the slit distance (d) changes the spacing of interference fringes.
Changing the wavelength (&lambda;) also affects the pattern size.
</p>