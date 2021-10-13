<template>
  <div id="app">
    <Head></Head>
    <Main></Main>
    <Foot></Foot>
    
  </div>
</template>

<script>
import Vue from 'vue'
import VueCoreVideoPlayer from 'vue-core-video-player'
 
import Head from './components/Head.vue'
import Main from './components/Main.vue'
import Foot from './components/Foot.vue'


Vue.use(VueCoreVideoPlayer, {
  lang: 'en'
})

export default {
  name: 'App',
  components: {
    Head,
    Main,
    Foot,
    
  },
   data () {
      return {
        options: {
            mouseControls: true,
            touchControls: true,
            minHeight: 500.00,
            minWidth: 200.00,
            scale: 1.00,
            scaleMobile: 1.00
        }
      }
    }
}
</script>

<style>
.vanta{
  position: fixed;
  right: 0;
  bottom: 0;
  min-width: 100%;
  min-height: 100%;
  margin: 0;
  padding: 0;
}
</style>
