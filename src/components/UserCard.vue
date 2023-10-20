<template>
  <div class="user-card">
    <div class="user-avatar">
      <img :src="user.picture.large" alt="User Avatar" />
    </div>
    <div class="user-info">
      <p class="user-name">
        <strong>{{ user.name.first }} {{ user.name.last }}</strong>
      </p>
      <p class="user-detail">Date of Birth: {{ user.dob.date }}</p>
      <p class="user-detail">Email/Phone: {{ user.email }} / {{ user.phone }}</p>
      <p class="user-detail">Location: {{ user.location.city }}, {{ user.location.country }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    user: Object,
  },
};
</script>

<style lang="scss" scoped>
.user {
  &-card {
    display: flex;
    align-items: center;
    background: #f5f5f5;
    border: 1px solid #ddd;
    border-radius: 5px;
    padding: 10px;
    margin: 10px 0;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  &-avatar {
    flex: 0 0 auto;
    width: 100px;
    height: 100px;
    overflow: hidden;
    border-radius: 50%;
  }

  &-avatar img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  &-info {
    margin-left: 20px;
    font-family: Arial, sans-serif;
    font-size: 16px;
  }

  &-name {
    font-weight: 600;
    font-size: 18px;
    margin: 0;
  }

  &-detail {
    margin: 5px 0;
  }
}
</style>
