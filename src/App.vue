<template>
  <div id="app">
    <preview-card class="card"/>
  </div>
</template>

<script>
import PreviewCard from './components/PreviewCard.vue'
export default {
  name: 'App',
  components: {
    PreviewCard
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background: hsl(30, 38%, 92%);
  height: 99vh;
  display: flex;
  justify-content: center;
  align-items: center;
  margin:0px;
  padding: 0px;
  overflow: hidden;
}.card{
  border-radius: 1em;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  background: white;
  overflow: hidden;
}
@media (max-width: 768px) {
  #app {
    height: 100vh;
  }
  .card{
    width:auto;
    height: 100%;
    flex-direction:column!important;
    overflow-y:auto!important;
  }
}
</style>
