/>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Helping Hands You Can Count On</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      background-color: #e0f7f7;
      color: #054d4d;
    }
    header {
      text-align: center;
      padding: 50px 20px;
      background-color: #b2ebeb;
    }
    header h1 {
      font-size: 2.5em;
      margin-bottom: 10px;
    }
    header p {
      font-size: 1.2em;
      margin-top: 0;
    }
    section {
      max-width: 900px;
      margin: auto;
      padding: 40px 20px;
    }
    .services {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
    }
    .service-card {
      background-color: white;
      border-radius: 10px;
      padding: 20px;
      box-shadow: 0 4px 6px rgba(0,0,0,0.1);
      text-align: center;
      cursor: pointer;
      transition: box-shadow 0.3s ease;
    }
    .service-card:hover {
      box-shadow: 0 6px 12px rgba(0,0,0,0.2);
    }
    .service-card h3 {
      margin-top: 0;
      color: #008080;
    }
    .price {
      font-size: 1.5em;
      color: #008080;
      margin-top: 10px;
    }
    .contact {
      text-align: center;
      background-color: #b2ebeb;
      padding: 30px 20px;
      margin-top: 30px;
    }
    a.button {
      display: inline-block;
      margin-top: 15px;
      background-color: #008080;
      color: white;
      padding: 10px 20px;
      border-radius: 5px;
      text-decoration: none;
    }
    a.button:hover {
      background-color: #006666;
    }
  </style>
</head>
<body>

  <header>
    <h1>Helping Hands You Can Count On</h1>
    <p>Reliable help for your home, yard, and pets in Montreal</p>
    <a href="#contact" class="button">Contact Me</a>
  </header>

  <section id="about">
    <h2>About Me</h2>
    <p>Hi, I’m Zae, a responsible and motivated 14-year-old 
      boy offering trustworthy and quality help to my community. Whether you need someone to walk your dog, help with yard work, or tackle household chores, I’m here to make your life easier.</p>
  </section>

  <section id="services">
    <h2>Services & Prices</h2>
    <div class="services">
      <div class="service-card" data-service="dogWalking">
        <h3>Dog Walking</h3>
        <p>Daily walks, exercise, and care for your furry friends.</p>
        <div class="price">$20</div>
      </div>
      <div class="service-card" data-service="householdChores">
        <h3>Household Chores</h3>
        <p>Cleaning, organizing, and helping keep your home tidy.</p>
        <div class="price">$25</div>
      </div>
      <div class="service-card" data-service="yardWork">
        <h3>Yard Work</h3>
        <p>Mowing, raking, watering, and general garden maintenance.</p>
        <div class="price">$45</div>
      </div>
      <div class="service-card" data-service="carWashing">
        <h3>Professional Car Washing</h3>
        <p>Exterior and interior car cleaning with professional care.</p>
        <div class="price">$50</div>
      </div>
    </div>
  </section>

  <section id="contact" class="contact">
    <h2>Contact Me</h2>
    <p>Email: <a href="mailto:kyiuswoolcock@gmail.com">kyiuswoolcock@gmail.com</a></p>
  </section>

<script>
  // Service details content
  const serviceDetails = {
    dogWalking: {
      title: "Dog Walking",
      content: <p>Daily walks, exercise, and care for your furry friends. I ensure your dog gets enough physical activity and companionship during walks, tailored to their needs and temperament.</p>
                <p>I am responsible, punctual, and will treat your pets like my own.</p>
    },
    householdChores: {
      title: "Household Chores",
      content: <p>Cleaning, organizing, and helping keep your home tidy. I assist with dusting, vacuuming, washing dishes, laundry, and other chores to make your home comfortable and neat.</p>
                <p>Reliable and thorough service every time.</p>
    },
    yardWork: {
      title: "Yard Work",
      content: <p>Mowing, raking, watering, and general garden maintenance. I can help keep your outdoor space neat and healthy.</p>
                <p>Friendly and efficient service to maintain your yard all season long.</p>
    },
    carWashing: {
      title: "Professional Car Washing",
      content: <p>Exterior and interior car cleaning with professional care. I use quality products to make your vehicle shine inside and out.</p>
                <p>Affordable and detail-oriented service for your car.</p>
    }
  };

  // Function to open new tab with service detail
  function openServiceDetail(serviceKey) {
    const detail = serviceDetails[serviceKey];
    if (!detail) return;

    const html = 
      <!DOCTYPE html>
      <html lang="en">
      <head>
        <meta charset="UTF-8" />
        <title>${detail.title} - Helping Hands</title>
        <style>
          body { font-family: Arial, sans-serif; margin: 40px; background-color: #e0f7f7; color: #054d4d; }
          h1 { color: #008080; }
          a { color: #008080; text-decoration: none; }
          a:hover { text-decoration: underline; }
        </style>
      </head>
      <body>
        <h1>${detail.title}</h1>
        ${detail.content}
        <p><a href="javascript:window.close()">Close this tab</a></p>
      </body>
      </html>
    ;

    const newWindow = window.open();
    newWindow.document.write(html);
    newWindow.document.close();
  }

  // Attach event listeners to service cards
  document.querySelectorAll('.service-card').forEach(card => {
    card.addEventListener('click', () => {
      const serviceKey = card.getAttribute('data-service');
      openServiceDetail(serviceKey);
    });
  });
</script>

</body>
</html>
