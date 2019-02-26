<template>
  <div class="wrapper">
    <TheHeader/>
    <!-- 内容替换区域 -->
    <div id="content-wrapper" class="container content-wrapper">
      <router-view/>
    </div>
    <TheFooter/>
  </div>
</template>

<script>
import TheHeader from "@/components/layouts/TheHeader";
import TheFooter from "@/components/layouts/TheFooter";
export default {
  name: "App",
  components: {
    TheHeader,
    TheFooter
  }
};
</script>

<style lang="scss">
$icon-font-path: "~bootstrap-sass/assets/fonts/bootstrap/";
@import "~bootstrap-sass/assets/stylesheets/_bootstrap";

$fa-font-path: "~font-awesome/fonts/";
@import "~font-awesome/scss/font-awesome";

@import "./styles/main";
body {
  background-color: rgb(240, 242, 245);
  font-family: "open sans", "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  color: #676a6c;
  height: 100%;
}
.content-wrapper {
  min-height: 100%;
  margin-bottom: -310px;
  .content-wrapper:after {
    content: "";
    display: block;
  }
}
</style>