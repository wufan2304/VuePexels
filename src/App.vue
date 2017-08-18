<template>
  <div id="app">
    <img src="./assets/logo.png">
    <router-view></router-view>
    <waterfall :line-gap="200" :watch="items">
      <!-- each component is wrapped by a waterfall slot -->
      <waterfall-slot v-for="(item, index) in items" :width="item.width" :height="item.height" :order="index" :key="item.id">
        <!--
        your component
      -->
      </waterfall-slot>
    </waterfall>
  </div>
</template>

<script>
import Waterfall from 'vue-waterfall/lib/waterfall'
import WaterfallSlot from 'vue-waterfall/lib/waterfall-slot'

export default {
  name: 'app',
  data () {
    return {
      pictures: []
    }
  },
  components: {
    Waterfall,
    WaterfallSlot
  },
  mounted: {

  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
