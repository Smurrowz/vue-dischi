<template>
  <header>
    <img src="../assets/img/Spotify.svg" alt="logo spotify">
  </header>
</template>
<script>
  export default {
    name: 'MainHeader'
  }

</script>
<style scoped lang="scss">
  @import '../var.scss';
  header{
    background-color: $bg-blue;
    padding: 10px 20px;
    & img{
      height: 50px
    }
  }
</style>