<template>
  <div class="auth-container">
    <div class="auth-box">
      <h2>Login</h2>
      <form @submit.prevent="loginUser">
        <div class="input-group">
          <label for="email">Email</label>
          <input type="email" id="email" v-model="email" required />
        </div>
        <div class="input-group">
          <label for="password">Password</label>
          <input type="password" id="password" v-model="password" required />
        </div>
        <button type="submit" class="submit-btn">Login</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      password: '',
    };
  },
  methods: {
    loginUser() {
      console.log('Logging in with:', this.email, this.password);
      // Add login logic here (e.g., API call)
      this.email = '';
      this.password = '';
    }
  }
};
</script>

<style scoped>
.auth-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: #f5f5f5;
}

.auth-box {
  background-color: #ffffff;
  padding: 30px;
  border-radius: 10px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  width: 100%;
  max-width: 400px;
}

h2 {
  margin-bottom: 20px;
  color: #333;
  text-align: center;
}

.input-group {
  margin-bottom: 15px;
}

.input-group label {
  font-weight: bold;
  color: #555;
  margin-bottom: 5px;
  display: block;
}

input {
  width: 100%;
  padding: 10px;
  border-radius: 5px;
  border: 1px solid #ccc;
  outline: none;
  transition: border-color 0.3s;
}

input:focus {
  border-color: #007bff;
}

.submit-btn {
  width: 100%;
  padding: 12px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  font-size: 16px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.submit-btn:hover {
  background-color: #0056b3;
}

@media screen and (max-width: 600px) {
  .auth-box {
    width: 90%;
  }
}
</style>
