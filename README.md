<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Tron USD (USDT)</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body, html {
      width: 100%;
      height: 100%;
      font-family: 'Segoe UI', sans-serif;
      overflow-x: hidden;
      background: black;
      color: #f1f1f1;
    }

    canvas {
      position: fixed;
      top: 0;
      left: 0;
      z-index: 0;
    }

    .content {
      position: relative;
      z-index: 1;
      max-width: 900px;
      margin: 0 auto;
      padding: 4rem 2rem;
      background-color: rgba(0, 0, 0, 0.7);
      border-radius: 12px;
      margin-top: 3rem;
      margin-bottom: 3rem;
    }

    header, section, footer {
      margin-bottom: 3rem;
    }

    h1, h2 {
      color: #e63946;
    }

    h1 {
      font-size: 2.5rem;
      text-align: center;
    }

    header p {
      text-align: center;
      font-size: 1.1rem;
      color: #aaa;
    }

    section h2 {
      border-bottom: 1px solid #444;
      padding-bottom: 0.5rem;
      margin-bottom: 1rem;
    }

    .donation-address {
      font-family: monospace;
      color: #ff4d4d;
    }

    table {
      width: 100%;
      margin-top: 1rem;
      border-collapse: collapse;
    }

    th, td {
      padding: 0.75rem;
      border: 1px solid #333;
      text-align: left;
    }

    th {
      background-color: #111;
      color: #e63946;
    }

    a {
      color: #ff4d4d;
    }

    footer {
      text-align: center;
      font-size: 0.9rem;
      color: #888;
    }

    .highlight {
      color: #ff4d4d;
    }

    .cta {
      font-size: 1.1rem;
      font-weight: bold;
    }

    .success-story {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 1.5rem;
      margin-top: 1rem;
    }

    .success-story img {
      border-radius: 50%;
      width: 120px;
      height: 120px;
      object-fit: cover;
      border: 2px solid #e63946;
    }

    .success-story p {
      margin-bottom: 0.5rem;
    }

    @media (max-width: 600px) {
      .success-story {
        flex-direction: column;
        text-align: center;
      }

      .success-story img {
        margin-bottom: 1rem;
      }
    }
  </style>
</head>
<body>

<canvas id="matrixCanvas"></canvas>

<div class="content">
  <header>
    <h1>Tron USD (USDT)</h1>
    <p>Dual Utility. Social Impact. Decentralized Power.</p>
  </header>

  <section>
    <h2>Our Mission</h2>
    <p>Empower transactions and empower futures. A portion of profits helps brilliant students complete their education.</p>
    <p>Contribute by simply buying or donating USDT (TRC-20).</p>
    <p><strong>Donation Address:</strong> <span class="donation-address">0x84F4CE8B889dFC29C5c96Fb144D7EAB446c4AED2</span></p>
  </section>

  <section>
    <h2>Live Stats <span class="highlight">(Coming Soon)</span></h2>
    <p>This section will show live stats once the Tron USD smart contract is deployed and connected via our API at:<br>
      <a href="https://tronusd.org/api/" target="_blank">https://tronusd.org/api/</a></p>

    <table>
      <thead>
        <tr>
          <th>Metric</th>
          <th>Value</th>
        </tr>
      </thead>
      <tbody>
        <tr><td>Total Supply</td><td>900,000,000,000 USDT</td></tr>
        <tr><td>Circulating Supply</td><td>[LIVE]</td></tr>
        <tr><td>Burned</td><td>[LIVE]</td></tr>
        <tr><td>Minted</td><td>[LIVE]</td></tr>
        <tr><td>Transfers</td><td>[LIVE]</td></tr>
        <tr><td>Market Price</td><td>[LIVE]</td></tr>
        <tr><td>24h Volume</td><td>[LIVE]</td></tr>
      </tbody>
    </table>
  </section>

  <section>
    <h2>Get Involved</h2>
    <p class="cta">Buy TRC-20 USDT. Help shape futures.</p>
    <p>Email us at <a href="mailto:support@tronusd.org">support@tronusd.org</a> for assistance.</p>
    <p>Official site: <a href="https://tronusd.org" target="_blank">tronusd.org</a></p>
  </section>

  <section>
    <h2>Student Success Story</h2>
    <div class="success-story">
      <img src="https://via.placeholder.com/120x120.png?text=Student" alt="Student Photo" />
      <div>
        <p style="font-style: italic; color: #ccc;">
          "Before TronUSD, I didn’t think I could afford to finish my engineering degree.
          Thanks to the support and funding provided through this initiative,
          I’m now graduating with honors and planning to launch a tech startup."
        </p>
        <p style="font-weight: bold; color: #e63946;">— Amina K., Lagos, Nigeria</p>
      </div>
    </div>
  </section>

  <footer>
    <p>© 2025 Tron USD Network. Not affiliated with TRON Foundation or Tether.</p>
    <p>This site is open source. <a href="#">Improve this page</a>.</p>
  </footer>
</div>

<script>
  // Matrix Falling Code Animation (Red Theme)
  const canvas = document.getElementById('matrixCanvas');
  const ctx = canvas.getContext('2d');

  canvas.height = window.innerHeight;
  canvas.width = window.innerWidth;

  const letters = 'アァイィウエエオカガキギクグケゲコゴサザシジスズセゼソゾタダチッヂヅテデトドナニヌネノハバパヒビピフブプヘベペホボポマミムメモヤユヨラリルレロワヲンABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789$#%&*';
  const fontSize = 14;
  const columns = canvas.width / fontSize;
  const drops = [];

  for (let x = 0; x < columns; x++) {
    drops[x] = 1;
  }

  function drawMatrix() {
    ctx.fillStyle = 'rgba(0, 0, 0, 0.05)';
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    ctx.fillStyle = '#e63946'; // Red color
    ctx.font = fontSize + 'px monospace';

    for (let i = 0; i < drops.length; i++) {
      const text = letters.charAt(Math.floor(Math.random() * letters.length));
      ctx.fillText(text, i * fontSize, drops[i] * fontSize);

      if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
        drops[i] = 0;
      }

      drops[i]++;
    }
  }

  setInterval(drawMatrix, 35);

  window.addEventListener('resize', () => {
    canvas.height = window.innerHeight;
    canvas.width = window.innerWidth;
  });
</script>

</body>
</html>
