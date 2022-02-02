<template>
  <div id="app">
    <loader-container v-if="!flagLoaded" />
    
    <header-container v-else/>
    <search-container @search="test"/>
    <album-container  :albumList="albumList"/>
  </div>
</template>

<script>
import axios from 'axios'
import LoaderContainer from './components/LoaderContainer.vue'
import AlbumContainer from './components/AlbumContainer.vue'
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
         flagLoaded:false
       }
     },
     methods:{
       test:function(){
          console.log(this.albumList[0].title);
       }
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
