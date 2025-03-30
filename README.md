# feb-2025-avasjcript-events-and-basic-interactivity

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Webpage</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; padding: 20px; }
        .hidden { display: none; }
        .error { color: red; }
    </style>
</head>
<body>
    <h1>JavaScript Interactive Webpage</h1>
    
    <!-- Interactive Button -->
    <button id="changeTextBtn">Click Me!</button>
    <p id="text">This text will change!</p>
    
    <!-- Form with Validation -->
    <form id="myForm">
        <label for="email">Email:</label>
        <input type="email" id="email" placeholder="Enter your email">
        <span class="error hidden" id="emailError">Invalid email!</span>
        <br><br>
        
        <label for="password">Password:</label>
        <input type="password" id="password">
        <button type="button" id="togglePassword">Show/Hide</button>
        <br><br>
        
        <button type="submit">Submit</button>
    </form>
    
    <script>
        // Event Listener to Change Text
        document.getElementById("changeTextBtn").addEventListener("click", function() {
            document.getElementById("text").textContent = "You clicked the button!";
        });

        // Toggle Password Visibility
        document.getElementById("togglePassword").addEventListener("click", function() {
            let passwordField = document.getElementById("password");
            passwordField.type = passwordField.type === "password" ? "text" : "password";
        });

        // Form Validation
        document.getElementById("myForm").addEventListener("submit", function(event) {
            let email = document.getElementById("email").value;
            let emailError = document.getElementById("emailError");
            let emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            
            if (!emailRegex.test(email)) {
                emailError.classList.remove("hidden");
                event.preventDefault(); // Prevent form submission
            } else {
                emailError.classList.add("hidden");
            }
        });
    </script>
</body>
</html>
