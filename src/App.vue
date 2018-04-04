<template>
  <div class="container">
    <div class="row">
      <div class="col-lg-12">
        <Header @pageWasChanged = "currentPage = $event"/>
        <keep-alive>
          <component :is="currentPage"></component>
        </keep-alive>
      </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
import Header from './components/Header'
import CardFront from './components/card/CardFront'
import CardInsideLeft from './components/card/CardInsideLeft'
import CardInsideRight from './components/card/CardInsideRight'
import CardBack from './components/card/CardBack'

export default {
  data: function(){
    return{
      currentPage: 'cardFront'
    }
  },
  components: {
    // HelloWorld
    Header,
    CardFront,
    CardInsideLeft,
    CardInsideRight,
    CardBack
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body{
  color: #333;
  font-family:"Arial, Helvetica, sans-serif";
  height: 1100px;
}
</style>
