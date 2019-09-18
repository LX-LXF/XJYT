<template>
	<view>
		<view class="nav_right_items">
  <text class='te'>头像</text>
  <open-data type="userAvatarUrl" class='te11'></open-data>
</view>
<view class="line1"></view>

<view class="nav_right_items">
  <text class='te'>昵称</text>
  <open-data type="userNickName" class='te1'></open-data>
</view>
<view class="line1"></view>

<view class="nav_right_items">
  <text class='te'>姓名</text>
  <text class='te1'>{{name}}</text>
</view>
<view class="line1"></view>

<view class="nav_right_items">
  <text class='te'>性别</text>
  <text class='te1' uniif="{gender == 'male'}">男</text>
  <text class='te1' unielif="{gender == 'female'}">女</text>
  <text class='te1' unielif="{gender == 'secret'}">未知</text>
</view>
<view class="line1"></view>

<view class="nav_right_items">
  <text class='te'>省份</text>
  <text class='te1'>{{provices}}</text>
</view>
<view class="line1"></view>

<view class="nav_right_items">
  <text class='te'>城市</text>
  <text class='te1'>{{city}}</text>
</view>
<view class="line1"></view>

<view class="nav_right_items">
  <text class='te'>联系电话</text>
  <text class='te1'>{{mobile}}</text>
</view>
<view class="line1"></view>

<view class="nav_right_items">
  <text class='te'>联系地址</text>
  <text class='te111'>{{address}}</text>
</view>
<view class="line1"></view>
	</view>
</template>
<!-- 个人资料 -->
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
.line1{
  width: 100%;

  height: 3rpx;

  background-color: #f2f2f2;
}
.te{
  /* font-weight:bold; */

  background: #fff;

  display: block;

  align-items: left;

  padding-left: 45rpx;

  font-size:32rpx;

  margin-top: 40rpx;

  margin-bottom: 30rpx;
}
.te1{
  display: block; 

  float: right;

  margin-top: -70rpx;

  margin-right: 50rpx;

  font-size:30rpx;

  white-space: pre-wrap;

  color: #7e7c7c
}
.te11{
  display: block;  

  float: right;

  margin-top: -96rpx;

  margin-right: 35rpx;

  font-size:30rpx;

  width: 85rpx;

  height:85rpx;
}
.te111{
  /* display: block;   */

  float: right;

  margin-top: -96rpx;

  margin-right: 26rpx;

  font-size:30rpx;

  width: 320rpx;

  color: #7e7c7c;

   margin-bottom: 10rpx;
}
.line1-te{
  width: 100%;

  height: 80rpx;

  background-color: #f2f2f2;

}
.nav_right_items{
  height:100%;
  
  overflow: hidden;
}
</style>
