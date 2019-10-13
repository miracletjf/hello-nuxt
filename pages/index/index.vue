<template>
  <div>
    <h1>{{name}}</h1>
    <!-- <ul v-if="listData && listData.length">
      <li v-for="(item, index) in listData" :key="index">
        <a :href="item.url">{{item.name}}</a>
        <span class="text">{{item.address}}</span>
      </li>
    </ul> -->
  </div>
</template>
<script>
export default {
  async asyncData({ $axios, query }) {
    console.log(query)
    const result = await $axios.$get('https://www.easy-mock.com/mock/5bd01284dfa1f337facb9fe0/example/query')
    let name = result.data.name
    return { name }
  },
  data() {
    return { }
  },
  created() {
    this.initData()
  },
  methods: {
    initData(){
      this.getUserInfo()
    },
    getUserInfo() {
      // this.name = this.$route.query.name
    }
  }
}
</script>