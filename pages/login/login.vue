<template>
<view class="container">
  <view class="login-icon">
    
    <image src="../../static/images/xiao.png" class="login-img"></image>
    <text class="login-text">欢迎来到星际云通</text>

  </view>
  <view class="login-from">
 
    <!--手机号-->
    <view class="inputView">
      
      <input class="inputText" maxlength="11" @input="getPhoneValue" type="text" id="phone" name="phone" placeholder="请输入手机号" autocomplete="off" onkeyup="checkMobile($(this))" :value="phone"></input>
    	<text class="tips">{{phoneTip}}</text>

    </view>
    <view class="line"></view>
 
    <!--获取验证码-->
    <view class="keyCodeBox">
			<input class="keyCode" bindinput="getCodeValue" :value="code" type="text" id="code" name="code" placeholder="请输入验证码"></input>
			<button :class="'sendBtn ' + (isChecked?'btnCode':'')" bindtap="getVerificationCode" :disabled="disabled" name="sendcode" id="sendcode">{{codename}}</button>
		</view>
    <view class="line"></view>  
  
    <!--注册-->
  <button class="changeBtn" bindtap="save">登录</button>

  </view>
</view>
</template>

<script>
//index.js
//获取应用实例
export default {
  data() {
    return {
        phone: '',
        code:'',
        iscode:'',
        codename:'',
    };
  },
    methods: {
      //获取input输入框的值
      getNameValue: function (e) {
        this.name = e.detail.value
      },
      //判断手机号长度
      getPhoneValue: function (e) {
        if (e.detail.value.length == 11) {
          this.disabled = false
        }
        this.phone = e.detail.value
      },
      getCodeValue: function (e) {
        this.code = e.detail.value
      },
      getCode: function () {
        var myreg = /^(16[0-9]|14[0-9]|13[0-9]|15[0-9]|17[0-9]|18[0-9]|19[0-9])\d{8}$$/;
        if(this.data.phone == '') {
            uni.showToast({
                title: '手机号不能为空',
                icon: 'none',
                duration: 1000
            });
           
        }else if (!myreg.test(this.$data.phone)) {
            uni.showToast({
                title:'请输入手机号',
                icon:'none',
                duration: 1000
            })
        }else {
            let aphone = this.data.phone
            var website = getApp().globalData.website
        }
      },
     save: function () {
    var _this = this;
    var open_id = getApp().globalData;
    var website = getApp().globalData.website
    var a = this.data.phone;
    var code = this.data.code;
    var phone = this.data.phone;
    let aphone = this.data.phone;
    let iscode = this.data.code;
    // var pre = that.data;
    var myreg = /^(16[0-9]|14[0-9]|13[0-9]|15[0-9]|17[0-9]|18[0-9]|19[0-9])\d{8}$$/;

    if (this.data.phone == "") {
      wx.showToast({
        title: '手机号不能为空',
        icon: 'none',
        duration: 1000
      })
      return false;
    } else if (!myreg.test(this.data.phone)) {
      wx.showToast({
        title: '请输入正确的手机号',
        icon: 'none',
        duration: 1000
      })
      return false;
    }
    },
    },
}
</script>
<style>
page{
  height: 100%;
  width: 100%;
}
 
.container {
  height: 100%;
  display: flex;
  flex-direction: column;
  padding: 0;
  box-sizing: border-box;
  background-color: #fff;
} 
 
/*登录图片*/
.login-icon{
  flex: none;
  height: 450rpx;
  width: 600rpx;
  display: flex;
  align-items: center;
  padding-left: 60rpx;
}
.login-img{

  width: 112rpx;
  height: 100rpx;
  margin-top: 39rpx;
}
.login-text{
   font-weight:bold;
  font-size: 58rpx;
  color: #01c0dd;
  margin-top: 20rpx;
  margin-left: 20rpx;
}


/*表单内容*/
.login-from {
  margin-top: 20px;
  flex: auto;
  height:100%;
  width: 80%;
}
 
.inputView {
  display: flex;
  background-color: #fff;
  line-height: 100rpx;
}

.keyCodeBox {
  display: flex;
  background-color: #fff;
  line-height: 100rpx;
  text-align: center;
}
.keyCode{
  flex: 1;
  float: left;
  text-align: left;
  margin-left: 40rpx;
  margin-top: 35rpx;
  color: #000;
  font-size: 38rpx;
}
.sendBtn{
  align-items: center;
  background: none !important;
  outline:none;
  flex: 1;
  text-align: center;
  height: 100rpx;
  font-size: 38rpx;
  margin-left: 40rpx;
  margin-top: 10rpx;
  

}
.sendBtn::after{
  border: none;
}
 

.inputText {
  flex: 1;
  float: left;
  text-align: left;
  margin-left: 40rpx;
  margin-top: 3rpx;
  margin-bottom: 10rpx;
  color: #000;
  height:100rpx;
  font-size: 38rpx;
}
 
.line {
  display: flex;
  width: 125%;
  height: 1px;
  background-color: #cccccc;
  margin-top: 1px;
}
/*按钮*/
.changeBtn{
  width: 96%;
  height: 100rpx;
  background:#01c0dd;
  color: #fff;
  border-radius: 30rpx;
  bottom: 25%;
  left: 62%;
  margin-left: -48%;
  line-height: 100rpx;
  margin-top: 50%;
  font-size: 42rpx;
}

</style>