<script>
  import { Link } from "svelte-navigator";
  let email,
    password,
    username = "";
  let emailErr,
    passwordErr,
    usernameErr = "";

  const handleSubmit = () => {
    console.log(email, password);
  };

  const setUsernameError = (uname) => {
    if (uname.length < 3) {
      return "Name should be at least three charecters.";
    } else {
      return "";
    }
  };

  const setEmailError = (email) => {
    let regex = new RegExp("[a-z0-9]+@[a-z]+.[a-z]{2,3}");
    if (regex.test(email)) {
      return "";
    } else {
      return "Invalid email address. Email should contain @ sign.";
    }
  };

  const setPasswordError = (pass) => {
    return "Password should contain lowercase, uppercase, digit.";
  };

  const checkError = (e) => {
    switch (e.target.name) {
      case "username":
        usernameErr = setUsernameError(username);
        break;
      case "email":
        emailErr = setEmailError(email);
        break;
      case "password":
        passwordErr = setPasswordError(password);
        break;
    }
  };
</script>

<div class="container form-container">
  <h5 class="header">Signup</h5>
  <form on:submit|preventDefault={handleSubmit}>
    <div class="form-group mb-2">
      <label for="username" class="form-label">Your Name</label>
      <div class="input-group">
        <span class="input-group-text" id="usernamePrepend">
          <ion-icon name="person-outline" />
        </span>
        <input
          class="form-control"
          name="username"
          type="text"
          bind:value={username}
          on:keydown={checkError}
        />
        <div>
          <p class="text-danger">{usernameErr ? usernameErr : ""}</p>
        </div>
      </div>
    </div>

    <div class="form-group mb-2">
      <label for="email" class="form-label">Email</label>
      <div class="input-group">
        <span class="input-group-text" id="emailPrepend">
          <ion-icon name="mail-outline" />
        </span>
        <input
          class="form-control"
          type="email"
          name="email"
          bind:value={email}
          on:keydown={checkError}
          required
        />
        <p class="text-danger">{emailErr ? emailErr : ""}</p>
      </div>
    </div>

    <div class="form-group mb-2">
      <label for="password" class="form-label">Password</label>
      <div class="input-group">
        <span class="input-group-text" id="passPrepend">
          <ion-icon name="lock-closed-outline" />
        </span>
        <input
          aria-describedby="password"
          class="form-control"
          name="password"
          type="password"
          bind:value={password}
          on:keydown={checkError}
          required
        />

        <div>
          <p class="text-danger">
            {passwordErr ? passwordErr : ""}
          </p>
        </div>
      </div>
    </div>
    <button class="btn login-btn btn-primary">Signup</button>
  </form>
  <div class="mt-2">
    <Link to="/login">Already have an account? Login</Link>
  </div>
</div>

<style>
  .header {
    margin-bottom: 1rem;
    text-align: center;
    outline: none;
    font-size: 22px;
  }
  .form-container {
    width: 350px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  .login-btn {
    width: 100%;
  }

  button:hover {
    box-shadow: 0px 4px 2px -2px lightgray;
  }
</style>
