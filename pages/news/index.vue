<template>
  <div>
    新闻列表
    <ul>
      <li v-for="item of list">
        <nuxt-link :to="`/news/${item.id}`" target="_blank">{{ item.title }}</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data () {
    return {
      ip: '',
      list: []
    }
  },
  async asyncData (ctx) {
    const result = await ctx.$axios.$get('https://cnodejs.org/api/v1/topics')
    return { list: result.data }
  },
  mounted () {
    
  },
  methods: {

  }
}
</script>