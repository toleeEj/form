<template>
  <div class="home-page">
    <div class="welcome-box">
      <h1>Welcome to Our Website</h1>
      <p>Please choose an option to continue:</p>

      <!-- Buttons to toggle between login and sign-up -->
      <div class="auth-buttons">
        <button @click="showLogin = true" :class="{ active: showLogin }">Login</button>
        <button @click="showLogin = false" :class="{ active: !showLogin }">Sign Up</button>
      </div>

      <!-- Conditional rendering of the form components -->
      <div v-if="showLogin">
        <LogIn />
      </div>
      <div v-else>
        <SignUp />
      </div>
    </div>
  </div>
</template>

<script>
import LogIn from './components/LogIn.vue';
import SignUp from './components/SignUp.vue';

export default {
  components: {
    LogIn,
    SignUp,
  },
  data() {
    return {
      showLogin: true, // Default to showing the login form
    };
  },
};
</script>

<style scoped>
.home-page {
  margin-top: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: #f0f0f0;
}

.welcome-box {
  text-align: center;
  background-color: #fff;
  padding: 40px;
  border-radius: 10px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  width: 100%;
  max-width: 500px;
}

h1 {
  margin-bottom: 20px;
  font-size: 24px;
  color: #333;
}

p {
  font-size: 18px;
  margin-bottom: 20px;
  color: #666;
}

.auth-buttons {
  display: flex;
  justify-content: center;
  gap: 15px;
  margin-bottom: 20px;
}

.auth-buttons button {
  padding: 12px 30px;
  font-size: 16px;
  cursor: pointer;
  border: none;
  border-radius: 5px;
  transition: background-color 0.3s;
}

.auth-buttons .active {
  background-color: #007bff;
  color: white;
}

.auth-buttons button:not(.active) {
  background-color: #ccc;
  color: #333;
}

.auth-buttons button:hover {
  background-color: #0056b3;
  color: white;
}
</style>
