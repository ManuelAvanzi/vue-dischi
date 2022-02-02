<template>
    <div class="container">
         <select @change="$emit('search')">

            <option value="all">All</option>
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
        </select>
    </div>
</template>


<script>
export default {
    
}
</script>


<style lang="scss" scoped>

.container{
    width: 100%;
    display: flex;
    justify-content: center;
    background-color:  #2E3A46;
    
}
  select{
      width:300px;
      height: 40px;
      color:black;
      text-align: center;
      margin-bottom:10px;
      border:3px solid orange;
  }
</style>