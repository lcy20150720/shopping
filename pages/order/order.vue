<template>
	<view class="page-wrap">
		<view class="bg"></view>
		<view class="order-top">
			<view class="txt-row">
				<text>收货人：</text>
				<text>AMILLY</text>
			</view>
			<view class="txt-row">
				<text>收货点：</text>
				<text>广州市白云区同和榕树西街32号</text>
			</view>
			<view class="txt-row">
				<text class="tips">下单后可联系客服，全程为您服务，保障售后无忧</text>
			</view>
		</view>
		<view class="order-bom">
			<view class="order-time">
				<text>2021-01-21 18:00</text>
				<text class="total-amount">共2件</text>
			</view>
			<view class="list">
				<view class="row" v-for="(item, index) in showList" :key="index">
					<view class="lf-img">
						<image class="goods-img" :src="item.src" :mode="item.mode"></image>
					</view>
					<view class="rg-txt">
						<text class="goods-txt">{{item.text}}</text>
						<view class="bom-txt">
							<text class="price-unit">￥</text>
							<text class="price">{{item.price}}</text>
							<text class="amount">共{{item.amount}}件</text>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="coupons">
			<text class="lf-txt">优惠券</text>
			<text class="rg-txt">-10</text>
		</view>
		<view class="foo-btns">
			<view class="foo-left">待支付<text class="unit">￥</text><text class="total">9.59</text></view>
			<view class="foo-right"><button type="default" class="pay-btn">立即支付</button></view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				showList: [
					{
						mode: 'scaleToFill',
						src: require('../../static/h1.jpg'),
						text:'新鲜江西红橙大优惠新鲜上市包邮到家',
						price:'5.9',
						amount: 1,
					},
					{
						mode: 'scaleToFill',
						src: require('../../static/h2.jpg'),
						text:'浓郁百香果缤纷的世界新鲜发货送开果器',
						price:'2.3',
						amount: 1,
					},
				],
			}
		},
		methods: {
			
		}
	}
</script>

<style>
.page-wrap{
	height: 100vh;
	background-color: #F5F5F5;
	padding-top: 30rpx;
}
.bg{
	width: 100%;
	height: 300rpx;
	border-bottom-left-radius: 60rpx;
	border-bottom-right-radius: 60rpx;
	background: url('~@/static/order_bg.jpg');
	position: absolute;
	top: 0;
	left: 0;
}
.order-top,.order-bom,.coupons{
	width: 690rpx;
	background-color: #fff;
	margin: 0 auto 30rpx auto;
	border-radius: 20rpx;
	position: relative;
	z-index: 50;
	padding: 0 30rpx;
	box-sizing: border-box;
	font-size: 32rpx;
	color: #333;
}
.order-top .txt-row{
	padding: 30rpx 0;
	border-bottom: 2rpx solid #eee;
}
.order-top .txt-row:last-child{
	border:none;
}
.order-top .tips{
	font-size: 28rpx;
	color: #e17857;
}
.order-bom .order-time{
	height: 80rpx;
	line-height: 80rpx;
	font-size: 28rpx;
	color: #333;
	border-bottom: 2rpx solid #eee;
	margin-bottom: 30rpx;
}
.order-bom .order-time .total-amount{
	float: right;
}
.list{
	padding-bottom: 30rpx;
}
.list .row{
	width: 100%;
	height: 180rpx;
	display: flex;
	margin-bottom: 30rpx;
}
.list .row:last-child{
	margin-bottom: 0;
}
.list .row .lf-img{
	width: 35%;
	display: inline-block;
}
.list .lf-img .goods-img{
	width: 100%;
	height: 100%;
	border-radius: 10rpx;
}
.list .row .rg-txt{
	width: 65%;
	display: inline-block;
	padding-left: 20rpx;
	box-sizing: border-box;
}
.list .booking-btn{
	width: 200rpx;
	height: 56rpx;
	line-height: 56rpx;
	display: inline-block;
	float: right;
	background-color: #FF5722;
	border-radius: 30rpx;
	font-size: 28rpx;
	margin: 4rpx 10rpx 0 0;
	font-weight: bold;
}
.list .goods-txt{
	height: 120rpx;
	color: #333;
	font-weight: bold;
	font-size: 32rpx;
	display: block;
}
.list .price-unit{
	font-size: 32rpx;
	color: #FF5722;
}
.list .price{
	font-size: 48rpx;
	font-weight: bold;
	color: #FF5722;
}
.list .amount{
	color: #999;
	font-size: 28rpx;
	float: right;
	padding-top: 12rpx;
}
.coupons .lf-txt,.coupons .rg-txt{
	height: 80rpx;
	line-height: 80rpx;
	font-size: 28rpx;
	display: inline-block;
}
.coupons .lf-txt{
	color: #333;
}
.coupons .rg-txt{
	color: #FF5722;
	float: right;
}
.foo-btns{
	width: 100%;
	height: 100rpx;
	background-color: #fff;
	box-shadow: 0 -2rpx 2rpx 2rpx #eee;
	position: fixed;
	bottom: 0;
	padding: 0 30rpx;
	box-sizing: border-box;
	display: flex;
}
.foo-btns .foo-left,.foo-btns .foo-right{
	width: 50%;
	height: 100%;
	display: inline-block;
}
.foo-btns .foo-left{
	line-height: 100rpx;
	color: #333;
	font-size: 32rpx;
}
.foo-btns .foo-left .unit{
	font-size: 28rpx;
	color:#FF5722;
}
.foo-btns .foo-left .total{
	font-size: 44rpx;
	color: #FF5722;
	font-weight: bold;
}
.foo-btns .foo-right .pay-btn{
	width: 240rpx;
	height: 80rpx;
	line-height: 80rpx;
	background-color: #FF5722;
	color: #fff;
	font-size: 32rpx;
	text-align: center;
	border-radius: 40rpx;
	float: right;
	margin-top: 10rpx;
}
</style>
