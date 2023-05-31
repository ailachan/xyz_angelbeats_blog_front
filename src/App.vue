<template>
  <div id="app">
    <router-view>
      <!--    底部信息-->
      <div class="ui segment bottom fixed footer_position">
        <Footer></Footer>
      </div>
    </router-view>
    <meting-js
      id="7717765305"
      lrc-type="0"
      server="netease"
      order="list"
      type="playlist"
      fixed="true"
      list-olded="true"
      mutex="true"
    ><!--autoplay="true"-->
    </meting-js>
  </div>
</template>
<script>
import Footer from "./components/footer.vue";

export default {
  name: 'App',
  components: {Footer},
}
</script>

<style scoped>
</style>
