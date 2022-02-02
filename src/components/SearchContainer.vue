<template>
    <div>
         <select
            
           
            @change="$emit('search')">

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

</style>