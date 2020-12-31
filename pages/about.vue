<template>
  <section class="about_blurb">
    <h1>{{ data.heading }}</h1>
    <p>{{ data.text_field_1 }}</p>
    <p>{{ data.author }}</p>
    <div class="card-holder">
      <Gallery
        v-for="(images, index) in data.gallery"
        :key="index"
        :path="images"
        :alt-tag="images"
      />
    </div>
    <p>{{ data.text_field_2 }}</p>
    <div class="card-holder">
    <Highlight 
      v-for="(block, index) in data.blocks[0].highlights"
      :key="index"
      :headline="block.headline"
      :description="block.description"
      :url="block.url"
    />
    </div>
    <br>
    <ul>
      <li
        v-for="(sortList, index) in data.sortable_one"
        :key="index"
      >
        {{ sortList }}
      </li>
    </ul>
    <div>
      <h2>{{ data.field_group_one.some_kind_of_heading }}</h2>
      <p>{{ data.field_group_one.paragraph_one }}</p>
    </div>
    <div :style="{backgroundColor: `${data.color_picker}`}">
      <p>toggle: {{ data.toggle_one }}</p>
      <p>What can I do with this boolean... 🤔</p>
      <p>Color: {{ data.color_picker }}</p>
      <p>Field Selector: {{ data.field_selector }}</p>
    </div>
  </section>
</template>

<script>
import Gallery from '../components/Gallery'
import Highlight from '../components/Highlight'
export default {
  components: {
    Gallery,
    Highlight
  },
  layout: 'layout',
  async asyncData() {
    try {
      const data = await import(`~/content/data/about.json`);
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
    display: flex;
    flex-flow: row wrap;
    justify-content: space-evenly;
  }
</style>
