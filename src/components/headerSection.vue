<template>
  <header class="d-flex align-items-center">
      <img src="../assets/spotify_logo.png" class="" alt="">
      <select class="h-50 w-25 rounded-pill" v-model="genreSelect" @change="$emit('filter', genreSelect)">
        <option value="All">All</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
        <option value="Pop">Pop</option>
        <option value="Rock">Rock</option>
      </select>
  </header>

</template>




<script>
export default {
name: "headerSection",
data() {
    return{
        genreSelect: "All"
    }
}
}
</script>




<style lang="scss" scoped>
header{
    background-color: #2e3a46;
    height: 10vh;

img{
    height: 80%;
    margin-left: 2rem;
}

select{
margin-left: 2rem;
}


}



</style>