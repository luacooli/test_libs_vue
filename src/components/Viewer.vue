<template>
  <div id="viewer">
    <!-- directive -->
    <div class="images" v-viewer="{ inline: false, toolbar: false }">
      <h2>Directive</h2>
      <h5 @click="abrir(i)">foto 1</h5>

      <img
        class="image"
        v-for="(image, i) in images"
        :src="image"
        :key="i"
        ref="viewer"
      />
    </div>

    <!-- component -->
    <!-- <viewer :images="images" :toolbar="false" ref="viewer2">
      <h2>Component</h2>
      <template slot-scope="scope">
        <img
          class="image"
          v-for="(image, i) in scope.images"
          :src="image"
          :key="i"
        />
        <button @click="show(i)">click here</button>
      </template>
    </viewer> -->
  </div>
</template>
<script>
import 'viewerjs/dist/viewer.css'
import Viewer from 'v-viewer'
import Vue from 'vue'
Vue.use(Viewer)

export default {
  data() {
    return {
      images: [
        'https://picsum.photos/200/200',
        'https://picsum.photos/200/200',
        'https://picsum.photos/200/200',
      ],
    }
  },
  methods: {
    abrir() {
      const viewer = this.$el.querySelector('.images').$viewer
      viewer.show()
    },
    // show() {
    //   const viewer = this.$el.querySelector('.image').$viewer
    //   viewer.show()
    // },
  },
}
</script>

<style>
.images {
  display: inline-block;
}

.images .image {
  display: none;
}
</style>
