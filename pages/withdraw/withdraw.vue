<template>
	<view>
		<!-- 转出 -->
		<view class='enter'>
		  <view class='enter-1'>转出地址</view>
		  
		  <view>
		  <image class='img' src='../../static/images/address.jpg'></image>
		  <text class='enter-2'>地址：</text>
		   <input class="weui-input1" placeholder="输入正确的转出地址" value="{address}" focus="true" bindinput='setAddress'/>
		  
		   <image class="wallet1" src="/pages/images/wallet.png" bindtap='gotoAddress'></image>
		    <view class="shu"></view>
		  </view>
		</view>
		
		<view class='out'>
		  <image class='img0' src='../../static/images/kuo.jpg'></image>
		  <view class='enter-11'>转出数量</view>
		  <view>
		  <image class='img1' src='../../static/images/FIL.jpg'></image>
		   <input class="weui-input11" placeholder="输入转出数量" value="{amount}" bindinput='setAmount'/>
		  </view>
		  <view class="line1"></view>
		  <view class='out1'>
		  <text class='bo'>可用余额：{{balance}}FIL</text>
		  </view>
		</view>
		
		<view class='enter'>
		  <view class='enter-1'>备注</view>
		  <view class="beizhu">
		   <input  placeholder="请输入转出备注" value="{remark}"  bindinput='setRemark'/>
		  </view>
		</view>
		<modal id="modal" hidden="{hiddenmodalput}" title="转账确认" confirm-text="提交" cancel-text="取消" bindcancel="cancel" bindconfirm="confirm">
		 <view class="n{flag?'tip':'tip1'}">{{tip}}</view>
		<view class='content'>
		    <block wx:for="{Length}" wx:key="item">
		      <input class='iptbox' value="{Value.length>=index+1?Value[index]:''}" disabled password='{ispassword}' catchtap='Tap'></input>
		    </block>
		  </view>
		  <input name="password" password="true" class='ipt' maxlength="{Length}" focus="{isFocus}" bindinput="Focus"></input>
		</modal>
		<view class='out2'>
		 <button class='changeBtn2' bindtap='withdraw' hover-class='btn_hover'>申请到转出地址</button>
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
  background: #f2f2f2;
}
.enter{
  margin: 30rpx 0 ;

  background: #fff;

  overflow: hidden;
}
.enter-1{
  margin-left: 30rpx;

  padding-top: 30rpx;

  font-size: 32rpx;

  color: #808080;

}
.img{
  
  display:block;

  width: 30rpx;

  height: 30rpx;

  margin-left: 30rpx;

  padding-top: 30rpx;

  margin-top:30rpx;
}
.enter-2{
  display:block;

  float: left;

  margin-left: 75rpx;

  font-size: 32rpx;

  margin-top: -36rpx;


}
.weui-input1{

  ime-mode:disabled;

  font-size: 30rpx; 

  display:block;

  float:left;

  margin-top: -38rpx;

  margin-bottom: 30rpx;

  /* margin-left: 110rpx; */
}
.beizhu{
    display:block;

  float: left;

  margin-left: 30rpx;

  font-size: 32rpx;

  margin-bottom:20rpx;
  margin-top: 20rpx;
}
.shu{
  float: right;
  margin-right:20rpx;
  margin-top:-25rpx;
  width:2rpx;
  height:30rpx;
  background: #47c6c6;
}
.wallet1{
  width:40rpx;
  height:40rpx;
  float: right;
  margin-right:48rpx;
  margin-top:-30rpx;
}
.out{
  margin: 30rpx 0 ;

  background: #fff;

  overflow: hidden;
}
.img0{
  float: left;

  display:block;

  width: 30rpx;

  height: 30rpx;

  margin-left: 30rpx;

  padding-top: 6rpx;

  margin-top:30rpx;

}
.enter-11{
  margin-left: 74rpx;

  padding-top: 30rpx;

  font-size: 32rpx;

  color: #808080;
}
.img1{
  display:block;

  width: 100rpx;

  height: 100rpx;

  margin-left: 30rpx;

  margin-top:20rpx;
}
.weui-input11{
  ime-mode:disabled;

  font-size: 30rpx; 

  display:block;

  float:left;

  margin-top: -74rpx;

  margin-bottom: 30rpx;

  margin-left: 170rpx;
}
.line1{
  width: 100%;

  height: 1rpx;

  background-color: #808080;
}
.bo{
  display:block;

  float: left;

  margin-left: 30rpx;

  font-size: 32rpx;

  color: #808080;

  padding-top: 20rpx;

  margin-bottom: 30rpx;
}
.out2{
  margin: 140rpx 0 ;

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

  /* background:#e51c23; */
  background-color:#30bcd5;
  
  color: #fff;

  margin-bottom: 25rpx;

  flex-direction: column;

  justify-content: center;

  align-items: center;
  
  border-radius: 4rpx;

  /* border-left:1rpx solid #8f8f8f */
}
.tip{
  width: 100%;
  text-align: center;
  height: 50rpx;
  line-height: 50rpx;
}
.tip1{
  width: 100%;
  height: 50rpx;
  text-align: center;
  line-height: 50rpx;
  color: red;
}
.content{
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin-top: 80rpx;
}
.iptbox{
  width: 80rpx;
  height: 80rpx;
  border:1rpx solid #ddd;
  border-radius: 20rpx;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.ipt{
  width: 0;
  height: 0;
}
</style>
