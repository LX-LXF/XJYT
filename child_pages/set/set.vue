<template>
	<view>
		<view class='top'>
		  <view class='sub' bindtap='personal'>
            <image src="../../static/images/user3.jpg" class="tu1"></image>
		    <view class='sub-title'>个人资料  </view>
		    <image src="../../static/images/jiantou3.png" class="tu"></image>
		    <view class="line1"></view>
		  </view>
		 
		  <view class='sub4' bindtap= "balance">
		    <image src="../../static/images/user2.jpg" class="tu1"></image>
		    <view class='sub-title'>我的余额</view>
		    <image src="../../static/images/jiantou3.png" class="tu"></image>
		     <view class="line1"></view>
		  </view>
		
		  <view class='sub4' bindtap='wallet'>
		    <image src="../../static/images/wallet.jpg" class="tu1"></image>
		    <view class='sub-title'>我的钱包</view>
		    <image src="../../static/images/jiantou3.png" class="tu"></image>
		     <view class="line1-te"></view>
		  </view>
		 
		  <view class='sub2' bindtap="{authentication==1?'identity':''}">
            <image src="../../static/images/user1.jpg" class="tu1"></image>
		    <view class='sub-title'>身份认证</view>
		    <view class='sub-te' uniif="{authentication==1}">未认证</view>
		    <view class='sub-te' uniif="{authentication==2}">认证中</view>
		    <view class='sub-te' uniif="{authentication==3}">已认证</view>
		    <image src="../../static/images/jiantou3.png" class="tu"></image>
		    <view class="line1"></view>
		  </view>
		  
		  <view class='sub3' bindtap="{email?'':'security'}">
            <image src="../../static/images/user5.jpg" class="tu1"></image>
		    <view class='sub-title' >安全认证</view>
		    <view class='sub-te1'>{{email?'已认证':'未认证'}}</view>
		    <image src="../../static/images/jiantou3.png" class="tu"></image>
		    <view class="line1"></view>
		  </view>
		
		  <view class='sub4' bindtap='capital'>
            <image src="../../static/images/an.jpg" class="tu1"></image>
		    <view class='sub-title'>资金安全密码设置</view>
		    <image src="../../static/images/jiantou3.png" class="tu"></image>
		    <view class="line1"></view>
		  </view>
		
		  <view class='sub4' bindtap='osave'>
            <image src="../../static/images/user4.jpg" class="tu1"></image>
		    <view class='sub-title'>解除绑定</view>
		    <image src="../../static/images/jiantou3.png" class="tu"></image>
		    <view class="line1"></view>
		  </view>
		</view>
	</view>
</template>
<!-- //设置 -->
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
/* miniprogram/pages/index9/index9.wxss */
page{
  /* background: #dfdfdf; */
}
.top{
  height: 100%;

  background: #fff;

}
.sub{
  background:#fff;

  margin-top: 40rpx;
}
.sub-title{
  /* font-weight:bold; */

  background: #fff;

  display: block;

  align-items: left;

  padding-left: 45rpx;

  font-size:32rpx;

  margin-top: 40rpx;

  margin-bottom: 30rpx;
}
.line1{
  width: 100%;

  height: 5rpx;

  background-color: #f2f2f2;
}

.tu{
  display: block;

  float: right;

  margin-top: -64rpx;

  width:18rpx;

  height:24rpx;

  margin-right:50rpx;
}
.line1-te{
  width: 100%;

  height: 80rpx;

  background-color: #f2f2f2;
}
.tu1{
  float: left;

  width: 50rpx;

  height: 50rpx;

  margin-left: 45rpx;

  padding-right: 45rpx;
}
.changeBtn{
  background: #74d8e7;

  color: #fff;

      width: 100%;

      height: 100rpx;

    position: fixed;

    text-align:center;

    bottom: 0rpx;

    line-height:100rpx;
}
.sub-te{
  float: left;

  width: 110rpx;

  height:36rpx;

  font-size: 26rpx;

  margin-left: 530rpx;

  background: #ead637;

  color: #fff;

  margin-top: -72rpx;

  text-align: center;
}
.sub-te1{
  float: left;

  width: 110rpx;

  height:36rpx;

  font-size: 26rpx;

  margin-left: 530rpx;

  background: #ead637;

  color: #fff;

  margin-top: -72rpx;

  text-align: center;
}
.zan-dialog__mask {
  position: fixed;

  top: 0;

  left: 0;

  right: 0;
  
  bottom: 0;

  z-index: 10;

  background: rgba(0, 0, 0, 0);

  display: none;
}

.zan-dialog__container {
  position: fixed;

  bottom: 400rpx;

  width: 650rpx;

  height: 350rpx;

  margin-left: 50rpx;

  background: #f8f8f8;

  transform: translateY(300%);

  transition: all 0.4s ease;

  z-index: 12;
  
  border-radius: 20rpx;

  box-shadow: 0px 3px 3px 2px gainsboro;
  
}

.zan-dialog--show .zan-dialog__container {
  transform: translateY(0);
}

.zan-dialog--show .zan-dialog__mask {
  display: block;
}
</style>
