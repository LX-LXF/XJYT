<template>
    <view>
        <view class="top">
            <view class="card">
                <view class="first">
                    <text class="num">{{fil_count}}</text>
                    <text class="fil">FIL个数</text>
                </view>
                <view class="second">
                    <text class="price">FIL实价</text>
                    <view class="change">
                        <image src="../../static/images/rmb.png" class="changeOne" alt="rmb"></image>
                        <text class="price2" @top='save1'>236.4</text>
                    </view>
                </view>
                <view class="second">
                    <text class="high">24H涨跌</text>
                    <text class="persent">+1.24%</text>
                </view>
                <view class="second">
                    <text class="yue">我的余额</text>
                    <image src="../../static/images/jiantou3.png" class="more" @top="balance"></image>
                    <image src="../../static/images/money.png" class="mon"></image>
                </view>
                <view class="userinfo-avatar" @top="jmp3">
                    <open-data type="suerAvatarUrl"></open-data>
                </view>
            </view>
        </view>
        <view class="line2">
            <view class="bg">
                <view class="card2">
                    <image src="../../static/images/zu10.png" class="kuang"></image>
                    <view class="manage">矿机管理</view>
                    <view class="list">
                        
                        <view class="listItem" @tap="save1">
                            <image src="../../static/images/shop.png" class="shop"></image>
                            <view class="sale">购买</view>
                        </view>
                        
                        <view class="listItem" @tap="save1">
                            <image src="../../static/images/sale.png" class="shop"></image>
                            <view class="sale">出售</view>
                        </view>
                        
                        <view class="listItem" @tap="save1">
                            <image src="../../static/images/market.png" class="shop"></image>
                            <view class="sale">市场</view>
                        </view>
                        
                        <view class="listItem" @tap="save1">
                            <image src="../../static/images/tip.png" class="shop"></image>
                            <view class="sale">记录</view>
                        </view>
                        
                    </view>
                </view>
            </view>
            <view class="bg2">
                <view class="allList">
                    
                    <view class="everyList" @top="jump">
                        <text class="text1">我的矿机</text>
                        <image class="go" src="../../static/images/jiantou3.png" ></image>
                        <text class="text2">438</text>
                    </view>
                    
                    <view class="everyList" @top="sevenIncome">
                        <text class="text1">7日收益</text>
                        <image class="go" src="../../static/images/jiantou3.png" ></image>
                        <text class="text2">438</text>
                    </view>
                    
                    <view class="everyList" @top="totalIncome">
                        <text class="text1">全部收益</text>
                        <image class="go" src="../../static/images/jiantou3.png" ></image>
                        <text class="text2">438</text>
                    </view>
                    
                    <view class="everyList" @top="jump2">
                        <text class="text1">矿机交易</text>
                        <image class="go" src="../../static/images/jiantou3.png" ></image>
                        <text class="text2">438</text>
                    </view>
                    
                    <view class="everyList" style="border-bottom: none" @top="save1">
                        <text class="text1">我的矿机</text>
                        <image class="go" src="../../static/images/jiantou3.png" ></image>
                        <text class="text2">438</text>
                    </view>
                    
                </view>
            </view>
            <view class="bg3">
                <view class="meterail">
                    <view class="everyList" style="border-bottom: none">
                        <image src="../../static/images/mete.png" calss="go1"></image>
                        <text class="text1">技术资料</text>
                        <image src="../../static/images/jiantou3.png" calss="go2"></image>
                        <text class="text3">更多</text>
                    </view>
                    <image src="../../static/images/ooo4.png" class="ooo1" @top="jump5"></image>
                    <image src="../../static/images/ooo3.png" class="ooo2" @top="jump6"></image>
                </view>
            </view>
            <view class="bg4">
                <view class="active">
                    <view class="everyList" style="border-bottom: none">
                        <image src="../../static/images/news.png" calss="go1"></image>
                        <text class="text1">新闻活动</text>
                        <image src="../../static/images/jiantou3.png" class="go2"></image>
                        <text class="text3">更多</text>
                    </view>
                    <swiper class="activeImg" indicator-dots="true" autoplay="true" interval="500" circular="true">
                      <block v-for="(item, id) in bnrUrl" :key="id">
                        <swiper-item>
                          <image :src="item.url" class="u-img-slide" mode="aspectFill"></image>
                        </swiper-item>
                      </block>
                    </swiper>
                    <view class="title1">管控体验升级调用</view>
                    <view class="title2">填写问卷调查, 赢取阿里云定制文化衫, 您的意见对我们至关重要。</view>
                </view>
            </view>
        </view>
    </view>
</template>

<script>
    export default {
      data() {
        return {
          "bnrUrl": [{
          }, {
            "url": "../../static/images/33.png"
          }, {
            "url": "../../static/images/44.png"
          }]
        };
      },
      onLoad:function (options) {
          var open_id = getApp().globalData;
          var token = getApp().globalData;
          var website = getApp().globalData;
          uni.request({
              method:'GET',
              url:"domain + 'service/home/' + open_id",
              data:{
                  open_id: getApp().globalData,
              },
              header:{
                  "Content-Type":"application/x-www-form-urlencoded",
                  "token":token,
                  "open-id":open_id
              },
              success:function (res) {
                  this.fil_count = res.data.data[0].fil_count,
                  this.machine_count = res.data.data[0].count,
                  this.lock_num = res.data.data[0].lock_num
              }
          })
      }
     }
</script>

<style>
    page{
      height: 100%;
      width: 100%;
    }
    .top{
      width:100%;
      height:440rpx;
      background: #01c0dd;
      position: relative;
    }
    .line2{
      width:100%;
      height:250rpx;
      background: #f2f2f2;
      position: absolute;
      border-bottom: 60rpx;
  
    }
    .card{
      width:700rpx;
      height:400rpx;
      background: #fff;
      border-radius: 20rpx;
      position:absolute;
      top:20rpx;
      left:calc((100% - 700rpx)/2);

    }
    .userinfo-avatar {
      overflow:hidden;
      display: block;
      position:absolute;
      top:20rpx;
      right:20rpx;
      width:120rpx;
      height:120rpx;
      border-radius: 50%;
      box-shadow: 3rpx 3rpx 10rpx rgba(0, 0, 0, 0.2);
      z-index: 2;
    }
    
    .first{
      height:140rpx;
      margin-bottom:20rpx;
    
    }
    .num{
      line-height: 190rpx;
      font-size:45rpx;
      color:#01c0dd;
      margin-right:30rpx;
      margin-left:30rpx;
    }
    .fil{
       line-height: 190rpx;
       font-size: 30rpx;
       color:#ccc;
    }
    .second{
      height:60rpx;
      margin-bottom: 20rpx;
    }
    .price{
       font-size:30rpx;
       margin-left:30rpx;
       line-height: 60rpx;
       margin-right:30rpx;
       color:#b0b0b0;
       float: left;
    }
    .change{
      float: left;
      width:200rpx;
      height:60rpx;
      border-radius: 80rpx;
      box-shadow: 0 1rpx 4rpx -1rpx rgba(210, 210, 210, 1);
      padding-left:10rpx;
      border: 2rpx solid rgba(244,244,244,1);
      position: relative;
    }
    .changeOne{
      position: absolute;
      top:0;
      right:0;
      width:62rpx;
      height:62rpx;
    }
    .price2{
      width:300rpx;
      height:60rpx;
      color:cyan;
      line-height: 60rpx;
      font-size: 30rpx;
    
    }
    .high{
      margin-left:30rpx;
      font-size:30rpx;
      margin-right:30rpx;
      line-height: 60rpx;
      color:#b0b0b0;
    }
    .persent{
      font-size: 30rpx;
      line-height: 60rpx;
      color:red;
    }
    .yue{
      line-height: 60rpx;
      font-size: 30rpx;
      margin-left:30rpx;
      float:left;
      color:#202020;
    }
    .more{
      width:20rpx;
      height:30rpx;
      float:right;
      margin-right:30rpx;
      margin-top:20rpx;
    }
    .mon{
      width:35rpx;
      height:30rpx;
      float:right;
      margin-right:10rpx;
      margin-top:20rpx;
    }
    .bg{
      width:100%;
      height:330rpx;
      background: #f2f2f2;
    }
    .card2{
      width:700rpx;
      height:300rpx;
      background: #fff;
      margin:0 auto;
      border-radius: 20rpx;
      padding:20rpx 40rpx;
      box-sizing:border-box;
      box-shadow: 0 10rpx 6rpx  -3rpx rgba(255,255,255,1);
    }
    .kuang{
      width:40rpx;
      height:40rpx;
      float: left;
    }
    .manage{
      float: left;
      font-size: 30rpx;
      margin-left:10rpx;
    
    }
    .list{
      width:620rpx;
      height:200rpx;
      margin-top:50rpx;
      display: flex;
      justify-content: space-between;
    }
    .listItem{
      width:60rpx;
      height:100%;
    }
    .shop{
      width:60rpx;
      height:60rpx;
      margin-top:50rpx;
    }
    .sale{
      width:100%;
      height:60rpx;
      line-height: 60rpx;
      text-align: center;
      font-size: 30rpx;
      color:#ccc;
    }
    .bg2{
      width:100%;
      height:560rpx;
      background: #f2f2f2;
    }
    .allList{
      width:700rpx;
      height:530rpx;
      background:#fff;
      margin:0 auto;
      border-radius: 20rpx;
      padding-left:30rpx;
      padding-top:20rpx;
      box-sizing: border-box;
      box-shadow: 0rpx 10rpx 6rpx  -3rpx rgba(255,255,255,1);
    }
    .everyList{
      width:100%;
      height:100rpx;
      border-bottom: 1rpx solid #ccc;
    }
    .text1{
      line-height: 100rpx;
      font-size: 30rpx;
    }
    .go{
      width:20rpx;
      height:25rpx;
      float: right;
      margin-right:20rpx;
      margin-top:40rpx;
    }
    .text2{
      float: right;
      margin-right:10rpx;
      line-height: 100rpx;
      color:#ccc;
      font-size: 30rpx;
    }
    .bg3{
      width:100%;
      height:350rpx;
      background: #f2f2f2;
    }
    .meterail{
      width:700rpx;
      height:320rpx;
      background: #fff;
      margin:0rpx auto;
      border-radius: 20rpx;
      padding:0rpx 20rpx;
      box-sizing: border-box;
      box-shadow: 0rpx 10rpx 6rpx  -3rpx rgba(255,255,255,1);
    }
    .go1{
      float: left;
      width:20rpx;
      height:25rpx;
      margin-top:37rpx;
      margin-right:10rpx;
    }
    .text3{
      float: right;
      margin-right:10rpx;
      line-height: 100rpx;
      color:#ccc;
      font-size: 30rpx;
    }
    .go2{
      float: right;
      width:20rpx;
      height:25rpx;
      margin-right:10rpx;
      margin-top:40rpx;
    }
    .ooo1{
      float: left;
      width: 300rpx;
      height: 185rpx;
      margin-right:20rpx;
      margin-bottom: 30rpx;
    
    }
    .ooo2{
       float: right;
      width: 300rpx;
      height: 185rpx;
      margin-bottom: 30rpx;
    }
    .bg4{
      width:100%;
      height:750rpx;
      background: #f2f2f2;
    }
    .active{
      width:700rpx;
      height:680rpx;
      background: #fff;
      margin:0rpx auto;
      border-radius: 20rpx;
      padding:0rpx 20rpx;
      box-sizing: border-box;
      box-shadow: 0rpx 10rpx 6rpx  -3rpx rgba(255,255,255,1);
    }
    .activeImg{
      width:640rpx;
      height:325rpx;
      margin:0rpx auto;
    }
    
    .u-img-slide {
      width: 100%;
      height:100%;
    }
    .title1{
      font-size: 30rpx;
      color:#000;
      line-height: 90rpx;
    }
    .title2{
       font-size:26rpx;
       color:#101010;
       line-height:40rpx;
    }
    image {
    width: 36rpx;
    height: 26rpx;
    display: inline-block;
    overflow: hidden;
    
    }

</style>
