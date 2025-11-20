<!-- SIGNUP BOX -->
<div class="signup-box">
  <h2>Create Your Account</h2>

  <input type="text" id="name" placeholder="Full Name" />
  <input type="email" id="email" placeholder="Email Address" />
  <input type="text" id="player" placeholder="Favorite Knicks Player" />
  <input type="password" id="password" placeholder="Create Password" />

  <button class="btn" id="joinBtn">Join Now</button>
  
  <p id="successMsg" style="color:green; margin-top:15px; display:none;">Thank you! Your account has been created.</p>
</div>

<script>
  const joinBtn = document.getElementById("joinBtn");
  const successMsg = document.getElementById("successMsg");

  joinBtn.addEventListener("click", () => {
    // Get input values
    const name = document.getElementById("name").value.trim();
    const email = document.getElementById("email").value.trim();
    const player = document.getElementById("player").value.trim();
    const password = document.getElementById("password").value.trim();

    // Simple validation
    if (!name || !email || !player || !password) {
      alert("Please fill out all fields!");
      return;
    }

    // Save data locally (for demo purposes)
    const userData = { name, email, player, password };
    let users = JSON.parse(localStorage.getItem("knicksUsers") || "[]");
    users.push(userData);
    localStorage.setItem("knicksUsers", JSON.stringify(users));

    // Show success message
    successMsg.style.display = "block";

    // Clear inputs
    document.getElementById("name").value = "";
    document.getElementById("email").value = "";
    document.getElementById("player").value = "";
    document.getElementById("password").value = "";
  });
</script>

