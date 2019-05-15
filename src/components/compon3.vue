<template>
  <div class="info">
    <h1>作品集/Profile</h1>
    <transition
      :duration="{ enter: 2500, leave: 1500 }"
      enter-active-class="animated fadeInRight">
      <div class="cont"  v-if="show">
        <el-row :gutter="20">
          <template v-for="item in profiles">
            <el-col :key="item.name" :span="12" :xs="24">
              <div class="item">
                <h2 v-text="item.name"></h2>
                <p v-text="'技术栈: ' + item.skills"></p>
                <p v-text="item.content"></p>
                <a :href="item.web" target="_blank">
                <p v-text="'在线预览地址:' + item.web"></p>
                </a>
                <p v-text="'github地址: ' + item.github"></p>
              </div>
            </el-col>
          </template>
        </el-row>
      </div>
    </transition>
  </div>
</template>
<script>
export default {
  data () {
    return {
      show: false,
      profiles: [
        {
          name: '模拟去哪儿App(learn移动端,没有提供API，手写json数据模拟)',
          skills: 'vue vue-cli vue-router vuex axios stylus swiper node.js ',
          content: '这个代理商城项目有的前端页面，基本实现了首页的全部功能，分页搜索功能，点击字母寻找对应首页字母并跳转功能，地方名分类展示搜索，（用户登录注册页面因为没有官方API接口，所以暂时用官网的页面代替！）',
          web: 'http://www.theskytydd.cn/trave',
          github: 'https://github.com/Angeljacket/trave'
        },
        {
          name: '沛星商城(提供了官方API接口)',
          skills: 'node vue vue-cli vue-router vuex axios stylus node.js',
          content: '这是由一个商城项目的微信小程序转变成app或者网页页面，vue框架，数据库是官方提供的，基本实现了商城类页面的全部功能，登录注册，付款等皆可跑通，showcc作为官方api文档，github作为多人合作在线编写!',
          web: 'http://www.theskytydd.cn/Peixingshop',
          github: 'https://github.com/Angeljacket/Pei-sing-mall'
        },
        {
          name: '网页简历',
          skills: 'vue  vue-cli vue-router axios',
          content: '一份本人的网页求职简历! 只兼容pc端...',
          web: 'http://www.theskytydd.cn/master',
          github: 'https://github.com/Angeljacket/master'
        },
        {
          name: '锤子手机官网（移动端）',
          skills: 'vue  vue-cli vue-router axios',
          content: '获取了锤子手机官网的官方API文档，然后用axios获取数据,能自适应各种移动端手机!',
          web: 'http://www.theskytydd.cn/mobileChuizi',
          github: 'https://github.com/Angeljacket/mobileChuizi'
        }
      ]
    }
  },
  methods: {
    timeout () {
      setTimeout(() => {
        this.show = true
      }, 1000)
    }
  },
  mounted () {
    this.timeout()
  }
}
</script>

<style lang="less" scoped>
@import '../less/index.less';
.resume{
  height: auto;
}
.info {
  .info;
  .cont {
    .cont;
    width: 90%;
    .item {
      background-color: rgba(59, 123, 13, 0.2);
      padding: 10px;
      border-radius: 15px;
      margin: 10px auto;
      @media screen and (max-width: 768px) {
        padding: 5px;
        margin: 5px auto;
      }
      &:hover {
        border-radius: 25px;
        background-color: rgba(10, 135, 87, 0.3);
      }
      p {
        text-align: left;
        text-indent: 28px;
        font-size: 1.1rem;
        line-height: 1.2;
        @media screen and (max-width: 768px) {
          text-indent: 12px;
          font-size: 0.7rem;
          line-height: 1.1;
        }
      }
    }
  }
}
</style>
