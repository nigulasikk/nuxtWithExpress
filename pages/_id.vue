<template>
  <section class="container">
    
    <h2 class="info">
      {{ user.name }}
    </h2>
    <nuxt-link class="button" to="/">
      返回Users
    </nuxt-link>
  </section>
</template>

<script>
import axios from '~plugins/axios'

export default {
  name: 'id',
  layout: 'dark',
  transition: 'test',
  asyncData ({ params, error }) {
    return axios.get('/api/users/' + params.id)
    .then((res) => {
      return { user: res.data }
    })
    .catch((e) => {
      error({ statusCode: 404, message: 'User not found' })
    })
  },
  head () {
    return {
      title: `User: ${this.user.name}`
    }
  }
}
</script>

<style scoped>
.title
{
  margin-top: 30px;
}
.info
{
  font-weight: 300;
  color: #9aabb1;
  margin: 0;
  margin-top: 10px;
}
.button
{
  margin-top: 30px;
}
</style>
