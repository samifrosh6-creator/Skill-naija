# Skill-naija
A Nigerian platform connecting people with jobs and skilled workers
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SkillNaija</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #f5f7f6;
      color: #17221b;
    }

    header {
      background: #0b7a3b;
      color: white;
      padding: 25px 20px;
      text-align: center;
    }

    header h1 {
      margin: 0;
      font-size: 32px;
    }

    header p {
      margin: 8px 0 0;
    }

    .container {
      max-width: 650px;
      margin: auto;
      padding: 25px 20px;
    }

    .search {
      width: 100%;
      padding: 16px;
      border: 1px solid #ddd;
      border-radius: 12px;
      font-size: 16px;
      margin-bottom: 15px;
    }

    .button {
      width: 100%;
      padding: 17px;
      border: none;
      border-radius: 12px;
      margin: 7px 0;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
    }

    .job {
      background: white;
      color: #0b7a3b;
      border: 2px solid #0b7a3b;
    }

    .worker {
      background: #17221b;
      color: white;
    }

    .login-btn {
      background: #0b7a3b;
      color: white;
    }

    .register-btn {
      background: #e9f4ed;
      color: #0b7a3b;
    }

    h2 {
      margin-top: 30px;
    }

    .skills {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
    }

    .skill {
      background: white;
      padding: 20px 10px;
      text-align: center;
      border-radius: 12px;
      font-weight: bold;
      cursor: pointer;
      box-shadow: 0 2px 8px rgba(0,0,0,0.05);
    }

    .page {
      display: none;
    }

    .page.active {
      display: block;
    }

    .card {
      background: white;
      padding: 25px 20px;
      border-radius: 15px;
      box-shadow: 0 3px 12px rgba(0,0,0,0.07);
    }

    .card h2 {
      margin-top: 0;
      color: #0b7a3b;
    }

    label {
      display: block;
      margin-top: 15px;
      margin-bottom: 6px;
      font-weight: bold;
    }

    input,
    select {
      width: 100%;
      padding: 14px;
      border: 1px solid #ddd;
      border-radius: 10px;
      font-size: 15px;
    }

    .back {
      background: transparent;
      border: none;
      color: #0b7a3b;
      font-weight: bold;
      cursor: pointer;
      margin-bottom: 15px;
      font-size: 15px;
    }

    .account-choice {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
      margin: 20px 0;
    }

    .choice {
      padding: 20px 10px;
      border: 2px solid #ddd;
      background: white;
      border-radius: 12px;
      text-align: center;
      cursor: pointer;
      font-weight: bold;
    }

    .choice.selected {
      border-color: #0b7a3b;
      background: #e9f4ed;
      color: #0b7a3b;
    }

    .message {
      display: none;
      margin-top: 15px;
      padding: 12px;
      border-radius: 8px;
      background: #e8f5ee;
      color: #0b7a3b;
    }

    .small-text {
      text-align: center;
      margin-top: 18px;
      font-size: 14px;
    }

    .link {
      color: #0b7a3b;
      font-weight: bold;
      cursor: pointer;
    }

    .profile {
      text-align: center;
      padding: 15px;
      background: #e9f4ed;
      border-radius: 12px;
      margin-bottom: 20px;
    }
  </style>
</head>

<body>

<header>
  <h1>SKILLNAIJA 🇳🇬</h1>
  <p>Skills. Jobs. Opportunities.</p>
</header>


<!-- ================= HOME PAGE ================= -->

<div id="homePage" class="page active">

  <div class="container">

    <button class="button login-btn" onclick="showPage('loginPage')">
      🔐 LOGIN
    </button>

    <button class="button register-btn" onclick="showPage('registerPage')">
      👤 CREATE ACCOUNT
    </button>

    <input
      id="search"
      class="search"
      type="text"
      placeholder="🔎 Search jobs, skills or workers..."
    >

    <button class="button job" onclick="showJobs()">
      💼 FIND A JOB
    </button>

    <button class="button worker" onclick="showWorkers()">
      🛠️ FIND A WORKER
    </button>

    <h2>🔥 Popular Skills</h2>

    <div class="skills">

      <div class="skill" onclick="searchSkill('Electrician')">
        ⚡ Electrician
      </div>

      <div class="skill" onclick="searchSkill('Plumber')">
        🚰 Plumber
      </div>

      <div class="skill" onclick="searchSkill('Carpenter')">
        🔨 Carpenter
      </div>

      <div class="skill" onclick="searchSkill('Solar')">
        ☀️ Solar
      </div>

      <div class="skill" onclick="searchSkill('Mechanic')">
        🚗 Mechanic
      </div>

      <div class="skill" onclick="searchSkill('Cleaner')">
        🧹 Cleaner
      </div>

    </div>

  </div>

</div>


<!-- ================= LOGIN PAGE ================= -->

<div id="loginPage" class="page">

  <div class="container">

    <button class="back" onclick="showPage('homePage')">
      ← Back to Home
    </button>

    <div class="card">

      <h2>🔐 Login to SkillNaija</h2>

      <label>Phone Number or Email</label>
      <input
        id="loginEmail"
        type="text"
        placeholder="Enter phone or email"
      >

      <label>Password</label>
      <input
        id="loginPassword"
        type="password"
        placeholder="Enter password"
      >

      <button class="button login-btn" onclick="login()">
        LOGIN
      </button>

      <p class="small-text">
        Don't have an account?
        <span class="link" onclick="showPage('registerPage')">
          Create one
        </span>
      </p>

      <div id="loginMessage" class="message"></div>

    </div>

  </div>

</div>


<!-- ================= REGISTER PAGE ================= -->

<div id="registerPage" class="page">

  <div class="container">

    <button class="back" onclick="showPage('homePage')">
      ← Back to Home
    </button>

    <div class="card">

      <h2>👤 Create Your Account</h2>

      <p>What are you looking for?</p>

      <div class="account-choice">

        <div
          id="workerChoice"
          class="choice"
          onclick="selectAccount('worker')"
        >
          🛠️<br>
          I'm a Worker
        </div>

        <div
          id="customerChoice"
          class="choice"
          onclick="selectAccount('customer')"
        >
          💼<br>
          I Need a Worker
        </div>

      </div>

      <form onsubmit="register(event)">

        <label>Full Name</label>
        <input
          id="fullName"
          type="text"
          placeholder="Enter your full name"
          required
        >

        <label>Phone Number</label>
        <input
          id="phone"
          type="tel"
          placeholder="08012345678"
          required
        >

        <label>Email</label>
        <input
          id="email"
          type="email"
          placeholder="example@email.com"
          required
        >

        <div id="workerFields" style="display:none;">

          <label>Your Skill</label>

          <select id="skill">
            <option value="">Select your skill</option>
            <option>Electrician</option>
            <option>Plumber</option>
            <option>Carpenter</option>
            <option>Solar Technician</option>
            <option>Mechanic</option>
            <option>Cleaner</option>
            <option>Painter</option>
            <option>Welder</option>
            <option>Tailor</option>
            <option>Other</option>
          </select>

          <label>Location</label>
          <input
            id="location"
            type="text"
            placeholder="e.g. Port Harcourt"
          >

          <label>Years of Experience</label>
          <input
            id="experience"
            type="number"
            min="0"
            placeholder="e.g. 5"
          >

        </div>

        <label>Password</label>
        <input
          id="registerPassword"
          type="password"
          placeholder="Create a password"
          required
        >

        <label>Confirm Password</label>
        <input
          id="confirmPassword"
          type="password"
          placeholder="Confirm password"
          required
        >

        <button class="button register-btn" type="submit">
          CREATE ACCOUNT
        </button>

      </form>

      <p class="small-text">
        Already have an account?
        <span class="link" onclick="showPage('loginPage')">
          Login
        </span>
      </p>

      <div id="registerMessage" class="message"></div>

    </div>

  </div>

</div>


<!-- ================= JAVASCRIPT ================= -->

<script>

  let accountType = "";

  function showPage(pageId) {

    document.querySelectorAll(".page").forEach(function(page) {
      page.classList.remove("active");
    });

    document.getElementById(pageId).classList.add("active");

    window.scrollTo({
      top: 0,
      behavior: "smooth"
    });
  }


  function selectAccount(type) {

    accountType = type;

    document.getElementById("workerChoice")
      .classList.remove("selected");

    document.getElementById("customerChoice")
      .classList.remove("selected");

    if (type === "worker") {

      document.getElementById("workerChoice")
        .classList.add("selected");

      document.getElementById("workerFields")
        .style.display = "block";

    } else {

      document.getElementById("customerChoice")
        .classList.add("selected");

      document.getElementById("workerFields")
        .style.display = "none";
    }
  }


  function register(event) {

    event.preventDefault();

    if (accountType === "") {

      showMessage(
        "registerMessage",
        "Please select whether you are a Worker or Customer."
      );

      return;
    }

    const password =
      document.getElementById("registerPassword").value;

    const confirmPassword =
      document.getElementById("confirmPassword").value;

    if (password !== confirmPassword) {

      showMessage(
        "registerMessage",
        "Passwords do not match."
      );

      return;
    }

    const user = {

      name: document.getElementById("fullName").value,

      phone: document.getElementById("phone").value,

      email: document.getElementById("email").value,

      password: password,

      type: accountType,

      skill: document.getElementById("skill").value,

      location: document.getElementById("location").value,

      experience: document.getElementById("experience").value
    };


    localStorage.setItem(
      "skillnaijaUser",
      JSON.stringify(user)
    );


    showMessage(
      "registerMessage",
      "🎉 Account created successfully! You can now login."
    );


    setTimeout(function() {
      showPage("loginPage");
    }, 1500);

  }


  function login() {

    const email =
      document.getElementById("loginEmail").value;

    const password =
      document.getElementById("loginPassword").value;

    const savedUser =
      JSON.parse(localStorage.getItem("skillnaijaUser"));


    if (!savedUser) {

      showMessage(
        "loginMessage",
        "No account found. Please create an account first."
      );

      return;
    }


    if (
      (email === savedUser.email ||
       email === savedUser.phone) &&
      password === savedUser.password
    ) {

      localStorage.setItem(
        "skillnaijaLoggedIn",
        "true"
      );

      showMessage(
        "loginMessage",
        "✅ Login successful! Welcome to SkillNaija."
      );


      setTimeout(function() {
        showDashboard(savedUser);
      }, 1000);

    } else {

      showMessage(
        "loginMessage",
        "❌ Incorrect phone/email or password."
      );

    }

  }


  function showDashboard(user) {

    document.querySelectorAll(".page").forEach(function(page) {
      page.classList.remove("active");
    });


    const dashboard =
      document.createElement("div");

    dashboard.id = "dashboardPage";
    dashboard.className = "page active";


    dashboard.innerHTML = `

      <div class="container">

        <div class="card">

          <div class="profile">

            <h2>👋 Welcome, ${user.name}</h2>

            <p>
              ${user.type === "worker"
                ? "🛠️ Worker Account"
                : "💼 Customer Account"}
            </p>

          </div>


          ${
            user.type === "worker"

            ?

            `
              <h3>🛠️ Your Worker Profile</h3>

              <p><strong>Skill:</strong>
                ${user.skill || "Not added"}
              </p>

              <p><strong>Location:</strong>
                ${user.location || "Not added"}
              </p>

              <p><strong>Experience:</strong>
                ${user.experience || "Not added"} years
              </p>

              <button
                class="button worker"
                onclick="alert('Worker profile editing will be added next.')"
              >
                ✏️ EDIT PROFILE
              </button>
            `

            :

            `
              <h3>💼 Find a Worker</h3>

              <p>
                Search for skilled workers near you.
              </p>

              <button
                class="button job"
                onclick="showPage('homePage')"
              >
                🔎 FIND WORKERS
              </button>
            `
          }


          <button
            class="button register-btn"
            onclick="logout()"
          >
            🚪 LOGOUT
          </button>

        </div>

      </div>
    `;


    document.body.appendChild(dashboard);

  }


  function logout() {

    localStorage.removeItem("skillnaijaLoggedIn");

    const dashboard =
      document.getElementById("dashboardPage");

    if (dashboard) {
      dashboard.remove();
    }

    showPage("homePage");

  }


  function showMessage(id, text) {

    const message =
      document.getElementById(id);

    message.innerText = text;
    message.style.display = "block";

  }


  function showJobs() {

    alert(
      "Jobs marketplace coming next! Customers will be able to post jobs here."
    );

  }


  function showWorkers() {

    alert(
      "Worker marketplace coming next! You will be able to search workers here."
    );

  }


  function searchSkill(skill) {

    document.getElementById("search").value = skill;

    alert(
      "Searching SkillNaija for " + skill + "..."
    );

  }

</script>

</body>
</html>
