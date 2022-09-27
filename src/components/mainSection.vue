<template>
    <main>
     <section class="container d-flex flex-wrap justify-content-center h-100 align-items-center">
        <div class="am-card d-flex align-items-center flex-column p-3 text-center text-white gap-3 rounded-4" v-for="(item) in exportedArray" :key="item.poster">
            <img class="rounded-4" :src="item.poster" alt="">
            <h3>{{item.title}}</h3>
            <h4>{{item.author}}</h4>
            <h4>{{item.year}}</h4>
        </div>
     </section> 
    </main>
</template>
    

  <!-- JAVASCRIPT -->
  <script>
  export default {
  name: "mainSection",
  props: {
    exportedArray: Array
  }
  }
  </script>
  
  
  
  
  <style lang="scss" scoped>
  main{
    background-color: #1e2d3b;
    height: 90vh;
  }

  .am-card{
    background-color: #2e3a46;
    width: calc(100% / 5 - 30px);
    height: 400px;
    margin: 15px;
   

    img{
        height: 150px;
        width: 150px;
    }
  }

  </style>