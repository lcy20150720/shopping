<template>
	<view>
		<view class="types-all">
			<view class="type-btns">
				<text class="type-lf-txt top-title">分类</text>
				<view class="type-wp">
					<text 
					v-for="(item, index) in tabs" 
					:class="{'type-lf-txt': true, 'cur' : active===index}" 
					:key="index"
					@click="tabChange(index)">{{tabs[index]}}</text>
				</view>
			</view>
			<view class="type-panel">
				<view class="panel">
					<view class="box" v-for="(item, index) in showList" :key="index">
						<image class="goods-img" :src="item.src" :mode="item.mode"></image>
						<text class="goods-txt">{{item.text}}</text>
						<view class="price-wp"><text class="goods-price-txt">￥</text><text class="goods-price">{{item.price}}</text></view>
						<button type="primary" class="booking-btn">购买</button>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
    data() {
        return {
			tabs:['蔬菜','水果','肉禽','海鲜','粮油','零食','酒饮'],
			showList: [
				{
					mode: 'scaleToFill',
					src: require('../../static/g1.jpg'),
					text:'新鲜柠檬大优惠新鲜上市包邮到家',
					price:'5.9',
				},
				{
					mode: 'scaleToFill',
					src: require('../../static/g2.jpg'),
					text:'红彤彤西红柿缤纷的世界新鲜发货',
					price:'2.3',
				},
				{
					mode: 'scaleToFill',
					src: require('../../static/g3.jpg'),
					text:'香郁草莓包邮到家香飘四溢健康你我他',
					price:'4.5',
				},
				{
					mode: 'scaleToFill',
					src: require('../../static/g3.jpg'),
					text:'香郁草莓包邮到家香飘四溢健康你我他',
					price:'4.5',
				}
			],
			active: 0,
        };
    },
    methods: {
       tabChange: function(index){
		   this.active = index;
	   }
    },
};
</script>

<style>
.types-all{
	width: 100%;
	height: 100%;
	position: fixed;
}
.type-btns{
	width: 200rpx;
	height: 100%;
	position: absolute;
	left: 0;
	top: 0;
	bottom: 0;
	background-color: #fff;
	border-right: 1px solid #eee;
	z-index: 999;
}
.type-panel{
	width: 100%;
	height: 100%;
	padding-left: 220rpx;
	padding-top: 20rpx;
	padding-right: 20rpx;
	box-sizing: border-box;
	position: fixed;
	bottom: 0;
	top: 88rpx;
	background-color: #F5F5F5;
}
.type-lf-txt{
	width: 100%;
	height: 80rpx;
	line-height: 80rpx;
	text-align: center;
	font-size: 30rpx;
	color: #333;
	display:block;	
	border-bottom: 2rpx solid #eee;
}
.cur{
	color: #FF5722;
}
.top-title{
	font-weight: bold;
	font-size: 32rpx;
}
.box{
	width: 48%;
	background: #fff;
	margin-right: 4%;
	box-shadow: 0 2rpx 2rpx 2rpx #eee;
	padding-bottom: 10rpx;
	margin-bottom: 20rpx;
	display: inline-block;
}
.box:nth-child(2n){
	margin-right: 0;
}
.box .goods-img{
	width: 100%;
	height: 160rpx;
}
.box .goods-txt{
	width: 100%;
	color: #333;
	font-size: 28rpx;
	font-weight: bold;
	height: 68rpx;
	display: block;
	line-height: 1.2;
	overflow: hidden;
	padding-left: 10rpx;
	padding-right: 10rpx;
	box-sizing: border-box;
}
.box .booking-btn{
	width: 200rpx;
	height: 44rpx;
	line-height: 44rpx;
	background-color: #FF5722;
	color: #fff;
	font-size: 28rpx;
	font-weight: bold;
	border-radius: 22rpx;
}
.box .goods-price{
	font-size: 36rpx;
	color: #FF5722;
	font-weight: bold;
}
.box .goods-price-txt{
	font-size: 28rpx;
	color:#FF5722;
}
.box .price-wp{
	text-align: center;
	margin-bottom: 10rpx;
}
</style>
