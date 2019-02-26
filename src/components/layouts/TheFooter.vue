<template>
  <div class="footer">
    <div class="container">
      <div class="footer-nav row">
        <dl class="col-xs-2">
          <dt>服务商</dt>
          <dd>
            <img src="../../assets/tengxunyun.png" alt="腾讯云" title="腾讯云">
          </dd>
        </dl>
        <dl class="col-xs-2">
          <dt>{{dictionary.title}}</dt>
          <dd v-for="item in dictionary.list" :key="item.num">
              <a href="{item.link}">{{item.name}}</a>
          </dd>
        </dl>
        <dl class="col-xs-2">
          <dt>{{learningWay.title}}</dt>
          <dd v-for="item in learningWay.list" :key="item.num">
              <a href="{item.link}">{{item.name}}</a>
          </dd>
        </dl>
        <dl class="col-xs-2">
          <dt>{{interView.title}}</dt>
          <dd v-for="item in interView.list" :key="item.num">
              <a href="{item.link}">{{item.name}}</a>
          </dd>
        </dl>
        <dl class="col-xs-2">
          <dt>{{source.title}}</dt>
          <dd v-for="item in source.list" :key="item.num">
              <a href="{item.link}">{{item.name}}</a>
          </dd>
        </dl>
        <dl class="col-xs-2">
          <img
            src="../../assets/QRcode.jpg"
            alt="Ans-小锋"
            title="Ans-小锋"
            class="img-responsive img-rounded"
          >
          <div class="contact text-center">
            <p>扫一扫 contact me</p>
          </div>
        </dl>
      </div>
    </div>
    <div class="copyright" v-html="copyright"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      copyright: `
       <div class="container">
        <div class="copyright-left">
         <strong>Copyright</strong> © 2018-2019 友叹-USIGH - 冀ICP备18012344号
        </div>
        <div class="domain">
          <strong>www.usigh.com</strong>
        </div>
      </div>
      `,
      dictionary: {
        title: "开发宝典",
        list: [
          {
            name: "PHP手册",
            link: "#"
          },
          {
            name: "Laravel手册",
            link: "#"
          },
          {
            name: "Mysql手册",
            link: "#"
          }
        ]
      },
      learningWay: {
        title: "学习路线",
        list: [
          {
            name: "Laravel学习指南",
            link: "#"
          },
          {
            name: "PHP学习指南",
            link: "#"
          },
          {
            name: "Mysql学习指南",
            link: "#"
          },
          {
            name: "ThinkPHP学习指南",
            link: "#"
          },
          {
            name: "Linux学习指南",
            link: "#"
          }
        ]
      },
      interView: {
        title: "面试王中王",
        list: [
          {
            name: "PHP面试宝典",
            link: "#"
          },
          {
            name: "简历模板",
            link: "#"
          },
          {
            name: "Mysql面试宝典",
            link: "#"
          },
          {
            name: "Linux面试宝典",
            link: "#"
          }
        ]
      },
      source: {
        title: "资源推荐",
        list: [
          {
            name: "暂无资源~",
            link: "#"
          }
        ]
      }
    };
  }
};
</script>

<style lang="scss" scoped>

</style>
