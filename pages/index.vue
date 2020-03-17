<template>
  <div class="container">
    <div class="title">this is index page</div>
    <Button type="default" @click="toListPage">to list page</Button>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
export default {
  components: {
    Logo
  },

  data () {
    return {
      a: 1
    };
  },

  mounted () {
    
  },

  methods: {
    toListPage () {
      this.$router.push({
        path: '/list',
        query: {
          a: 1,
          b: 2
        }
      })
    }
  }
}
</script>

<style lang="less" scoped>
.title {
  color: @red;
  font-size: @font30;
}
</style>
