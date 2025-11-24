<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>FuelUp Café — Campus Food Truck</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    :root{--bg1:#0f172a;--bg2:#0b1220;--accent:#ff6b35;--accent2:#ffd166;--card:#ffffff;--glass:rgba(255,255,255,0.06);--muted:#d1d5db}
    *{box-sizing:border-box}
    body{margin:0;font-family:Poppins,system-ui,Arial;background:radial-gradient(1200px 600px at 10% 10%, rgba(255,107,53,0.08), transparent),linear-gradient(180deg,var(--bg1),var(--bg2));color:var(--muted);-webkit-font-smoothing:antialiased}
    .container{max-width:1200px;margin:28px auto;padding:20px}
    header{display:flex;align-items:center;gap:16px}
    .logo{background:linear-gradient(90deg,var(--accent),var(--accent2));color:#0b1220;padding:12px 16px;border-radius:12px;font-weight:700;box-shadow:0 10px 30px rgba(0,0,0,0.4)}
    h1{margin:0;color:white;font-size:1.6rem}
    p.lead{margin:0;color:var(--muted)}
    .hero{display:grid;grid-template-columns:1fr 420px;gap:22px;align-items:center;margin-top:20px}
    @media (max-width:920px){.hero{grid-template-columns:1fr}}
    .glass-card{background:linear-gradient(180deg,rgba(255,255,255,0.03),rgba(255,255,255,0.01));border-radius:14px;padding:18px;border:1px solid rgba(255,255,255,0.04);box-shadow:0 10px 40px rgba(2,6,23,0.6)}
    .big-phrase{font-size:1.3rem;color:#fff;margin-bottom:8px}
    .accent{color:var(--accent);font-weight:700}
    .sub{color:#cbd5e1}

    /* Menu & actions */
    .two-col{display:grid;grid-template-columns:1fr 1fr;gap:18px;margin-top:18px}
    @media (max-width:880px){.two-col{grid-template-columns:1fr}}
    .menu-item{display:flex;justify-content:space-between;align-items:center;padding:10px;border-radius:10px;background:linear-gradient(180deg,#07111b,transparent);border:1px solid rgba(255,255,255,0.03)}
    .menu-item h4{margin:0;color:#fff}
    .menu-item p{margin:4px 0 0;color:#9aa6b2;font-size:0.92rem}
    .price{font-weight:700;color:var(--accent)}
    .btn{background:var(--accent);border:none;color:#08101a;padding:10px 12px;border-radius:10px;font-weight:700;cursor:pointer}
    .outline{background:transparent;border:1px solid rgba(255,255,255,0.06);color:var(--muted);padding:8px 10px;border-radius:10px;cursor:pointer}

    /* right column */
    .card-small{background:linear-gradient(180deg,rgba(255,255,255,0.02),transparent);padding:12px;border-radius:12px;border:1px solid rgba(255,255,255,0.03)}
    .cart-list{max-height:260px;overflow:auto;margin-top:8px}
    .cart-row{display:flex;justify-content:space-between;gap:8px;padding:8px;border-bottom:1px dashed rgba(255,255,255,0.02)}

    /* forms */
    form{display:grid;gap:8px}
    label{font-size:0.9rem;color:#cbd5e1}
    input,select,textarea{padding:10px;border-radius:8px;border:1px solid rgba(255,255,255,0.06);background:transparent;color:var(--muted);outline:none}
    .small{font-size:0.9rem;color:#9aa6b2}

    /* BMC link */
    .bmc-link{display:inline-block;margin-top:12px;text-decoration:none;color:var(--accent);font-weight:700}

    footer{margin-top:28px;text-align:center;color:#93a4b8;font-size:0.95rem}

    /* modal */
    .modal{position:fixed;inset:0;display:none;align-items:center;justify-content:center;background:linear-gradient(rgba(2,6,23,0.6),rgba(2,6,23,0.8));z-index:60}
    .modal.show{display:flex}
    .modal-card{background:#07111b;padding:18px;border-radius:12px;width:520px;border:1px solid rgba(255,255,255,0.04)}

    /* fun accents */
    .spark{display:inline-block;background:linear-gradient(90deg,#ffd166,#ff6b35);padding:6px 10px;border-radius:999px;color:#07111b;font-weight:700}
    .tagline{margin-top:8px;color:#cbd5e1}
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="logo">FuelUp</div>
      <div style="flex:1">
        <h1>FuelUp Café — Campus Food Truck</h1>
        <p class="lead">Healthy • 100% Vegetarian • Student-run</p>
      </div>
      <div style="text-align:right">
        <div class="spark">Order • Reserve • Book Seats</div>
        <div class="sub" style="margin-top:6px">Fresh food, fast service — fuel your success!</div>
      </div>
    </header>

    <section class="hero">
      <div class="glass-card">
        <div class="big-phrase">Delicious. Nutritious. On-the-go.</div>
        <p class="sub">"FuelUp" brings student-loved vegetarian meals right to your campus gate. Grab a quick bite between lectures or book a cozy table for group study sessions.</p>

        <div style="margin-top:14px" class="two-col">
          <div class="card-small">
            <h3 style="color:#fff;margin:0">Menu Highlights</h3>
            <div style="margin-top:8px">
              <div class="menu-item">
                <div>
                  <h4>Paneer Tikka Wrap</h4>
                  <p>Grilled paneer, fresh veggies, mint chutney</p>
                </div>
                <div style="text-align:right">
                  <div class="price">₹85</div>
                  <button class="btn" onclick="addToCart('Paneer Tikka Wrap',85)">Add</button>
                </div>
              </div>

              <div class="menu-item" style="margin-top:8px">
                <div>
                  <h4>FuelUp Energy Bowl</h4>
                  <p>Oats, yogurt, seasonal fruits & dry fruits</p>
                </div>
                <div style="text-align:right">
                  <div class="price">₹75</div>
                  <button class="btn" onclick="addToCart('FuelUp Energy Bowl',75)">Add</button>
                </div>
              </div>

              <div class="menu-item" style="margin-top:8px">
                <div>
                  <h4>Veggie Grilled Burger</h4>
                  <p>House-made patty, fresh slaw, mint mayo</p>
                </div>
                <div style="text-align:right">
                  <div class="price">₹95</div>
                  <button class="btn" onclick="addToCart('Veggie Grilled Burger',95)">Add</button>
                </div>
              </div>

              <div class="menu-item" style="margin-top:8px">
                <div>
                  <h4>Masala Maggie Bowl</h4>
                  <p>Masala noodles with veggies & peanuts</p>
                </div>
                <div style="text-align:right">
                  <div class="price">₹40</div>
                  <button class="btn" onclick="addToCart('Masala Maggie Bowl',40)">Add</button>
                </div>
              </div>

            </div>

            <a class="bmc-link" href="#bmc">View Business Model Canvas »</a>
          </div>

          <div class="card-small">
            <h3 style="color:#fff;margin:0">Quick Actions</h3>
            <div style="margin-top:8px" class="small">Place order online for pickup or reserve a seat for a study group. No backend required — data stored locally.</div>

            <div style="margin-top:12px">
              <button class="btn" onclick="openModal('order')">Place Order</button>
              <button class="outline" style="margin-left:8px" onclick="openModal('reserve')">Reserve / Book Seats</button>
            </div>

            <div style="margin-top:12px">
              <h4 style="color:#fff;margin:0">Cart</h4>
              <div class="cart-list" id="cart"></div>
              <div style="margin-top:8px;display:flex;justify-content:space-between;align-items:center"><div class="small">Total:</div><div id="total" style="font-weight:700;color:var(--accent)">₹0</div></div>
              <div style="margin-top:10px"><button class="btn" onclick="checkout()">Checkout (Save Order)</button></div>
            </div>
          </div>
        </div>
      </div>

      <div>
        <div class="glass-card">
          <h3 style="margin:0;color:#fff">Why FuelUp?</h3>
          <p class="tagline">Smart pricing • Student-run • Eco-friendly packaging • Fresh local ingredients</p>

          <div style="margin-top:12px">
            <h4 style="margin:0;color:#fff">Reservation & Events</h4>
            <p class="small">Reserve a table for a team meeting or book seats during college fests. Flexible slots and group discounts available.</p>
            <button class="btn" style="margin-top:8px" onclick="openModal('booking')">Book Seats for Event</button>
          </div>
        </div>

        <div style="height:14px"></div>

        <div class="glass-card">
          <h4 style="margin:0;color:#fff">Contact</h4>
          <p class="small">Email: fuelup@campus.example • Phone: +91 90000 00000</p>
          <p class="small">Follow us: Instagram @fuelup_cafe</p>
        </div>
      </div>
    </section>

    <!-- BMC compact -->
    <section id="bmc" style="margin-top:18px">
      <div class="glass-card">
        <h2 style="margin:0;color:#fff">Business Model Canvas</h2>
        <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-top:12px">
          <div style="background:rgba(255,255,255,0.02);padding:10px;border-radius:8px">
            <h4 style="color:#fff;margin:0">Key Partners</h4>
            <p class="small">Local suppliers • College admin • FSSAI • Eco-pack vendors • Student volunteers</p>
          </div>
          <div style="background:rgba(255,255,255,0.02);padding:10px;border-radius:8px">
            <h4 style="color:#fff;margin:0">Key Activities</h4>
            <p class="small">Food prep • Marketing • Inventory • Event catering • Hygiene compliance</p>
          </div>
          <div style="background:rgba(255,255,255,0.02);padding:10px;border-radius:8px">
            <h4 style="color:#fff;margin:0">Value Proposition</h4>
            <p class="small">Healthy, affordable veg meals; student-run; eco-conscious</p>
          </div>
        </div>
      </div>
    </section>

    <footer>
      <div>Designed for: College Entrepreneurship Report • FuelUp Café</div>
      <div style="margin-top:6px;color:#7f9bb0">Data here is stored locally in your browser (no server). Use the page as a demo prototype.</div>
    </footer>
  </div>

  <!-- modal dialogs -->
  <div id="modal" class="modal">
    <div class="modal-card" id="modalCard">
      <div style="display:flex;justify-content:space-between;align-items:center">
        <h3 id="modalTitle" style="margin:0;color:#fff">Modal</h3>
        <button class="outline" onclick="closeModal()">Close</button>
      </div>

      <div id="modalBody" style="margin-top:12px;color:var(--muted)"></div>
    </div>
  </div>

  <script>
    // Simple client-side cart, order, reservation & booking system (localStorage)
    let cart = JSON.parse(localStorage.getItem('fuelup_cart')||'[]');
    const cartEl = document.getElementById('cart');
    const totalEl = document.getElementById('total');

    function renderCart(){
      cartEl.innerHTML = '';
      let total = 0;
      if(cart.length===0){cartEl.innerHTML='<div class="small">Cart is empty</div>'}
      cart.forEach((it,idx)=>{
        const row = document.createElement('div');row.className='cart-row';
        row.innerHTML = `<div style="flex:1"><div style=\"color:#fff;font-weight:600\">${it.name}</div><div class=\"small\">Qty: ${it.qty}</div></div><div style=\"text-align:right\">₹${it.price*it.qty}<div style=\"margin-top:6px\"><button class=\"outline\" onclick=\"removeItem(${idx})\">Remove</button></div></div>`;
        cartEl.appendChild(row);
        total += it.price*it.qty;
      })
      totalEl.innerText = '₹'+total;
    }
    renderCart();

    function addToCart(name,price){
      const existing = cart.find(c=>c.name===name);
      if(existing){existing.qty +=1}else{cart.push({name,price,qty:1})}
      localStorage.setItem('fuelup_cart',JSON.stringify(cart));
      renderCart();
      alert(name+ ' added to cart');
    }
    function removeItem(i){cart.splice(i,1);localStorage.setItem('fuelup_cart',JSON.stringify(cart));renderCart();}

    function openModal(type){
      const modal = document.getElementById('modal');const title = document.getElementById('modalTitle');const body = document.getElementById('modalBody');
      if(type==='order'){
        title.innerText='Place Your Order';
        body.innerHTML = `
          <div class="small">Review your cart and enter pickup details.</div>
          <div style="margin-top:8px"><strong>Items:</strong></div>
          <div id="orderItems" style="max-height:140px;overflow:auto;margin-top:6px"></div>
          <label>Name</label><input id="orderName" placeholder="Your name" />
          <label>Contact</label><input id="orderContact" placeholder="Phone or email" />
          <label>Pickup time</label><input id="orderTime" type="time" />
          <div style="margin-top:8px"><button class="btn" onclick="saveOrder()">Save Order</button></div>
        `;
        // populate items
        const orderItems = cart.map(i=>`${i.qty} x ${i.name} — ₹${i.price*i.qty}`).join('<br>')||'<div class="small">No items yet</div>';
        setTimeout(()=>{document.getElementById('orderItems').innerHTML=orderItems},80);
      }else if(type==='reserve'){
        title.innerText='Reserve a Table';
        body.innerHTML = `
          <div class="small">Reserve a table for group study or meetings. Max 6 per table.</div>
          <label>Full Name</label><input id="resName" placeholder="Your name" />
          <label>Contact</label><input id="resContact" placeholder="Phone or email" />
          <label>Date</label><input id="resDate" type="date" />
          <label>Time</label><input id="resTime" type="time" />
          <label>Guests</label><select id="resGuests"><option>1</option><option>2</option><option>3</option><option>4</option><option>5</option><option>6</option></select>
          <div style="margin-top:8px"><button class="btn" onclick="saveReservation()">Save Reservation</button></div>
        `;
      }else if(type==='booking'){
        title.innerText='Book Seats for Event';
        body.innerHTML = `
          <div class="small">Book multiple seats for campus events or fest stalls.</div>
          <label>Contact Person</label><input id="bookName" placeholder="Name" />
          <label>Contact</label><input id="bookContact" placeholder="Phone or email" />
          <label>Event Date</label><input id="bookDate" type="date" />
          <label>Number of Seats</label><input id="bookSeats" type="number" min="1" max="200" value="4" />
          <div style="margin-top:8px"><button class="btn" onclick="saveBooking()">Confirm Booking</button></div>
        `;
      }
      modal.classList.add('show');
    }
    function closeModal(){document.getElementById('modal').classList.remove('show')}

    function saveOrder(){
      const name=document.getElementById('orderName').value.trim();
      const contact=document.getElementById('orderContact').value.trim();
      const time=document.getElementById('orderTime').value;
      if(!name||!contact){alert('Please enter name and contact');return}
      const orders = JSON.parse(localStorage.getItem('fuelup_orders')||'[]');
      orders.push({id:Date.now(),name,contact,time,items:cart});
      localStorage.setItem('fuelup_orders',JSON.stringify(orders));
      // clear cart
      cart=[];localStorage.setItem('fuelup_cart',JSON.stringify(cart));renderCart();
      alert('Order saved locally — show this confirmation at pickup.');
      closeModal();
    }

    function saveReservation(){
      const name=document.getElementById('resName').value.trim();
      const contact=document.getElementById('resContact').value.trim();
      const date=document.getElementById('resDate').value; const time=document.getElementById('resTime').value; const guests=document.getElementById('resGuests').value;
      if(!name||!contact||!date||!time){alert('Please complete required fields');return}
      const res = JSON.parse(localStorage.getItem('fuelup_reservations')||'[]');
      res.push({id:Date.now(),name,contact,date,time,guests});
      localStorage.setItem('fuelup_reservations',JSON.stringify(res));
      alert('Reservation saved locally. Present your name at FuelUp on arrival.');
      closeModal();
    }

    function saveBooking(){
      const name=document.getElementById('bookName').value.trim();
      const contact=document.getElementById('bookContact').value.trim();
      const date=document.getElementById('bookDate').value; const seats=document.getElementById('bookSeats').value;
      if(!name||!contact||!date||!seats){alert('Please complete required fields');return}
      const bk = JSON.parse(localStorage.getItem('fuelup_bookings')||'[]');
      bk.push({id:Date.now(),name,contact,date,seats});
      localStorage.setItem('fuelup_bookings',JSON.stringify(bk));
      alert('Booking confirmed locally. Arrive early to claim seats.');
      closeModal();
    }

    function checkout(){
      if(cart.length===0){alert('Cart empty');return}
      openModal('order');
    }

    // quick demo: load sample data if empty
    if(!localStorage.getItem('fuelup_cart')) localStorage.setItem('fuelup_cart',JSON.stringify([]));
    if(!localStorage.getItem('fuelup_orders')) localStorage.setItem('fuelup_orders',JSON.stringify([]));
    if(!localStorage.getItem('fuelup_reservations')) localStorage.setItem('fuelup_reservations',JSON.stringify([]));
    if(!localStorage.getItem('fuelup_bookings')) localStorage.setItem('fuelup_bookings',JSON.stringify([]));

    // keyboard ESC to close modal
    document.addEventListener('keydown',e=>{if(e.key==='Escape')closeModal()});
  </script>
</body>
</html>
