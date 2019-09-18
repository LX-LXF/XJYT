<template>
	<view>
		<view class='enter'>
		  <view>
		  <image class='enter-2' src='../../static/images/suo.jpg'></image> 
		
		   <input class="weui-input1"  password="true" placeholder="输入资金密码（6位数字）" bindinput="setPassword"/>
		
		  </view>
		  </view>
		
		  <view class='enter'>
		  <view>
		  <!-- <view class="line1"></view> -->
		  <image class='enter-2' src='../../static/images/suo.jpg'></image> 
		
		  <input class="weui-input1"  password="true" placeholder="再次输入资金密码" bindinput="setConfirm"/>
		  </view>
		  </view>
		
		  <view class='enter'>
		  <view>
		  <!-- <view class="line1"></view> -->
		  <image class='enter-2' src='../../static/images/email.png'></image> 
		
		  <view class="email" style="margin-left:100rpx;font-size:30rpx;line-height:120rpx;" >{{email}}</view>
		  </view>
		  </view>
		
		  <view class='enter'> 
		  <view>
		  <!-- <view class="line1"></view> -->
		  <image class='enter-2' src='../images/yanzheng.png'></image> 
			<input class="weui-input1" bindinput="getCodeValue" value='{code}' type="text" id="code" name="code" placeholder="请输入邮箱验证码"/>
		
			<button class="sendBtn {isChecked?'btnCode':''}" bindtap='sendCode' disabled='{disabled}' name="sendcode" id="sendcode">{{codename}}</button>
		
		
		
		</view>
		  </view>
		
		<view class='out2'>
		 <button class='changeBtn2' bindtap='save1' hoverclass='btn_hover'>确定保存</button>
		</view>
	</view>
</template>
<!-- 设置资金密码 -->
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
  margin: 5rpx 0 ;

  background: #fff;

  overflow: hidden;

  position:relative;
  
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

  width: 50rpx;

  height: 50rpx;

  float: left;

  margin-left: 30rpx;


  margin-top: 30rpx;

  color: #808080;

  margin-bottom: 30rpx;

  opacity: 0.4;

}
.weui-input1{
  ime-mode:disabled;
  width: 500rpx;
  font-size: 30rpx; 

  display:block;

  float:left;

  padding-top: 32rpx;

  padding-left: 35rpx;

  margin-top: 0rpx;

  margin-bottom: 30rpx;

}

 
.line1{
  width: 100%;
  height: 1rpx;
  background-color: #808080;
}

.out2{
  margin: 200rpx 0 ;

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


.sendBtn{
    background: none !important;
   outline:none;
   text-align: right;
   font-size: 30rpx;
    position:absolute;
    right:48rpx;
    top:24rpx;
    color:red;
}
.sendBtn::after{
  border: none;
}
</style>
