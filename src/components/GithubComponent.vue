<template>
<div class="github">
  <input type="text" v-model="username" placeholder="Type in your Github username" v-on:keyup.enter="getUserInfo()">
  <button @click="getUserInfo()">Get User info</button>
  <div><img :src="user.avatar_url" ></div>
  <p>{{ user.name }}</p>
  <p>{{ user.bio }}</p>
  <div v-if="user.id > 0">
    <p>Number of followers: {{ user.followers }}</p>
    <p>Joined in {{ user.created_at }}</p>
  </div>

</div>
</template>

<script>
export default {
  name: 'GithubComponent',
  data: () => {
    return {
      user: {},
      username: ''
    }
  },
  //getting the info with axios
  methods: {
    getUserInfo() {
      this.$http.get(`https://api.github.com/users/${this.username}`)
      .then(response => {
        this.user = response.data
      })
    }
  }
}

</script>