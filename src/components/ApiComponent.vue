<template>
  <div>
    <h1>Защищенная страница</h1>
    <div class="buttons">
      <button class="load-button" @click="loadMoreUsers">Загрузить больше</button>
      <button class="logout-button" @click="logout">Выйти</button>
    </div>
    <div class="user-list">
      <user-card v-for="user in users" :user="user" :key="user.login.uuid" />
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import UserCard from './UserCard.vue';

export default {
  name: 'ApiComponent',
  components: {
    UserCard,
  },
  data() {
    return {
      users: [],
    };
  },
  methods: {
    async loadMoreUsers() {
      try {
        const response = await axios.get('https://randomuser.me/api/?results=10');
        this.users = this.users.concat(response.data.results);
        console.log(this.users);
      } catch (error) {
        console.error('Ошибка при загрузке пользователей', error);
      }
    },
    logout() {
      localStorage.setItem('loggedIn', 'false');
      this.$router.push('/');
    },
  },
};
</script>

<style lang="scss" scoped>
.user-list {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
}

.buttons {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}

.load-button,
.logout-button {
  padding: 10px 20px;
  font-size: 16px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.load-button:hover,
.logout-button:hover {
  background-color: #0056b3;
}
</style>
