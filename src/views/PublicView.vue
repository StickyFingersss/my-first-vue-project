<template>
  <div class="protected">
    <CV />
  </div>
</template>

<script>
import CV from '@/components/CV.vue';

export default {
  name: 'PublicView',
  components: {
    CV,
  },
};
</script>
