<template>
  <header>
  	1.SEO HTML 头部 （default header meta 和 每个页面自定义meta）
  	<br>
  	2.缓存组件 
  	<br>
  	3.loading 自定义组件加载
  	<br>
  	4. 自定义路由
  	<br>
  	5.布局
  	<br>
  	6.中间件
    <br>
    7.路由动效 （在同个layout下才能生效）
    <br>
    8.异步取数据 axios
    <br>
    9.vuex
    <br>
    10.用now一键部署至云端：https://nuxtwidthexpress-roxkkdvngf.now.sh/
  </header>
</template>
<script>
export default {
  head: {
    meta: [
      { name: 'twitter:card', content: 'summary' },
      { name: 'twitter:site', content: '@nuxt_js' },
      { name: 'twitter:title', content: 'Nuxt.js Twitter Card' },
      { name: 'twitter:description', content: 'Nuxt.js lets you handle custom headers for your app with vue-meta' },
      { name: 'twitter:image', content: 'https://avatars0.githubusercontent.com/u/23360933?v=3' },
      { name: 'twitter:image:alt', content: 'Nuxt.js logo' }
    ]
  }
}
</script>