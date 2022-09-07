<template>
  <div id="app">
    <MainHeader></MainHeader>
    <MainContent/>
  </div>
</template>

<script>
import MainHeader from './components/MainHeader.vue';
import MainContent from './components/MainContent.vue';


export default {
  name: 'App',
  components: {
    MainHeader,
    MainContent
}
}
</script>

<style lang="scss">
  @import './var.scss';
  @import './index.scss';
  #app{
    background-color: $bg-darkblue;
  }
</style>
