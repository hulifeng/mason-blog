<template>
  <div class="header">
    <nav class="navbar navbar-static-top" role="navigation" id="nav">
      <div class="container">
        <div class="navbar-header">
          <button
            type="button"
            class="navbar-toggle collapsed m-r-sm"
            data-toggle="collapse"
            data-target="#bs-example-navbar-collapse-1"
            aria-expanded="false"
          >
            <span class="sr-only">Toggle navigation</span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
          </button>
          <router-link to="/" class="navbar-brand blog-logo">Laravel</router-link>
        </div>

        <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
          <ul class="nav navbar-nav">
            <li
              :class="{'active': activeIndex === $index}"
              v-for="(item, $index) in navList"
              :key="item.num"
            >
              <a :href="item.link" @click="changeNavIndex($index)">{{item.title}}</a>
            </li>
          </ul>
          <TheEntry/>
          <!-- 登录后展示 -->
          <!-- <ul class="nav navbar-nav navbar-right">
            <li class="dropdown pull-right">
              <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">
                Mason
                <span class="caret"></span>
              </a>
              <ul class="dropdown-menu">
                <li>
                  <a href="#">个人资料</a>
                </li>
                <li>
                  <a href="#">修改资料</a>
                </li>
                <li>
                  <a href="#">退出登录</a>
                </li>
              </ul>
            </li>
          </ul>-->
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
import TheEntry from "@/components/layouts/TheEntry";
export default {
  data() {
    return {
      logo: {
        src: "laravel blog",
        title: "laravel-blog"
      },
      navList: [
        {
          link: "/",
          title: "首页"
        },
        {
          link: "#",
          title: "发现"
        },
        {
          link: "#",
          title: "文章"
        },
        {
          link: "#",
          title: "每日精进"
        },
        {
          link: "#",
          title: "分类"
        },
        {
          link: "#",
          title: "话题"
        }
      ],
      activeIndex: 0
    };
  },
  methods: {
    changeNavIndex(index) {
      this.activeIndex = index;
    }
  },
  components: {
    TheEntry
  }
};
</script>

<style lang="scss" scoped>
.header {
  #nav {
    background-color: #fff;
    border-color: #e7e7e7;
    box-shadow: 0 1px 11px 2px rgba(42, 42, 42, 0.1);
  }
  .navbar-toggle {
    background-color: #1ab394;
    .icon-bar {
      background-color: #fff;
    }
  }
  .navbar-brand {
    color: #1ab394;
    font-weight: 700;
  }
  .nav > li.active a {
    border-left: 4px solid #19aa8d;
    background: #293846;
    color: #fff;
  }
  .nav > li > a {
    color: #676a6c;
    font-weight: 600;
  }
  .dropdown-menu > li > a {
    border-radius: 3px;
    color: #676a6c;
    line-height: 25px;
    margin: 4px;
    text-align: left;
    &:hover {
      color: black;
    }
  }
}
</style>
