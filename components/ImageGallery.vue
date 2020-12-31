<template>
<div>
  <img
    :src=path
    :alt=altTag
  >
  <h2>{{ title }}</h2>
</div>
</template>

<script>
export default {
  props: [
    'path',
    'altTag',
    'title'
  ]
}
</script>

<style scoped>
  img {
    object-fit: cover;
    height: 200px;
    width: 200px;
  }
</style>