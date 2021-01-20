<template>
	<view class="page-wrap">
		<view class="cart-list">
			<view class="cart-item" v-for="(item, index) in showList" :key="index">
				 <label class="radio"><radio value="r1" :color="color" /></label>
				 <image class="goods-img" :src="item.src" :mode="item.mode"></image>
				 <view class="txt-wrap">
					 <text class="item-title">{{item.text}}</text>
					 <view class="bom-txt">
						 <text class="unit">￥</text>
						 <text class="price">{{item.price}}</text>
						 <view class="count-box">
							 <view class="add-btn">+</view>
							 <input class="uni-input" placeholder="" value="0"/>
							 <view class="del-btn">-</view>
						 </view>
					 </view>
				 </view>
			</view>
		</view>
		<view class="cart-total">
			<view class="total-left">
			   <label class="radio"><radio value="r1" :color="color" class="ra"/><text class="radio-txt">全选</text></label>
			   <view class="total">
				  <view class="total-top">
					  合计：<text class="unit">￥</text><text class="total-num">999</text>
				  </view> 
				  <view class="total-bom">
					  共节省：<text>￥9.00</text>
				  </view>
			   </view>
			</view>
			<view class="total-right">
				 <navigator url="../../pages/collect/collect" open-type="redirect" hover-class="other-navigator-hover">
                    <button type="default" class="pay-btn">去下单</button>
                </navigator>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				color: '#FF5722',
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
					
				],
			}
		},
		methods: {
			
		}
	}
</script>

<style>
.page-wrap{
	background-color: #f5f5f5;
	height: calc( 100vh - 188rpx );
}
.cart-list{
	padding-top: 30rpx;
	padding-left: 30rpx;
	padding-right: 30rpx;
	box-sizing: border-box;
}
.cart-list .cart-item{
	width: 100%;
	height: 200rpx;
	background-color: #fff;
	margin-bottom: 30rpx;
	border-radius: 20rpx;
	padding: 20rpx;
	box-sizing: border-box;
	position: relative;
}
.cart-list .cart-item .goods-img{
	width: 160rpx;
	height: 160rpx;
	display: inline-block;
	margin-left: 60rpx;
}
.cart-list .cart-item .radio{
	position:absolute;
	z-index: 99;
	top: 50%;
	margin-top: -24rpx;
}
.cart-list .cart-item .txt-wrap{
	display: inline-block;
	width: 430rpx;
	padding-left: 20rpx;
	box-sizing: border-box;
}
.cart-list .cart-item .item-title{
	font-size: 32rpx;
	color: #333;
	font-weight: bold;
	height: 100rpx;
	overflow: hidden;
	display: block;
}
.cart-list .cart-item .goods-img,
.cart-list .cart-item .item-title{
	vertical-align: top;
}
.cart-list .cart-item .unit{
	font-size: 28rpx;
	color: #FF5722;
}
.cart-list .cart-item .price{
	font-size: 44rpx;
	color: #FF5722;
	font-weight: bold;
}
.cart-list .cart-item .count-box{
	width: 200rpx;
	height: 60rpx;
	display: inline-block;
	float: right;
	border: 1px solid #ddd;
	border-radius: 2px;
}
.cart-list .cart-item .count-box .add-btn,
.cart-list .cart-item .count-box .del-btn{
	width: 60rpx;
	height: 60rpx;
	line-height: 60rpx;
	text-align: center;
	color: #333;
	font-size: 40rpx;
	background-color: #EEEEEE;
}
.cart-list .cart-item .count-box .uni-input{
	width: 80rpx;
	height: 60rpx;
	text-align: center;
}
.cart-list .cart-item .count-box .add-btn,
.cart-list .cart-item .count-box .del-btn,
.cart-list .cart-item .count-box .uni-input{
	display: inline-block;
	vertical-align: top;
}
.cart-total{
	position: absolute;
	width: 750rpx;
	height: 140rpx;
	background-color: #FFFFFF;
	box-shadow: 0 -2rpx 2rpx 2rpx #eee;
	bottom: 0;
	left: 0;
	right: 0;
	z-index: 999;
	padding: 20rpx;
	box-sizing: border-box;
	display: flex;
}
.cart-total .radio{
	position: absolute;
	top: 50%;
	margin-top: -24rpx;
	font-size: 32rpx;
}
.cart-total .ra,.cart-total .radio-txt{
	vertical-align: top;
}
.cart-total .radio-txt{
	padding-top: 4rpx;
	display: inline-block;
}
.cart-total .total-left{
	width: 70%;
	height: 100%;
}
.cart-total .total{
	float: right;
}
.cart-total .total-top{
	color: #333;
	font-size: 32rpx;
	font-weight: bold;
}
.cart-total .total-bom{
	color: #FF5722;
	font-size: 28rpx;
}
.cart-total .total .unit,
.cart-total .total .total-num{
	color: #FF5722;
}
.cart-total .total .total-num{
	font-size: 44rpx;
}
.cart-total .total-right{
	width: 30%;
	height: 100%;
	padding: 5px 0 0 30rpx;
	box-sizing: border-box;
}
.cart-total .total-left,
.cart-total .total-right{
	display: inline-block;
}
.cart-total .pay-btn{
	width: 100%;
	height: 80rpx;
	line-height: 80rpx;
	text-align: center;
	color: #fff;
	background-color: #FF5722;
	font-size: 32rpx;
	border-radius: 40rpx;
}
</style>
