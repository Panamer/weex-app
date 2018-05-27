<template>
  <div>
    <text class="message" @click="toVue('router')"> {{tip1}} </text>
    <text class="message" @click="toVue('navigator')"> {{tip2}} </text>
  </div>
</template>

<script>
const navigator = weex.requireModule('navigator')
const modal = weex.requireModule('modal')
export default {
  data () {
    return {
      tip1: 'Jump by Router',
      tip2: 'Jump by Navigator'
    }
  },
  methods: {
    toVue (flag) {
      if (flag === 'router') {
        this.$router.push({
          name: 'First'
        })
      } else {
        navigator.push({
          url: 'http://weex.apache.org/cn/references/modules/navigator.html',
          animated: 'true'
        }, event => {
          // modal.toast({ message: 'callback ok: ' + event })
          navigator.pop({
            animated: 'true'
          }, event => {
            modal.toast({ message: 'callback ok: ' + event })
          })
        })
      }
    }
  }
}
</script>

<style scoped>
  .message {
    margin-bottom: 30px
  }
</style>
