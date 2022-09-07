<template>
  <div class="row gap-4">
    <div class="my-card" v-for="(album, index) in albums" :key="index" style="width: 13rem;">
      <img class="my-card-img" :src="album.poster" :alt="album.title">
      <div class="my-card-bottom">
        <h5>{{album.title}}</h5>
        <p class="my-card-description">
          {{album.author}} <br>
          {{album.year}}
        </p>
      </div>
    </div>

  </div>
</template>
<script>

export default {
  name: 'AlbumCard',
  props: {
    albums: Array,
  },
  
}
</script>
<style scoped lang="scss">
@import '../var.scss';
@import '../index.scss';

main {
  padding: 70px 0;
}

.my-card {
  background-color: $bg-blue;
  padding: 20px;

  & .my-card-img {
    width: 100%;
  }

  & .my-card-bottom {
    text-align: center;

    & h5 {
      color: white;
      text-transform: uppercase;
      padding: 20px 0;
    }

    & .my-card-description {
      color: grey;
      font-size: 20px;
      font-weight: 500;
    }
  }
}
</style>