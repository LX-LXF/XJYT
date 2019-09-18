<template>
	<view>
		<view class='box1'> 
		<view class="phone">
		  <image class='icon' src="../../static/images/email.png"></image>
		  <input class="tel" placeholder='请输入邮箱' bindinput='setEmail'></input>
		</view>
		<view class="phone">
		  <image class='icon2' src="../../stasic/images/yanzheng.png"></image>
		  <input class="tel" placeholder='请输入邮箱验证码' bindinput='setCode'></input>
		  <text class="code" bindtap='sendCode'>发送验证码</text>
		</view>
		<view class="btn" bindtap='bind'>绑定</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
page{
  width:100%;
  height:100%;
  background: #f2f2f2;
  z-index:2;
  /* padding-top:100rpx;
  box-sizing: border-box; */
}
.phone{
  width:100%;
  height:120rpx;
  background: #fff;
  border-bottom: 1px solid #f1f1f1;
}
.icon{
  width:45rpx;
  height:54rpx;
  margin-left:42rpx;
  margin-right:40rpx;
  margin-top:40rpx;
  float: left;
}
.icon2{
  width:45rpx;
  height:50rpx;
  margin-left:43rpx;
  margin-right:34rpx;
  margin-top:40rpx;
  float: left;
}
.tel{
  float: left;
  font-size: 28rpx;
  margin-top:40rpx;
  color: #808080;
}
.code{
  float: right;
  font-size: 24rpx;
  color:red;
  margin-top:50rpx;
  margin-right:48rpx;
}
.btn{
  width:680rpx;
  height:80rpx;
  margin:100rpx auto;
  text-align: center;
  line-height: 80rpx;
  color: #fff;
  background-color:#30bcd5;
  border-radius: 10rpx;
}
</style>
