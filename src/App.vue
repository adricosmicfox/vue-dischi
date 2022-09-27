<template>
  <div id="app">
    <headerSection @filter="assignFilter" />
    <MainSection :exportedArray = applyFilter />
  </div>
</template>

<script>


import headerSection from "./components/headerSection.vue"
import MainSection from "./components/mainSection.vue"
import axios from "axios"


export default {
  name: 'App',
  components: {
    headerSection,
    MainSection
},

data(){
return {
  musicArray: [],
  filter : "All"
}
},

methods: {
assignFilter (genreSelect) {
  this.filter=genreSelect
}
},

computed: {
applyFilter(){
  let array = []
  this.musicArray.forEach(element =>{
    if (this.filter === element.genre) {
      array.push(element)
    } else if (this.filter === "All") {
      array = this.musicArray
    }
  })
return array
}
},

created (){
  axios.get("https://flynn.boolean.careers/exercises/api/array/music")
  .then((response) =>{
  this.musicArray = response.data.response
  })
}
}


</script>

<style lang="scss">
@import "./style/common.scss";


</style>
