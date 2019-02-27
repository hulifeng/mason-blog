<template>
  <div class="row">
    <div class="col-md-4 col-md-offset-4 floating-box">
      <!-- 消息组件 -->
        <Message :show.sync="msgShow" :type="msgType" :msg="msg"/>
      <div class="panel panel-default base-border">
        <div class="panel-body" data-validator-form>
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
                v-model.trim="username"
                v-validator:input.required="{ regex: /^[a-zA-Z]+\w*\s?\w*$/, error: '用户名要求以字母开头的单词字符' }"
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
                type="password"
                class="form-control"
                placeholder="请填写密码"
                aria-describedby="basic-addon1"
                id="password"
                v-model.trim="password"
                v-validator.required="{ regex: /^\w{6,16}$/, error: '密码要求 6 ~ 16 个单词字符' }"
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
                type="password"
                class="form-control"
                placeholder="请确认密码"
                aria-describedby="basic-addon1"
                v-model.trim="cpassword"
                v-validator.required="{ target: '#password' }"
              >
            </div>
          </div>
          <div class="form-group">
            <label class="control-label">图片验证码</label>
            <div class="input-group">
              <span class="input-group-addon" id="basic-addon1">
                <i class="fa fa-fw fa-photo"></i>
              </span>
              <input
                type="text"
                class="form-control"
                placeholder="请填写验证码"
                aria-describedby="basic-addon1"
                v-model.trim="captcha"
                v-validator.required="{ title: '图片验证码' }"
              >
            </div>
          </div>
          <div class="thumbnail" title="点击图片重新获取验证码" @click="getCaptcha">
            <div class="captcha vcenter" v-html="captchaTpl"></div>
          </div>
          <button type="submit" class="btn btn-lg btn-success btn-block" @click="register">
            <i class="fa fa-btn fa-sign-in"></i> 注册
          </button>
          <div class="to_login">
            <p class="text-center">
              已有账号？
              <a href="#">现在登录</a>
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import createCaptcha from "@/utils/createCaptcha";
import ls from "@/utils/localStorage";
export default {
  name: "Register",
  data() {
    return {
      captchaTpl: "", // 验证码模板
      username: "", // 用户名
      password: "", // 密码
      cpassword: "", // 确认密码
      captcha: "", // 验证码
      msg: "", // 消息
      msgType: "", // 消息类型
      msgShow: false // 是否显示消息，默认不显示
    };
  },
  created() {
    this.getCaptcha();
  },
  methods: {
    getCaptcha() {
      const { tpl, captcha } = createCaptcha(6);

      this.captchaTpl = tpl;
      this.localCaptcha = captcha;
    },
    register(e) {
      this.$nextTick(() => {
        const target =
          e.target.type === "submit" ? e.target : e.target.parentElement;

        if (target.canSubmit) {
          this.submit();
        }
      });
    },
    submit() {
      if (this.captcha.toUpperCase() !== this.localCaptcha) {
        this.showMsg("验证码不正确");
        this.getCaptcha();
      } else {
        const user = {
          name: this.username,
          password: this.password,
          avatar: `https://api.adorable.io/avatars/200/${this.username}.png`
        };
        const localUser = ls.getItem("user");

        if (localUser) {
          if (localUser.name === user.name) {
            this.showMsg("用户名已存在");
          } else {
            this.login(user);
          }
        } else {
          this.login(user);
        }
      }
    },
    login(user) {
      ls.setItem("user", user);
      this.showMsg("注册成功", "success");
    },
    showMsg(msg, type = "warning") {
      this.msg = msg;
      this.msgType = type;
      this.msgShow = false;

      this.$nextTick(() => {
        this.msgShow = true;
      });
    }
  }
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
.captcha {
  font-size: 24px;
  font-weight: bold;
  user-select: none;
}
.flex {
  display: flex;
}
.flex1 {
  flex: 1;
}
.vcenter {
  align-items: center;
  @extend .flex;
}
.hcenter {
  justify-content: center;
  @extend .flex;
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
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
</style>
