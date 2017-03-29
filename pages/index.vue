<template>
  <section class="container">
    <img src="../assets/img/logo.png" alt="Nuxt.js Logo" class="logo" />
    <h1 class="title">
      USERS
       <p>组件缓存test: {{ date }}</p>
    </h1>
    <ul class="users">
      <li v-for="(user, index) in users" class="user">
        <nuxt-link :to="{ name: 'id', params: { id: index }}">
          {{ user.name }}
        </nuxt-link>
      </li>
    </ul>
    <hr>
    中间件 浏览记录：

    <visits/>
  </section>
</template>

<script>
import axios from '~plugins/axios'
import Visits from '~components/visits.vue'


export default {
  name: 'indexkk',
  transition: 'test',
  layout: 'dark',
  components: {
    Visits
  },
  async asyncData () {
    let { data } = await axios.get('/api/users')
    return {
      users: data
    }
  },
  serverCacheKey () {
    // Will change every 3 secondes
    return Math.floor(Date.now() / 10000)
  },
  data () {
    return { date: Date.now() }

  },
  head () {
    return {
      title: 'Users'
    }
  }
}
</script>

<style scoped>
.title
{
  margin: 30px 0;
}
.users
{
  list-style: none;
  margin: 0;
  padding: 0;
}
.user
{
  margin: 10px 0;
}
</style>
