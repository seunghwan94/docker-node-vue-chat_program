<template>
  <div class="background-select-color">
    <router-view></router-view>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {

  }
}
</script>

<style>
body{
  margin: 0;
}

div{
  box-sizing: border-box;
}

.background-select-color{
  position: fixed;
  padding: 20px;
  width: 100%;
  height: 100%;
  background: #a7c4e0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
