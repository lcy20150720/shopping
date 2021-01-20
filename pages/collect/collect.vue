<template>
	<view class="page-wrap">
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
				showList: [
					{
						mode: 'scaleToFill',
						src: require('../../static/h1.jpg'),
						text:'新鲜江西红橙大优惠新鲜上市包邮大家',
						price:'5.9',
					},
					{
						mode: 'scaleToFill',
						src: require('../../static/h2.jpg'),
						text:'浓郁百香果缤纷的世界新鲜发货送开果器',
						price:'2.3',
					},
					{
						mode: 'scaleToFill',
						src: require('../../static/h3.jpg'),
						text:'红苹果包邮到家健康你我他每天一苹果',
						price:'4.5',
					}
				],
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.page-wrap{
		width: 100%;
		height:100vh;
		background-color: #F5F5F5;
	}
	.list{
		padding-left: 30rpx;
		padding-right: 30rpx;
		box-sizing: border-box;
		padding-top: 40rpx;
	}
	.list .row{
		width: 100%;
		height: 200rpx;
		display: flex;
		margin-bottom: 30rpx;
		background-color: #FFFFFF;
		padding: 10rpx;
		box-sizing: border-box;
		border-radius: 10rpx;
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
	.list .bom-txt{
		text-align: right;
	}
</style>
