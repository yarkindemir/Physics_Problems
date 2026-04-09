<h2>10. Animation: Wave Sources</h2>

<p><strong>Wave equation for one source:</strong></p>
<p>
u(r,t) = [A / |r - r₀|<sup>&alpha;</sup>] sin(k|r - r₀| - &omega;t)
</p>

<p><strong>Definitions:</strong></p>
<ul>
  <li>r → observation point</li>
  <li>r₀ → position of the source</li>
  <li>A → amplitude</li>
  <li>&alpha; → decay parameter (0 to 2)</li>
  <li>k = 2&pi;/&lambda; → wave number</li>
  <li>&omega; → angular frequency</li>
</ul>

<p><strong>Idea:</strong></p>
<p>
Each point (dot) acts as a wave source.
The total wave is the sum of all waves (superposition).
</p>

<p><strong>Total wave:</strong></p>
<p>
u<sub>total</sub> = u₁ + u₂ + u₃ + ...
</p>

<p><strong>Effect of &alpha;:</strong></p>
<ul>
  <li>&alpha; = 0 → no decay (waves travel with same amplitude)</li>
  <li>Large &alpha; → waves decay faster with distance</li>
</ul>

<hr>

<p><strong>Interactive HTML Animation:</strong></p>

<canvas id="waveCanvas" width="700" height="400"></canvas>

<br>

<label>&alpha; (decay):</label>
<input type="range" id="alpha" min="0" max="2" step="0.1" value="1">

<label>Wavelength (&lambda;):</label>
<input type="range" id="lambda" min="20" max="120" value="60">

<button onclick="sources=[]">Clear Sources</button>

<p>Click on the canvas to add wave sources.</p>

<script>
const canvas = document.getElementById("waveCanvas");
const ctx = canvas.getContext("2d");

let sources = [];

canvas.addEventListener("click", (e) => {
  const rect = canvas.getBoundingClientRect();
  sources.push({
    x: e.clientX - rect.left,
    y: e.clientY - rect.top
  });
});

function draw(t) {
  const alpha = parseFloat(document.getElementById("alpha").value);
  const lambda = parseFloat(document.getElementById("lambda").value);
  const k = 2 * Math.PI / lambda;

  const w = canvas.width;
  const h = canvas.height;

  const image = ctx.createImageData(w, h);
  const data = image.data;

  for (let y = 0; y < h; y += 2) {
    for (let x = 0; x < w; x += 2) {

      let u = 0;

      for (let s of sources) {
        const dx = x - s.x;
        const dy = y - s.y;
        const r = Math.sqrt(dx*dx + dy*dy) + 1;

        u += (1 / Math.pow(r, alpha)) * Math.sin(k*r - t*0.01);
      }

      let c = Math.floor(127 + 127*u);

      for (let dy2 = 0; dy2 < 2; dy2++) {
        for (let dx2 = 0; dx2 < 2; dx2++) {
          const i = 4 * ((y+dy2)*w + (x+dx2));
          data[i] = c;
          data[i+1] = 100;
          data[i+2] = 255 - c;
          data[i+3] = 255;
        }
      }
    }
  }

  ctx.putImageData(image, 0, 0);

  for (let s of sources) {
    ctx.fillStyle = "black";
    ctx.beginPath();
    ctx.arc(s.x, s.y, 4, 0, 2*Math.PI);
    ctx.fill();
  }

  requestAnimationFrame(draw);
}

requestAnimationFrame(draw);
</script>

<p><strong>Explanation:</strong></p>
<p>
This animation shows how waves from multiple sources combine.
Each source produces circular waves, and the final pattern is the sum of all waves.
</p>