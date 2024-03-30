<!DOCTYPE html>
<html>
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sign in and Sign up form</title>
    <link rel="stylesheet" href="style.css">
    <script src="https://kit.fontawesome.com/5f5717a14e.js" crossorigin="anonymous"></script>
</head>
<body>
    <div class="container">
        <div class="form-box">
            <h1 id="title">Sign up</h1>
            <form id="signupForm">
                <div class="input-group">
                    <div class="input-field" id="nameField">
                        <i class="fa-solid fa-user-pen"></i>
                        <input type="text" id="name" placeholder="Name" required>
                    </div>
                    <div class="input-field">
                        <i class="fa-solid fa-envelope"></i>
                        <input type="email" id="email" placeholder="Email" required>
                    </div>
                    <div class="input-field">
                        <i class="fa-solid fa-lock"></i>
                        <input type="password" id="password" placeholder="Password" required>
                    </div>
                    <div class="input-field" id="phoneField">
                        <i class="fa-solid fa-phone"></i>
                        <input type="text" id="phone" placeholder="phone number"required>
                    </div>
                    <div class="input-field" id="genderfield">
                        
                    <label for="male">male</label>
                    <input type="radio" name="gender" id="male" value="male"><br>
                    <label for="female">female</label>
                    <input type="radio" name="gender" id="female" value="female"><br>
</div>
<div class="input-field" id="agefield">
    <label for="age-group">select your age group</label>
    <select name="   " id="age-group">
        <option value="5-10">5-10</option>
        <option value="11-20">11-21</option>
        <option value="21-50">21-50</option>
        <option value="50+">50+</option>

    </select>
                </div>
                <p> Lost password <a href="#">Click here!</a></p>
                <div class="btn-field">
                    <button type="button" id="signupBtn">Sign up</button>
                    <button type="button" id="signinBtn" class="disable">Sign in</button>
                </div>
            </form>
        </div>
    </div>

    <script>
        let signupBtn = document.getElementById("signupBtn");
        let signinBtn = document.getElementById("signinBtn");
        let nameField = document.getElementById("nameField");
        let phoneField = document.getElementById("phoneField");
        let agefield = document.getElementById("agefield");
        let genderfield = document.getElementById("genderfield");
        
        let title = document.getElementById("title");
        let signupForm = document.getElementById("signupForm");

        signinBtn.onclick = function(){
            nameField.style.maxHeight = "0";
            phoneField.style.maxHeight = "0";
            agefield.style.maxHeight = "0";
            genderfield.style.maxHeight = "0";
            title.innerHTML = "Sign In";
            signupBtn.classList.remove("disable");
            signinBtn.classList.add("disable");
            signupBtn.classList.remove("disable");
            signinBtn.classList.add("disable");
        }

        signupBtn.onclick = function(){
            nameField.style.maxHeight = "60px";
            phoneField.style.maxHeight = "60px";
            agefield.style.maxHeight = "60px";
            genderfield.style.maxHeight = "60px";
            title.innerHTML = "Sign Up";
            signupBtn.classList.add("disable");
            signinBtn.classList.remove("disable");
        }

        signupForm.addEventListener("submit", function(event) {
            if (!validateForm()) {
                event.preventDefault(); // Prevents form submission if validation fails
            }
        });

        function validateForm() {
            let name = document.getElementById("name").value;
            let email = document.getElementById("email").value;
            let password = document.getElementById("password").value;

            if (name.trim() === "" || email.trim() === "" || password.trim() === "") {
                alert("All fields must be filled out");
                return false;
            }

            // You can add more specific validation logic for email and password if needed

            return true;
        }
    </script>
</body>
</html>
