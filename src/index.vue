<template>
  <div class="wrapper">
    <image :src="logo" class="logo" />
    <text>./images/03.jpg PC可以显示 虚拟机不能显示</text>
    <text class="greeting" @click="toApp">Bottom is router-view  Let‘s Go !</text>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      logo: 'http://www.bslxx.com/uploads/180506/1-1P506135342102.jpg'
    }
  },
  methods: {
    toApp () {
      this.$router.push({
        name: 'HelloWorld'
      })
    }
  }
}
</script>

<style scoped>
  .wrapper {
    /* justify-content: center; */
    align-items: center;
  }
  .logo {
    width: 700px;
    height: 400px;
  }
  .greeting {
    text-align: center;
    margin-top: 70px;
    margin-bottom: 70px;
    font-size: 50px;
    color: #41B883;
  }
  .message {
    margin: 30px;
    font-size: 32px;
    color: #727272;
  }
</style>
