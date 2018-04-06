<template>
  <div class="extra-margin">
      <h1 class="text-center">Creative Cards Design on <code>Vue.js</code></h1>
      <p class="text-center"><b>Create your card, it's dynamic and functional</b></p>
      <ul class="nav justify-content-center">
          <!-- <li class="nav-item"><a class="nav-link" @click="pageSelected='cardFront'">Front</a></li> -->
          <!-- <li class="nav-item"><a class="nav-link" @click="pageSelected='cardInsideLeft'">Inside Left</a></li> -->
          <!-- <li class="nav-item"><a class="nav-link" @click="pageSelected='cardInsideRight'">Inside Right</a></li> -->
          <!-- <li class="nav-item"><a class="nav-link" @click="pageSelected='cardBack'">Back</a></li> -->
      </ul>
  </div>
</template>

<script>
    export default{
        data: function(){
            return{
                pageSelected: ''
            }
        },
        watch:{
            pageSelected: function(){
                this.$emit('pageWasChanged', this.pageSelected);
            }
        }
    }
</script>

<style scoped>
h1{
    margin-top: 10px; 
}
a{
    cursor: pointer;
}
</style>
