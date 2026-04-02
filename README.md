<!DOCTYPE html>
</header>

<nav>
  <a href="#home">Home</a>
  <a href="#services">Services</a>
  <a href="#contact">Contact</a>
</nav>

<div class="hero" id="home"><h1>Your Lawn, Our Passion</h1></div>

<div class="priceBox">Total: $<span id="price">0</span></div>

<section class="container" id="services">
  <h2>Our Services</h2>
  <div class="services">
    <div class="card" onclick="openPanel('grounds')">Grounds Work</div>
    <div class="card" onclick="openPanel('large')">Large Ground Changes</div>
  </div>
</section>

<!-- Grounds Work Panel -->
<div id="grounds" class="panel">
  <span class="close" onclick="closePanel('grounds')">&times;</span>
  <h3>Grounds Work</h3>
  <p>Prices starting at $20</p>

  <label><input type="checkbox" value="10" onchange="updatePrice(this)"> Weedwacking ($10+)</label><br>
  <label><input type="checkbox" value="20" onchange="updatePrice(this)"> Mowing ($20+)</label><br>
  <label><input type="checkbox" value="15" onchange="updatePrice(this)"> Hedge Trimming ($15+)</label><br>
  <label><input type="checkbox" value="25" onchange="updatePrice(this)"> Mowing + Weedwacking ($25+)</label><br>
  <label><input type="checkbox" value="15" onchange="updatePrice(this)"> Aerating ($15+)</label><br>
  <label><input type="checkbox" value="30" onchange="updatePrice(this)"> Weed Control ($30+)</label><br>

  <h4>Custom Request</h4>
  <textarea id="groundsText" placeholder="Describe your needs..."></textarea>
  <button onclick="sendEmail('groundsText')">Send Request</button>
</div>

<!-- Large Work Panel -->
<div id="large" class="panel">
  <span class="close" onclick="closePanel('large')">&times;</span>
  <h3>Large Ground Changes</h3>
  <textarea id="largeText" placeholder="Describe your project..."></textarea>
  <button onclick="sendEmail('largeText')">Send Request</button>
</div>

<section class="container" id="contact">
  <h2>Contact</h2>
  <p>Email: <a href="mailto:deerecarelandscaping@gmail.com">deerecarelandscaping@gmail.com</a></p>
  <p>Phone: <a href="tel:6086719597">608-671-9597</a></p>
</section>

<footer>
  <p>&copy; 2026 Deere Care Landscaping</p>
</footer>

<script>
let total = 0;
function openPanel(id){ document.getElementById(id).classList.add('open'); }
function closePanel(id){ document.getElementById(id).classList.remove('open'); }

function updatePrice(el){
  if(el.checked){ total += parseInt(el.value); }
  else{ total -= parseInt(el.value); }
  document.getElementById('price').innerText = total;
}

function sendEmail(textId){
  const text = document.getElementById(textId).value;
  const subject = "Service Request";
  const body = text + "\nEstimated total: $" + total;
  window.location.href = `mailto:deerecarelandscaping@gmail.com?subject=${subject}&body=${encodeURIComponent(body)}`;
}
</script>

</body>
</html>

