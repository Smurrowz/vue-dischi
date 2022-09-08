<template>
  <header>
    <img src="../assets/img/Spotify.svg" alt="logo spotify">
    <div class="inputs">
      <select v-model="selectGenre" @click="$emit('search', selectGenre )" class="rounded" name="genere" id="genere">
        <option value="" selected disabled hidden>Choose Genre</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Metal">Metal</option>
        <option value="Jazz">Jazz</option>
        <option value="">Reset</option>
      </select>
      <input v-model="albumNameText" @keyup="$emit('searchName',albumNameText)" type="text" class="rounded" placeholder="Album Name es: 'In Rock'">
      <input v-model="albumArtistText" @keyup="$emit('searchArtist',albumArtistText)" type="text" class="rounded" placeholder="Artist es: 'Jimi Hendrix'">
      <input v-model="albumYearText" @keyup="$emit('searchYear',albumYearText)" type="number" class="rounded" placeholder="Year es: '2022'">

    </div>
    
  </header>
</template>
<script>
  export default {
    name: 'MainHeader',
    data(){
      return{
        selectGenre: "",
        albumNameText: "",
        albumArtistText: "",
        albumYearText:"",
      }
    }
  }

</script>
<style scoped lang="scss">
  @import '../var.scss';
  header{
    background-color: $bg-blue;
    padding: 10px 20px;
    position: relative;
    display: flex;
    align-items: center;
    & .inputs{
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
      & select{
        height: 1.5rem;
        margin: 0 10px;
      }
      & input{
        height: 1.5rem;
        margin: 0 10px;
      }
    }
    & img{
      height: 50px;
      
    }
  }
</style>