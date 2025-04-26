# Gadget-web-<!DOCTYPE html>
<html lang="bn">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Airpod Pro অর্ডার করুন</title>
  <style>
    body {
      font-family: 'Helvetica', sans-serif;
      margin: 0;
      padding: 0;
      background: #f2f2f2;
    }
    .container {
      max-width: 600px;
      margin: 20px auto;
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    }
    img {
      width: 100%;
      border-radius: 10px;
      margin-bottom: 20px;
    }
    h1 {
      text-align: center;
      color: #333;
    }
    p {
      text-align: center;
      font-size: 18px;
      color: #555;
    }
    form {
      display: flex;
      flex-direction: column;
      margin-top: 20px;
    }
    input, textarea {
      margin-bottom: 15px;
      padding: 12px;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      padding: 15px;
      background: #28a745;
      color: white;
      font-size: 18px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background: #218838;
    }
    .thank-you {
      display: none;
      text-align: center;
      font-size: 20px;
      color: green;
      margin-top: 20px;
    }
  </style>
</head>
<body>

<div class="container">
  <h1>Airpod Pro ব্লুটুথ হেডফোন</h1>
  <img src="https://images.unsplash.com/photo-1606813903277-0c2f62ce4a29?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=60" alt="Airpod Pro 2">
  <p><strong>দাম:</strong> মাত্র ৪৫০ টাকা!</p>
  <p>সীমিত সময়ের জন্য অফার! দ্রুত অর্ডার করুন।</p>

  <form action="https://formspree.io/f/mayvpkzw" method="POST" id="orderForm">
    <input type="text" name="name" placeholder="আপনার নাম লিখুন" required>
    <input type="tel" name="phone" placeholder="মোবাইল নাম্বার লিখুন" required>
    <textarea name="address" placeholder="আপনার সম্পূর্ণ ঠিকানা লিখুন" required></textarea>
    <button type="submit">এখন অর্ডার করুন</button>
  </form>

  <div class="thank-you" id="thankYouMessage">
    ধন্যবাদ! আপনার অর্ডার গ্রহণ করা হয়েছে।
  </div>
</div>

<script>
  const form = document.getElementById('orderForm');
  const thankYouMessage = document.getElementById('thankYouMessage');

  form.addEventListener('submit', function(event) {
    event.preventDefault();
    const formData = new FormData(form);

    fetch(form.action, {
      method: "POST",
      body: formData,
      headers: {
        'Accept': 'application/json'
      }
    }).then(response => {
      if (response.ok) {
        form.style.display = 'none';
        thankYouMessage.style.display = 'block';
      } else {
        alert('অর্ডার পাঠানো যায়নি, আবার চেষ্টা করুন।');
      }
    }).catch(error => {
      alert('সার্ভারে সমস্যা হয়েছে!');
    });
  });
</script>

</body>
</html>
