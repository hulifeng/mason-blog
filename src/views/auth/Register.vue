<template>
  <div class="row">
    <div class="col-md-4 col-md-offset-4 floating-box">
      <div class="panel panel-default base-border">
        <div class="panel-body">
          <div class="form-group">
            <label class="control-label">用户名</label>
            <div class="input-group">
              <span class="input-group-addon" id="basic-addon1">
                <i class="fa fa-fw fa-id-card"></i>
              </span>
              <input
                type="text"
                class="form-control"
                placeholder="请填写用户名"
                aria-describedby="basic-addon1"
              >
            </div>
          </div>
          <div class="form-group">
            <label class="control-label">密码</label>
            <div class="input-group">
              <span class="input-group-addon" id="basic-addon1">
                <i class="fa fa-fw fa-lock"></i>
              </span>
              <input
                type="text"
                class="form-control"
                placeholder="请填写密码"
                aria-describedby="basic-addon1"
              >
            </div>
          </div>
          <div class="form-group">
            <label class="control-label">确认密码</label>
            <div class="input-group">
              <span class="input-group-addon" id="basic-addon1">
                <i class="fa fa-fw fa-lock"></i>
              </span>
              <input
                type="text"
                class="form-control"
                placeholder="请确认密码"
                aria-describedby="basic-addon1"
              >
            </div>
          </div>
          <div class="form-group">
            <label class="control-label">图片验证码</label>
            <div class="input-group">
              <span class="input-group-addon" id="basic-addon1">
                <i class="fa fa-fw fa-photo"></i>
              </span>
              <input type="text" class="form-control" placeholder="请填写验证码" aria-describedby="basic-addon1">
            </div>
          </div>
          <div class="thumbnail" title="点击图片重新获取验证码">
            <div class="captcha"></div>
          </div>
          <button type="submit" class="btn btn-lg btn-blog btn-block">
            <i class="fa fa-btn fa-sign-in"></i> 注册
          </button>
          <div class="to_login">
            <p class="text-center">已有账号？<a href="#">现在登录</a></p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Reigster"
};
</script>

<style lang="scss" scoped>
.thumbnail {
  width: 170px;
  margin-top: 10px;
  cursor: pointer;
}
.thumbnail .captcha {
  height: 46px;
  background: #e1e6e8;
}
// 注册样式
.input-group-addon {
  background-color: transparent;
}
.input-group .form-control {
  z-index: 0;
}
// 去掉 input 闪烁的光
.form-control:focus {
  box-shadow: none;
  border-color: #ccc;
}
input {
  border-left: none;
}
.base-border {
  border: none;
  box-shadow: 0 1px 6px #ccc;
}
.to_login {
  margin-top: 15px;
}
.btn-blog {
  background-color: #1ab394;
  color: #fff;
}
</style>
