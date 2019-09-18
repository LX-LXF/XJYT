<template>
	<view>
		<view class='enter'>
		  <view>
		  <text class='enter-2'>姓名</text>
		
		  <input class="weui-input1" placeholder="请填写真实姓名" maxlength="11" value="{account}" focus="true" name="account"/>
		  </view>
		  </view>
		
		  <view class='enter'>
		  <view>
		  <!-- <view class="line1"></view> -->
		  <text class='enter-2'>身份证号</text>
		
		  <input class="weui-input1" placeholder="请填写完整的身份证号"  value="{account}" focus="true" name="account"/>
		  </view>
		  </view>
		
		<view class="container">
		  <text class='container1'>上传身份证<text style='color:red'>人像</text>面</text>
		  <image class='shen1' src='../../static/images/shen1.jpg'></image>
		  <button class='shen1-1' bindtap='chooseImageTap'><image class='shen1-1-1' src='../../static/images/jia.jpg'></image></button>
		  <text class="click" style="font-size:30rpx;margin-top:20rpx;">点击上传</text>
		</view>
		
		<view class="container">
		  <text class='container2'>上传身份证<text style='color:red'>国徽</text>面</text>
		  <image class='shen1' src='../../static/images/shen1.jpg'></image>
		  <button class='shen1-1' bindtap='chooseImageTap'><image class='shen1-1-1' src='../../static/images/jia.jpg'></image></button>
		  <text class="click" style="font-size:30rpx;margin-top:20rpx;">点击上传</text>
		</view>
		
		<view class="line2">
		   <view class="reque">拍摄图片要求</view>
		</view> 
		<view class="idcard">
		  <view class="id1">
		  <image class="c" src='../../static/images/card.png'></image>
		  <view class="biaozhun">
		     <image class="y" src='../../static/images/yes.png'></image>
		     <text class='pai'>标准拍摄</text>
		  </view>
		  </view>
		   <view class="id1">
		   <image class="c" src='../../static/images/card2.png'></image>
		  <view class="biaozhun">
		     <image class="y" src='../../static/images/no.png'></image>
		     <text class='pai'>边框缺失</text>
		  </view>
		   </view>
		    <view class="id1">
		    <image class="c" src='../../static/images/card3.png'></image>
		  <view class="biaozhun">
		     <image class="y" src='../../static/images/no.png'></image>
		     <text class='pai'>照片模糊</text>
		  </view>
		    </view>
		     <view class="id1">
		     <image class="c" src='../../static/images/card4.png'></image>
		  <view class="biaozhun">
		     <image class="y" src='../../static/images/no.png'></image>
		     <text class='pai'>闪光强烈</text>
		  </view>
		     </view>
		</view>
		<view class='out2'>
		 <button class='changeBtn2' bindtap='save1' hoverclass='btn_hover'>提交审核</button>
		</view>
	</view>
</template>
<!-- 身份认证 -->
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
.enter{
  margin: 30rpx 0 ;

  background: #fff;

  overflow: hidden;
  
}
.img{
  float: left;

  display:block;

  width: 30rpx;

  height: 30rpx;

  margin-left: 232rpx;

  padding-top: 30rpx;

  margin-top:12rpx;

  padding-bottom: 30rpx;
}
.enter-2{
  display:block;

  float: left;

  margin-left: 30rpx;

  font-size: 32rpx;

  margin-top: 30rpx;

  color: #808080;

  margin-bottom: 30rpx;

}
.weui-input1{
  ime-mode:disabled;

  font-size: 30rpx; 

  display:block;

  float:left;

  margin-top: 24rpx;

  margin-left: 30rpx;

  /* margin-bottom: 30rpx; */

}
.line1{
  width: 100%;
  height: 1rpx;
  background-color: #808080;
}
/* .container{
  height: 300rpx;
  width: 500rpx;
} */
.container .prev{
  width:250px;
  height:150px;
  overflow: hidden;
}

.container1{
  display: block;

  margin-top: 24rpx;

  margin-bottom: 24rpx;
}
.shen1{
  width: 500rpx;

  height: 300rpx;

  opacity: 0.4;
}
.shen1-1{
  float: left;

  width: 100rpx;

  height: 100rpx;

  border-radius: 50rpx;

  margin-top: -200rpx;
  border:none;

}
.shen1-1:after{
  border: none
}
.shen1-1-1{
   width: 100rpx;

  height: 100rpx;

  margin-left: -25rpx;
}
.container2{
    display: block;

  margin-top: 150rpx;

  margin-bottom: 24rpx;

}
.line2{
  width:100%;
  height:2rpx;
  border-top:2rpx solid #ccc;
  position: relative;
  margin-top:100rpx;
}
.reque{
  width:200rpx;
  height:40rpx;
  background: #f2f2f2;
  font-size: 28rpx;
  text-align: center;
  position: absolute;
  top:-20rpx;
  left:275rpx;
}
.idcard{
   width:650rpx;
   height:150rpx;
   margin:50rpx auto 0;
   display: flex;
   justify-content: space-between;

}
.id1{
  width:130rpx;
  height:150rpx;
}
.c{
  width:100%;
  height:80rpx;
}
.biaozhun{
  width:100%;
  height:70rpx;
}
.y{
  width:30rpx;
  height:30rpx;

}
.pai{
  font-size: 20rpx;
  margin-left:10rpx;
  line-height: 30rpx;
}
.out2{
  margin: 100rpx 0 ;

  /* background: #fff; */

  overflow: hidden;
}
.changeBtn2{
  float:right;

  display: flex;

  width: 94%;

  height: 80rpx;

  font-size: 30rpx;

  margin-top: 25rpx;

  margin-right: 25rpx;

  background-color:#30bcd5;

  color: #fff;

  margin-bottom: 25rpx;

  flex-direction: column;

  justify-content: center;

  align-items: center;
  
  border-radius: 15rpx;
 
  /* border-left:1rpx solid #8f8f8f */
}
</style>
