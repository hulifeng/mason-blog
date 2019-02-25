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
          <dt>开发宝典</dt>
          <dd>PHP手册</dd>
          <dd>Laravel手册</dd>
          <dd>Mysql手册</dd>
        </dl>
        <dl class="col-xs-2">
          <dt>学习路线</dt>
          <dd>Linux学习指南</dd>
          <dd>Laravel学习指南</dd>
          <dd>Python学习指南</dd>
          <dd>Mysql学习指南</dd>
        </dl>
        <dl class="col-xs-2">
          <dt>面试王中王</dt>
          <dd>PHP面试模板</dd>
          <dd>简历模板</dd>
          <dd>Mysql面试宝典</dd>
          <dd>Linux面试宝典</dd>
        </dl>
        <dl class="col-xs-2">
          <dt>资源推荐</dt>
          <dd>暂无内容~</dd>
        </dl>
        <dl class="col-xs-2">
          <img src="../../assets/QRcode.jpg" alt="Ans-小锋" title="Ans-小锋" class="img-responsive img-rounded">
          <div class="contact text-center">
              <p>扫一扫 contact me</p>
          </div>
        </dl>
      </div>
    </div>
    <div class="copyright">
      <div class="container">
        <strong>Copyright</strong> © 2018 友叹-USIGH - All rights reserved - 冀ICP备18012344号
        <div class="pull-right">
          <strong>www.usigh.com</strong>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.footer {
  position: absolute;
  bottom: 0;
  width: 100%;
  display: inline-block;
  background-color: #fff;
  strong {
    font-weight: 700;
  }
  .footer-nav {
    padding: 40px 0 20px 0;
    dt {
      margin-bottom: 30px;
    }
    dd {
      margin: 5px 0;
      color: #676a6c;
    }
  }
  .copyright {
    padding: 6px 0;
    line-height: 40px;
    border-top: 1px solid #e7eaec;
  }
}
</style>
