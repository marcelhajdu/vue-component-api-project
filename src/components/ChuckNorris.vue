<template>
  <div class="hello">
    <h1>Get a Chuck Norris joke</h1>
    <p>{{ joke }}</p>
    <button @click="getJoke()">Get a joke</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: () => {
    return {
      joke: ''
    }
  },
  methods: {
      async getJoke() {
        let config = {
          headers: {
            'Accept': 'application/json'
          }
        }
        const joke = await this.$http.get('http://api.icndb.com/jokes/random1http://api.icndb.com/jokes/random', config)
        this.joke = joke.data.value.joke
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
