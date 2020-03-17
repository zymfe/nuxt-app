<template>
  <div class="list-container">
    <h1>this is list page</h1>
    <div v-for="(v, k) in list" :key="k" @click="toDetailPage(v.id)">{{v.name}}</div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      list: [
        {id: 1, name: 1},
        {id: 2, name: 2},
        {id: 3, name: 3}
      ]
    }
  },

  methods: {
    toDetailPage (id) {
      this.$router.push({
        path: '/detail',
        query: {
          id
        }
      })
    }
  }
}
</script>

<style lang="less" scoped>
.list-container {
  font-size: 20px;
  color: blue;
}
</style>