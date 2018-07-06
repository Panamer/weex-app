<template>
  <div class="wrapper">
    <image :src="get_img_path('03.jpg')" class="logo" />
    <text>{{img_path}}</text>
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
    },
    get_img_path (img_name) {
      // 获取图片在三端上不同的路径
      	// e.g. 图片文件名是 test.jpg, 转换得到的图片地址为
      	// - H5      : http: //localhost:1337/src/images/test.jpg
      	// - Android : local:///test
      	// - iOS     : ../images/test.jpg
        let platform = weex.config.env.platform
    		this.platform = weex.config.env.platform
    		let img_path = ''

    		if (platform == 'Web') {
    			img_path = `http://10.134.190.11:8081/images/${img_name}`
    		} else if (platform == 'android') {
    			// android 不需要后缀
    			img_name = img_name.substr(0, img_name.lastIndexOf('.'));
    			img_path = `local:///${img_name}`
    		} else {
    			img_path = `local://${img_name}`
    		}
        this.img_path = img_path
    		return img_path
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
