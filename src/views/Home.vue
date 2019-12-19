<template>
  <div class="home">
    <ChuckNorris/>
  </div>
</template>

<script>
// @ is an alias to /src
import ChuckNorris from '@/components/ChuckNorris.vue'

export default {
  name: 'home',
  components: {
    ChuckNorris
  }
}
</script>
