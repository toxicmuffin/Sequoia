<template>
  <div class="image-card">
    <img
      :src=path
      :alt=altTag
    >
    <p>{{ altTag }}</p>
  </div>
</template>

<script>
export default {
  props: [
    'path',
    'altTag'
  ]
}
</script>

<style scoped>
  .image-card {
    width: 30%;
    min-width: 300px;
  }
  img {
    height: 200px;
    width: 100%;
    object-fit: cover;
  }
</style>