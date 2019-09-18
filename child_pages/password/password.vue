<template>
	<view>
        <!-- 修改资金密码 -->
        <view class='enter'>
          <view>
            <image class='enter-2' src='../../static/images/suo.jpg'></image>
            <input class="weui-input1" type="number" password="true" placeholder="请输入旧密码" bindinput="oldPassword" />
          </view>
        </view>
        <view class='enter'>
          <view>
            <image class='enter-2' src='../../static/images/suo.jpg'></image>
            <input class="weui-input1" type="number" password="true" value='{newPass}' placeholder="请输入新密码" bindinput="newPassword" />
          </view>
        </view>
        <view class='enter'>
          <view>
            <image class='enter-2' src='../../static/images/suo.jpg'></image>
            <input class="weui-input1" type="number" password="true" placeholder="再次输入新密码" bindinput="confirm" />
          </view>
        </view>
        <view class="forget" bindtap='forget'>忘记密码?</view>
        <view class='out2'>
          <button class='changeBtn2' bindtap='save' hover-class='btn_hover'>确认保存</button>
        </view>
	</view>
</template>
<!-- 修改资金密码 -->
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

</style>
<template>
	<view>
		
	</view>
</template>
<!-- 修改资金密码 -->
<script>
	export default {
		data() {
            codename: '发送'
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
/* miniprogram/pages/index_capital/index_capital.wxss */
page{
  background: #f2f2f2;
}
.enter{
  margin: 5rpx 0 ;

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

  font-size: 30rpx; 

  display:block;

  padding-top: 32rpx;

  padding-left: 35rpx;

  margin-top: 0rpx;

  /* margin-bottom: 30rpx; */

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
  align-items: center;
  background: none !important;
  outline:none;
  /* flex: 1; */
  text-align: right;
  font-size: 30rpx;
  margin-left: 40rpx;
  margin-top: -64rpx; 
  color: red;
}
.sendBtn::after{
  border: none;
}
</style>
