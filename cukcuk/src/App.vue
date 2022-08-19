<template>
  
  <TheMenu/>
  <TheContent />
  

</template>

<script>

  import TheContent from './components/TheContent.vue';
  import TheMenu from './components/TheMenu.vue';

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
}
#app {
  width: 100vw;
  height: 100vh;
  font-size: 13px;
  display: flex;
}
</style>
