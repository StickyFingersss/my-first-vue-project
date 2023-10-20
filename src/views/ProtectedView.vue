<template>
  <div class="protected">
    <div v-if="isLoggedIn">
      <ApiComponent />
    </div>
    <div v-else>
      <p>Вы не вошли в систему. Пожалуйста, <router-link to="/">войдите</router-link>.</p>
    </div>
  </div>
</template>

<script>
import ApiComponent from '@/components/ApiComponent.vue';

export default {
  name: 'ProtectedView',
  components: {
    ApiComponent,
  },
  computed: {
    isLoggedIn() {
      return localStorage.getItem('loggedIn') === 'true';
    },
  },
};
</script>
