<template>
  <div v-show="content.length === 0" >
    <h2>aspetta mentre elaboriamo i dati</h2>
  </div>
</template>
<script>
export default{
  name: 'LoaderContent',
  props: {
   content : Array, 
  }
}
</script>
<style scoped lang="scss">
h2{
  font-size: 100px;
  color: white;
  padding: 300px 0;
}
</style>