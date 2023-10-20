<template>
  <div class="home">
    <AuthorizationForm />
  </div>
</template>

<script>
import AuthorizationForm from '../components/AuthorizationForm.vue';

export default {
  name: 'HomeView',
  components: { AuthorizationForm },
};
</script>
