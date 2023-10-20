<template>
  <nav>
    <router-link to="/">Home</router-link> | <router-link to="/protected">Protected</router-link> |
    <router-link to="/public">Public</router-link>
  </nav>
  <router-view />
</template>
