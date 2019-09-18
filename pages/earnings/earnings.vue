<template>
	<view>
		<view class="charts">
		  <ff-canvas id="interval" canvas-id="interval" opts="{ opts }"> </ff-canvas>
		</view>
		
		<view class="{scrollTop>182?'topFix':'income'}">
		  <view class="divLine"></view>
		  <view style='height:150rpx;padding-left:48rpx;'>
		    <view class="side">
		      <view class="txt">矿机数量</view>
		      <view class="num">{{machine_num}}</view>
		    </view>
		    <view class="side2">
		      <view class="txt">存储空间</view>
		      <view class="num">{{fs_cap}}
		        <text class='fontStyle' space='true'> T</text>
		      </view>
		    </view>
		  </view>
		  <view class="divLine"></view>
		  <view style='height:150rpx;padding-left:48rpx;'>
		    <view class="side">
		      <view class="txt">本月收益</view>
		      <view class="num">{{month_profit}}
		        <text class='fontStyle' space='true'> FIL</text>
		      </view>
		    </view>
		    <view class="side2">
		      <view class="txt">总计</view>
		      <view class="num">{{orders.user_total_profit}}
		        <text class='fontStyle' space='true'> FIL</text>
		      </view>
		    </view>
		  </view>
		  <view class="divLine"></view>
		  <view class="notes">
		    <text class="top">收益记录</text>
		    <view class="line">
		      <view class='select_box'>
		        <view class='select' catchtap='selectTap'>
		          <text class='select_text'>{{selectData[index]}}</text>
		          <image class='select_img{selectShow&&select_img_rotate}' src='../../static/images/select.png' background-size="contain"></image>
		        </view>
		        <view class='option_box' style='height:{selectShow?(selectData.length>5?325:selectData.length*50):0}rpx;'>
		          <text class='option' wx:for='{selectData}' wx:key='this' data-index='{index}' catchtap='optionTap'>{{item}}</text>
		        </view>
		      </view>
		      <view class="all">收益：{{month_profit}}
		        <text class='fontStyle' space='true'>FIL</text>
		      </view>
		    </view>
		  </view>
		</view>
		
		<scroll-view scroll-y='true' class="notes">
		  <view class="none">
		    <view class="list" wx:for="{orders.user_profit_data}" wx:key="id">
		      <image class="pic" src="../../static/images/income.png"></image>
		      <view class="desc">
		        <view class="info">收款</view>
		        <view class="info">{{item.trans_time}}</view>
		      </view>
		      <view class="add">+{{item.num}}FIL</view>
		    </view>
		  </view>
		</scroll-view>
	</view>
</template>
<!-- //全部收益 -->
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
page {
  background: #f2f2f2;
}

.charts {
  width: 100%;
  height: 400rpx;
  background: #fff;
}

.income {
  width: 100%;
  height: 465rpx;
  background: #fff;
  
}
.divLine{
 background: #E0E3DA;
 width: 100%;
 height: 5rpx;
}
.topFix{
  position: fixed;
  height: 465rpx;
  background: #fff;
  top: 0rpx;
  width: 100%;
  z-index: 1;
}

.side {
  width: 45%;
  float: left;
}
.side2 {
  width: 55%;
  float: left;
}

.txt {
  margin-top: 8rpx;
  height: 60rpx;
  /* text-align: center; */
  line-height: 60rpx;
  color: #313131;
  font-size: 26rpx;
  /* font-family: Microsoft YaHei */
  /* margin-left: 48rpx */
}
.fontStyle{
  font-size: 25rpx;
}
.num {
  margin-top: 8rpx;
  height: 60rpx;
  /* text-align: center; */
  line-height: 60rpx;
  color: #333;
  font-size: 38rpx;
  /* margin-left: 48rpx */
}

.notes {
  /* overflow: hidden; */
  width: 100%;
  /* height:400rpx; */
  background: #fff;
  padding-left: 48rpx;
  padding-right: 48rpx;
  padding-bottom:50rpx;
  box-sizing: border-box;
}

.top {
  font-size: 32rpx;
  color: #333;
  line-height: 100rpx;
}

.line {
  width: 100%;
  height: 50rpx;
}
.select_box{
  width:30%;
  height:100%;
  border-radius: 14rpx;
  border: 1px solid #f2f2f2;
  position: relative;
  float: left;
}
.select_box .select{
  box-sizing: border-box;
  width: 100%;
  height: 100%;
  border-radius: 8rpx;
  display: flex;
  align-items: center;
  padding: 0 10rpx;
   z-index:99;
}
.select_box .select .select_text{
  font-size: 26rpx;
  color: #777777;
  line-height: 28rpx;
  flex: 1;
}
.select_box .select .select_img{
  width: 30rpx;
  height: 30rpx;
  display: block;
  transition:transform 0.3s;
}
.select_box .select .select_img_rotate{
  transform:rotate(180deg); 
}
.select_box .option_box{
  position: absolute;
  top: calc(100% - 1px);
  width: 100%;
  background: #fff;
  box-sizing: border-box;
  height: 0;
  overflow-y: auto;
  background: #fff;
  z-index: 9;
  transition: height 0.3s;
  border-left:1px solid #efefef;
  border-right:1px solid #efefef;
}
.select_box .option_box .option{
  display: block;
  line-height: 30rpx; 
  font-size: 26rpx;
  border-top: 1px solid #efefef;
  border-bottom: 1px solid #efefef;
  padding: 10rpx;
 
}

.all {
  float: right;
  font-size: 30rpx;
}

.none {
  width: 100%;
  height: 350rpx;
  text-align: center;
  line-height: 300rpx;
  font-size: 50rpx;
  color: #ccc;
  
}

.list {
  width: 100%;
  height: 80rpx;
  margin-top: 40rpx;
}

.pic {
  width: 60rpx;
  height: 60rpx;
  float: left;
  margin-top: 10rpx;
}

.desc {
  float: left;
  width: 300rpx;
  height: 100%;
  padding-left: 20rpx;
}

.info {
  height: 40rpx;
  line-height: 40rpx;
  font-size: 26rpx;
  color: #000;
  text-align: left;
}

.add {
  float: right;
  line-height: 80rpx;
  color: #13C1DB;
  font-size: 32rpx;
}
</style>
