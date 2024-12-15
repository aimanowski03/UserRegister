<template>
  <div class="register-container">
    <div class="register-form">
      <h1>REGISTER</h1>
      <form @submit.prevent="register">
        <div class="input-group">
          <label for="email">EMAIL</label>
          <div class="input-wrapper">
            <input
              v-model="email"
              type="email"
              id="email"
              placeholder="Enter your email"
              required
            />
            <i class="fa fa-envelope"></i>
          </div>
        </div>

        <div class="input-group">
          <label for="username">USERNAME</label>
          <div class="input-wrapper">
            <input
              v-model="username"
              type="text"
              id="username"
              placeholder="Enter your username"
              required
            />
            <i class="fa fa-user"></i>
          </div>
        </div>

        <div class="input-group">
          <label for="password">PASSWORD</label>
          <div class="input-wrapper">
            <input
              v-model="password"
              :type="passwordVisible ? 'text' : 'password'"
              id="password"
              placeholder="Enter your password"
              required
            />
            <i
              class="fa"
              :class="passwordVisible ? 'fa-eye-slash' : 'fa-eye'"
              @click="togglePasswordVisibility('password')"
            ></i>
          </div>
        </div>

        <div class="input-group">
          <label for="confirmPassword">CONFIRM PASSWORD</label>
          <div class="input-wrapper">
            <input
              v-model="confirmPassword"
              :type="passwordVisible ? 'text' : 'password'"
              id="confirmPassword"
              placeholder="Confirm your password"
              required
            />
            <i
              class="fa"
              :class="passwordVisible ? 'fa-eye-slash' : 'fa-eye'"
              @click="togglePasswordVisibility('confirmPassword')"
            ></i>
          </div>
        </div>

        <button type="submit">SIGN UP</button>
      </form>

      <p class="login-link">
        Already have an account? <a href="/login">Login</a>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Register",
  data() {
    return {
      email: "",
      username: "",
      password: "",
      confirmPassword: "",
      passwordVisible: false,
    };
  },
  methods: {
    register() {
      if (this.password !== this.confirmPassword) {
        alert("Passwords do not match!");
        return;
      }

      // You can implement the registration logic here
      alert("Registration successful!");
    },
    togglePasswordVisibility(field) {
      this.passwordVisible = !this.passwordVisible;
    },
  },
};
</script>

<style scoped>
.register-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: white; /* Change background to white */
}

.register-form {
  background-color: white; /* Form background also white */
  padding: 30px;
  border-radius: 10px;
  width: 350px;
  text-align: center;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
}

h1 {
  color: #333; /* Dark color for the header */
  font-size: 26px;
  margin-bottom: 20px;
}

.input-group {
  margin-bottom: 20px;
  position: relative;
}

.input-group label {
  color: #333; /* Dark color for labels */
  text-align: left;
  font-size: 14px;
  display: block;
}

.input-wrapper {
  position: relative;
}

input {
  width: 100%;
  padding: 10px;
  font-size: 16px;
  border-radius: 5px;
  border: 1px solid #ccc; /* Light border for inputs */
  background-color: #fafafa; /* Light background for inputs */
  color: #333; /* Dark text color */
  margin-top: 5px;
}

input:focus {
  outline: none;
  border-color: #4CAF50;
}

button {
  width: 100%;
  padding: 12px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 5px;
  font-size: 16px;
  cursor: pointer;
}

button:hover {
  background-color: #45a049;
}

.login-link {
  margin-top: 20px;
  color: #333; /* Dark color for the login link */
}

.login-link a {
  color: #4CAF50;
  text-decoration: none;
}

.login-link a:hover {
  text-decoration: underline;
}

.fa {
  position: absolute;
  top: 50%;
  right: 10px;
  transform: translateY(-50%);
  cursor: pointer;
}
</style>
