<template>
  <div class="highlighted-content">
    <h1>{{ headline }}</h1>
    <p>{{ description }}</p>
    <NuxtLink :to=url>BUTTON</NuxtLink>
  </div>
</template>

<script>
export default {
  props: [
    'headline',
    'description',
    'url'
  ],
}
</script>

<style scoped>
  .highlighted-content {
    display: flex;
    flex-direction: column;
    align-content: center;
    justify-content: center;
    width: 30%;
    min-width: 300px;
  }
  h1 {
    text-align: center;
  }
  a {
    text-align: center;
    background-color: #76d0e9;
    padding: 12px;
    border-radius: 5px;
    border: 1px solid #000000;
    width: 70%;
    margin: 0 auto;
  }
</style>