<template>
  <div id="app">
    <loader-container v-if="!flagLoaded" />
    
    <header-container v-else/>
    <search-container @search="genre"/>
    <album-container  :albumList="albumList"/>
  </div>
</template>

<script>
import axios from 'axios'
import LoaderContainer from './components/LoaderContainer.vue'
import AlbumContainer  from './components/AlbumContainer.vue'
import HeaderContainer from './components/HeaderContainer.vue'
import SearchContainer from './components/SearchContainer.vue'



export default {
  name: 'App',

  components: {
    HeaderContainer,
    AlbumContainer,
    LoaderContainer,
    SearchContainer

  },
     
     data(){
       return {
         albumList:[],
         flagLoaded:false,
         filtered:[],
       }
     },
     methods:{
       filterDisc(genre){
          this.filterDisc=this.albumList.filter((disc) => {
            return disc.genre.toLowerCase() === genre || genre ==='all';
          });
       },
     },
  mounted() {

    setTimeout( () => {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response)=>{
     
     this.albumList=response.data.response
     this.flagLoaded=true;
    })
    }, 1000)
  }
}
</script>

<style lang="scss">

    @import 'style/main.scss'

</style>
