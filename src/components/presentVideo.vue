<template>
<div class="presentVideo">
  <div class="container">

    <form class="field is-grouped" v-on:submit="formSubmit">
      <p class="control is-expanded">
        <input class="input is-large is-danger" type="text" v-model="textToSearch" placeholder="Search...(exemples: Sharknado, Breaking bad, fairy tail,...)">
      </p>
      <p class="control">
        <button type="submit" class="button is-large is-danger red">
      Search
    </button>
      </p>
    </form>
  </div>
</div>
</template>

<script>
export default {
  name: 'presentVideo',
  data() {
    return {
      textToSearch: ''
    }
  },
  methods: {
    formSubmit(event) {
      this.$emit('formSubmit', this.textToSearch);
      event.preventDefault();
    }

  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.red {
  background-color: red;
}

input[type="text"],
textarea {}
</style>
