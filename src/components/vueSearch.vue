<template>
<div  class="response">
  <div v-if="tests.show_title" class="container">
    <div class="columns">

      <div class="column img">
        <img :src="tests.poster" />

      </div>
      <div class="column">

        <h2 class="title">{{ tests.show_title }} ({{ tests.release_year }})</h2>
        <p><b>Netflix Rating: </b> {{ tests.rating }}</p>
        <br>
        <p>{{ tests.summary }}</p>
        <br>
        <p><b>Actors: </b>{{ tests.show_cast }}</p>
      </div>

    </div>

  </div>
  <p v-else>{{ tests }}</p>

</div>



</template>

<script>
export default {
  name: 'vueSearch',
  props: ['tests']


}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h2 {
  font-weight: bolder;
}

.columns {
  padding: 30px 0 30px 0;
}
img{
  border-radius: 10px;

}

.container {
  color: #999999;
  max-width: 750px;
  text-align: left;
}

.response {
  background-color: #171715;
  margin-top: 25px;
}
</style>
