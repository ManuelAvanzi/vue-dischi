<template>
    <div class="album-card">
        <div class="album-poster">
            <img class="immagine" :src="album.poster" alt="">
        </div>

        <div class="album-info">
            <div class="album-title">{{ album.title.toUpperCase() }}</div>
            <div class="author ">{{ album.author }}</div>
            <div class="year ">{{ album.year }}</div>
        </div>
    </div>
</template>


<script>
export default {
    
    props:{
        album: Object,
    }
}
</script>

<style lang="scss" scoped>
.album-card {
    margin:10px;
    width: 200px;
    height: 350px;
    max-height: 350px;
    padding:10px;
    overflow: hidden;
    background-color: rgba(255, 255, 255, 0.1);
    

      .immagine{
          width:200px;
          overflow: hidden;
      }
      .album-poster {
        max-height: 150px;
        overflow: hidden;
      }

      .album-info{
          .album-title{
              color:white;
              text-align:center;
              font-size:22px;
              margin-top:20px;
          }
          color:grey;
          text-align:center;
          margin:20px;
      }
}

</style>