<template>
  <div class="wrapper clearfix">
    <div class="content">
      <TheHeader/>
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
body {
  background-color: rgb(240, 242, 245);
  font-family: "open sans", "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  color: #676a6c;
}
</style>