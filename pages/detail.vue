<template>
  <div>
    <h1>this is detail page, {{title}}</h1>
    <div @click="message">id: {{$route.query.id}}</div>
  </div>
</template>

<script>
export default {
  layout: 'blog',
  loading: true,
  transition: {
    name: 'test',
    mode: 'out-in'
  },
  data () {
    return {
      title: ''
    }
  },
  asyncData (context, callback) {
    console.log('context: ',context)
    context.store.commit('add', 123)
    context.store.commit('add', 456)
    setTimeout(() => {
      callback(null, { title: 'the title from ajax' })
    }, 2000)
  },
  methods: {
    message () {
      this.$Message.loading({
        content: 'loading',
        duration: 4000
      })
    }
  }
}
</script>