<template>
  <div class="card-holder">
    <ImageGallery
      v-for="(images, index) in data.naming_scheme_5"
      :key="index"
      :path="images.image"
      :alt-tag="images.image_alt_tag"
      :title="images.image_title"
      class="image-item"
    />
  </div>
</template>

<script>
import ImageGallery from '../components/ImageGallery'
export default {
  components: {
    ImageGallery,
  },
  layout: 'layout',
  async asyncData() {
    try {
      const data = await import(`~/content/data/gallery.json`);
      return {
        data
      }
    } catch(err) {
      return false
    }
  },
  head() {
    return {
      styleObject: {
        color: this.data.color_picker
      }
    }
  }
}
</script>

<style scoped>
  .card-holder {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    justify-items: center;
  }
</style>
