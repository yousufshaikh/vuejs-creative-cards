<template>
  <div class="container">
    <div class="row">
      <div class="col-lg-12">
        <Header @pageWasChanged = "currentPage = $event"/>
        <keep-alive>
          <component :is="currentPage"></component>
        </keep-alive>
        <Footer>
          <p class="text-center footer-heading" slot="app-name">&copy; {{appName}}</p>
          <nav>
              <ul class="nav justify-content-center">
                  <li class="nav-item"><a class="nav-link">Home</a></li>
                  <li class="nav-item"><a class="nav-link">About</a></li>
                  <li class="nav-item"><a class="nav-link">Contact Us</a></li>
              </ul>
          </nav>
        </Footer>
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
import Footer from './components/Footer'


export default {
  data: function(){
    return{
      currentPage: 'cardFront',
      appName: 'Creative Card'
    }
  },
  components: {
    // HelloWorld
    Header,
    CardFront,
    CardInsideLeft,
    CardInsideRight,
    CardBack,
    Footer
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
.footer-heading{
  margin-top: 20px;
}
</style>
