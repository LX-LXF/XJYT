
<template>
	<view>
		<view class="obg">
		    <image src="../../static/images/logo2.jpg" class="logo-a"></image>
		    <view class="circle">
		        <image src="../../static/images/ipfs.png" class="ipfs"></image>
		        <image src="../../static/images/FIL.png" class="fil"></image>
		    </view>
		    <view class="box">星际云通 Filecoin</view>
		    <view class="load"><loading :hidden="hidden">加载中...</loading></view>
		</view>
	</view>
</template>
<!-- //登录页 -->
<script>
	export default {
		data() {
			return {
                hidden: false
            }
		},
        onPullDownRefresh: function () {
            wx.showNavigationBarLoading(); //在标题栏中显示加载
        
            setTimeout(function () {
              // complete
              wx.hideNavigationBarLoading(); //完成停止加载
        
              wx.stopPullDownRefresh(); //停止下拉刷新
            }, 1500);
          },
	}
</script>

<style>
.header {
    margin-top: 140rpx;

    margin-left: 279rpx;

    margin-bottom: 212rpx;

    margin-right: 279rpx;

    border-bottom: 1px solid #ccc;

    text-align: center;

    height: 200rpx;

    line-height: 450rpx;
}

.header image {
    width: 200rpx;

    height: 200rpx;
}

.content {
    margin-left: 50rpx;

    margin-bottom: 90rpx;
}

.content text {
    display: block;

    color: #9d9d9d;

    margin-top: 40rpx;
}

.bottom {
    border-radius: 80rpx;

    margin: 70rpx 50rpx;

    font-size: 35rpx;
}
.obg {
    background: #fff;

    height: 100%;
}
.logo-a {
    width: 500rpx;

    height: 500rpx;

    margin-left: 128rpx;
}
.circle {
    width: 200rpx;
    height: 74rpx;
    border: 2rpx solid #d9f2f7;
    border-radius: 30rpx;
    margin: 0rpx auto;
    position: relative;
}
.ipfs {
    width: 50rpx;
    height: 50rpx;
    position: absolute;
    top: 12rpx;
    left: 10rpx;
}
.fil {
    width: 50rpx;
    height: 50rpx;
    position: absolute;
    top: 15rpx;
    right: 10rpx;
}

.box {
    text-align: center;

    font-size: 58rpx;

    color: #01c0dd;

    font-weight: bold;

    margin-top: 500rpx;
}
</style>
