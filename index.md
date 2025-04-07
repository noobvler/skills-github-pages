---
title: Welcome to my blog
---
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Supabase Website</title>
  <link rel="stylesheet" href="styles.css">
  <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2.0.0/dist/umd/supabase.min.js"></script>
</head>
<body>
  <h1>Welcome to my Supabase App</h1>

  <!-- Form for user authentication -->
  <div id="login-form">
    <input type="email" id="email" placeholder="Email">
    <input type="password" id="password" placeholder="Password">
    <button onclick="login()">Login</button>
  </div>

  <script>
    // Supabase client setup
    const supabaseUrl = 'https://curtpsmoagjqlgtxqmry.supabase.co'; // Your Supabase URL
    const supabaseKey = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImN1cnRwc21vYWdqcWxndHhxbXJ5Iiwicm9sZSI6ImFub24iLCJpYXQiOjE3NDQwMTk5NDIsImV4cCI6MjA1OTU5NTk0Mn0.vP9Szxmoic63Z7XYNmqxfq1jrVnKTO1UkRFDrXH8YbA'; // Your Supabase Anon key
    const supabase = supabase.createClient(supabaseUrl, supabaseKey);

    async function login() {
      const { user, error } = await supabase.auth.signIn({
        email: document.getElementById('email').value,
        password: document.getElementById('password').value
      });

      if (error) {
        alert('Error: ' + error.message);
      } else {
        alert('Welcome ' + user.email);
      }
    }
  </script>
</body>
</html>

