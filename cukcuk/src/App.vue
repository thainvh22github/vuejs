<template>
  
  <TheMenu/>
  <TheContent />
  

</template>

<script>
  import TheMenu from './components//layout/TheMenu.vue';
  import TheContent from './components/layout/TheContent.vue';

  export default {
    name: 'App',
    components: {
      TheMenu,
      TheContent
  }
}
</script>

<style>
  @import url("./css/common/main.css");

body{
  margin: 0;
  width: 100vw;
  height: 100vh;
  font-size: 13px;
  font-family: Regular;
}
#app {
  width: 100%;
  height: 100%;
  display: flex;
}
</style>
