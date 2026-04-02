<!DOCTYPE html>
    I began my journey into business by taking on small jobs and learning what it takes to serve people well.
  </p>
  <p>
    Over time, I went on to start four additional businesses. Through that experience, I sold two and passed
    one down to my sister, continuing to grow and learn along the way.
  </p>
  <p>
    Today, Deere Care Landscaping represents everything I’ve learned — dedication, quality service, and
    a commitment to making every customer’s property look its absolute best.
  </p>
</section>

<div id="grounds" class="panel">
  <span class="close" onclick="closePanel('grounds')">&times;</span>
  <h3>Grounds Work</h3>
  <p>Starting at $20</p>

  <label><input type="checkbox" value="10" onchange="updatePrice(this)"> Weedwacking ($10+)</label><br>
  <label><input type="checkbox" value="20" onchange="updatePrice(this)"> Mowing ($20+)</label><br>
  <label><input type="checkbox" value="15" onchange="updatePrice(this)"> Hedge Trimming ($15+)</label><br>
  <label><input type="checkbox" value="25" onchange="updatePrice(this)"> Mowing + Weedwacking ($25+)</label><br>
  <label><input type="checkbox" value="15" onchange="updatePrice(this)"> Aerating ($15+)</label><br>
  <label><input type="checkbox" value="30" onchange="updatePrice(this)"> Weed Control ($30+)</label><br>

  <textarea id="groundsText" placeholder="Describe additional details..."></textarea>
  <button onclick="sendEmail('groundsText')">Send Request</button>
</div>

<div id="landscape" class="panel">
  <span class="close" onclick="closePanel('landscape')">&times;</span>
  <h3>Landscaping Requests</h3>
  <textarea id="largeText" placeholder="Describe your landscaping project..."></textarea>
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

</div>

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
