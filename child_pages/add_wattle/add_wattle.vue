<template>
	<view>
		<view class="box">
		  <input class="name" placeholder='请输入转出昵称' bindinput='addnickname' value='{nickname}'></input>
		</view>
		<view class="box">
		  <input class="name" placeholder='请输入钱包地址' bindinput='addaddress' value='{wallet_address}'></input>
		</view>
		<modal id="modal" hidden="{hiddenmodalput}" title="转账确认" confirm-text="提交" cancel-text="取消" bindcancel="cancel" bindconfirm="confirm">
		 <text class='tip'>请输入资金密码</text>
		<view class='content'>
		    <block wx:for="{Length}" wx:key="item">
		      <input class='iptbox' value="{Value.length>=index+1?Value[index]:''}" disabled password='{ispassword}' catchtap='Tap'></input>
		    </block>
		  </view>
		  <input name="password" password="true" class='ipt' maxlength="{Length}" focus="{isFocus}" bindinput="Focus"></input>
		</modal>
		<button class="btn" bindtap='save'>保存并使用</button>
	</view>
</template>
<!-- 新增钱包地址 -->
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
/* miniprogram/pages/add_wattle/add_wattle.wxss */
.box{
  width:100%;
  height:186rpx;
  margin-left:48rpx;
  border-bottom:1px solid #ccc;
  padding-top:130rpx;
  box-sizing: border-box;
}
.name{
  /* margin-left:48rpx; */
  font-size: 30rpx;
}
.btn{
width: 600rpx;
height: 80rpx;
margin-top:100rpx;
border-radius: 5px;
background-color:#30bcd5;
color: rgba(255, 255, 255, 1);
font-size: 32rpx;
text-align: center;
font-family: Microsoft Yahei;

}
.tip{
  width: 100%;
  text-align: center;
  margin-left: 160rpx;
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
