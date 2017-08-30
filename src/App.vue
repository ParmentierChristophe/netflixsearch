<template>
<div id="app">

  <img class="logo" src="./assets/Netflixlogo.svg" alt="">
  <h1 class="title">Search on Netflix</h1>

  <presentVideo v-on:formSubmit="searchNetflix"></presentVideo>
  <vueSearch :tests='tests'></vueSearch>

  <footer class="footer back">
    <div class="container">
      <div class="content has-text-centered">
        <p>
          by <a target="_blank" href="http://christophe-parmentier.fr">Crispy</a>.
          <p>
            <a class="icon" target="_blank" href="https://github.com/ParmentierChristophe">
            <i class="fa fa-github"></i>
          </a>
          </p>
      </div>
    </div>
  </footer>
</div>
</template>

<script>
import presentVideo from './components/presentVideo';
import vueSearch from './components/vueSearch';

export default {
  name: 'app',
  components: {
    presentVideo,
    vueSearch

  },
  data() {
    return {
      tests: ''
    }

  },
  methods: {
    searchNetflix: function(text) {

      this.$http.get("https://netflixroulette.net/api/api.php?title=" + text).then((response) => {
        this.tests = response.body;
        console.log(response.body);





      }, response => {
        var resp = 'sry its not'
        this.tests = resp;

      });
    }
  }

}
</script>

<style>
body {
  width: 100%;
  height: 100vh;
  background-color: #1D1D1D;
  overflow-x: hidden;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #fff;
}

.title {
  color: white;
}

.logo {
  padding-top: 25px;
  width: 20%;
}

.back {
  background-color: #1D1D1D;
}

.back a {
  color: red;
}
</style>
