<template>
    <div id="container-"> 
    
       <div
          
          v-for="(album, index) in albumList"
          :key="index">

          <album-card :album = "album" />
       </div>

    </div>
    
    
</template>


<script>

import AlbumCard from './AlbumCard.vue'

export default {

  components:  {
      AlbumCard 
  },

    
    props: {
      albumList: Array,
    },
}
</script>


<style lang="scss" scoped>

   #container{
       padding:30px;
       width: 100%;
       height: 100vh;
       background-color: #1E2D3B;;
   }

</style>