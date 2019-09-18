
<template>
	<view>
		<view class='te'>
		  <view class='box'>现货账户</view>
		
		  <view class='box1'>
		
		  <text class='box1-1'>{{fil_count}} </text>
		
		  <text class='box1-2'>FIL </text>
		  
		  </view>
		
		  <view class='box2'>
		
		  <text class='box2-1'>可用：{{fil_count-lock_num}} </text>
		
		  <text class='box2-2'>锁定：{{lock_num}} </text>
		  
		  </view> 
		
		  <image class='img' src='../../stasic/images/FIL.jpg'></image>
		
		  <view class='ensp'>
		
		     <button class='ensp1' bindtap='' hoverclass='btn_hover'>转入</button>
		
		     <!-- <view class='linex'></view> -->
		
		     <button class='ensp2' bindtap='withdraw' hoverclass='btn_hover'>转出</button>
		
		  </view>
		
		</view>
	</view>
</template>
<!-- 我的余额 -->
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
  background: #f2f2f2;
}
.te{
  background: #fff;

  margin: 30rpx 30rpx;

  border-radius: 30rpx;
}
.ensp{
  overflow: hidden;
}
.ensp1{
  width: 50%;

  float: left;

  font-size: 36rpx;

  background:#e5e5e5;

  color: #000;

border-right:2rpx solid #f2f2f2;
  border-bottom-left-radius: 30rpx;
}
.ensp1::after{

  border: none;

}
.ensp2{
  width: 50%;

  float: right;

  font-size: 36rpx;

  background:#e5e5e5;

  color: #000;

  border-bottom-right-radius: 30rpx;
}
.ensp2::after{
  border: none;
}
button{
  border-radius: 0px;
}
.box{
  padding-top: 30rpx;

  margin-left: 30rpx;

  font-size: 32rpx;

  color: #808080;
}
.box1{
    margin-top: 30rpx;
}
.box1-1{
  margin-left: 30rpx;

  font-size: 46rpx;
}
.box1-2{
  margin-left: 30rpx;

  font-size: 32rpx;

  color: #808080;
}
.box2{
  margin-top: 30rpx;

  padding-bottom: 30rpx;
}
.box2-1{
  margin-left: 30rpx;

  font-size: 32rpx;

   color: #808080;

}
.box2-2{
  margin-left: 30rpx;

  font-size: 32rpx;

   color: #808080;
}
.img{
  width: 190rpx;

  height: 190rpx;

  float: right;

  margin-right: 30rpx;
  
  margin-top: -230rpx;
}
</style>
