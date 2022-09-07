<template>
  <main>
    <div class="my-container">
      <div class="row gap-4" >
        <div class="my-card"  v-for="(album, index) in listAlbums" :key="index" style="width: 13rem;">
          <img class="my-card-img" :src="album.poster" :alt="album.title" >
          <div class="my-card-bottom">
            <h5>{{album.title}}</h5>
            <p class="my-card-description">
              {{album.author}} <br>
              {{album.year}}
            </p>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
<script>
  import axios from "axios";
  export default {
  name: 'MainContent',
  data(){
    return{
      listAlbums: [],
    }
  },
  created(){
    axios
    .get('https://flynn.boolean.careers/exercises/api/array/music')
    .then((res) =>{
      this.listAlbums = res.data.response;
    })
  }
}
</script>
<style scoped lang="scss">
@import '../var.scss';
@import '../index.scss';

main {
  padding: 70px 0;
}
.my-card{
  background-color: $bg-blue;
  padding: 20px;
  & .my-card-img{
    width: 100%;
  }
  & .my-card-bottom{
    text-align: center;
    & h5{
      color: white;
      text-transform: uppercase;
      padding: 20px 0;
    }
    & .my-card-description{
      color: grey;
      font-size: 20px;
      font-weight: 500;
    }
  }
}
</style>