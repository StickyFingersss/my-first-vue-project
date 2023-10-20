<template>
  <div>
    <form @submit.prevent="submitForm" v-if="!formSubmitted" class="auth-form">
      <span class="auth-label">Email</span>
      <input v-model="email" type="email" class="auth-input" placeholder="Enter your email" />
      <span class="auth-label">Password</span>
      <input v-model="name" type="password" class="auth-input" placeholder="Enter your password" />
      <button class="auth-submit">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'AuthorizationForm',
  data() {
    return {
      name: '',
      email: '',
      formSubmitted: false,
    };
  },
  created() {
    const loggedIn = localStorage.getItem('loggedIn');
    if (loggedIn === 'true') {
      this.$router.push('/protected');
    }
  },
  methods: {
    submitForm: function () {
      if (this.email === 'admin@example.com' && this.name === 'Qwerty12345') {
        localStorage.setItem('loggedIn', 'true');
        this.$router.push('/protected');
      } else {
        alert('Неправильное имя пользователя или пароль');
      }
    },
  },
};
</script>

<style scoped lang="scss">
.auth-form {
  font-family: Arial, sans-serif;
  border: 2px solid black;
  border-radius: 5px;
  max-width: 400px;
  margin: 0 auto;
  padding: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.auth-input {
  width: 300px;
  padding: 10px;
  margin: 10px 0;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.auth-label {
  font-size: 18px;
  margin: 4px;
  font-weight: 500;
}

.auth-submit {
  width: 100px;
  background: #222;
  color: #fff;
  padding: 10px;
  border: none;
  border-radius: 5px;
  font-size: 16px;
  cursor: pointer;
  margin-top: 10px;
}
</style>
