<template>
  <div id="app">
    <Particles class="background-particles"
        id="tsparticles"
        :options="{
            particles: {
                color: {
                    value: '#dddddd'
                },
                links: {
                    color: '#dddddd',
                    distance: 150,
                    enable: true,
                    opacity: 0.5,
                    width: 1
                },
                move: {
                    direction: 'none',
                    enable: true,
                    outMode: 'bounce',
                    random: false,
                    speed: 1,
                    straight: false
                },
                number: {
                    density: {
                        enable: true,
                        value_area: 800
                    },
                    value: 80
                },
                opacity: {
                    value: 0.5
                },
                shape: {
                    type: 'circle'
                },
                size: {
                    random: true,
                    value: 5
                }
            },
            detectRetina: true
        }"
    />
    <h1 class="title">《 插 件 的 名 字 》</h1>
    <Setting style="width: 500px; margin:auto;"/>
  </div>
</template>

<script>
import Setting from './components/Setting.vue'

export default {
  name: 'App',
  components: {
    Setting
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 60px;
  margin-left: 30px;
  text-align: center;
}
.background-particles{
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  z-index: -1;
}
.title{
  margin-bottom: 3em;
}
</style>
