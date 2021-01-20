<template>
	<view class="content">
		<uni-swiper-dot :info="info" :current="current" field="content" :mode="mode" :dotsStyles="dotsStyles">
			<swiper class="swiper-box" :autoplay="autoplay" :interval="interval" :duration="duration">
				<swiper-item v-for="(item ,index) in info" :key="index">
					<view class="swiper-item">
						 <image style="width: 100%;height: 300rpx;" :mode="item.mode" :src="item.src"></image>
					</view>
				</swiper-item>
			</swiper>
		</uni-swiper-dot>
		<view class="btn-area">
			<view class="col">
				<image class="icon" src="../../static/a1.png" mode=""></image>
				<text class="bm-txt">推荐有奖</text>
			</view>
			<view class="col">
				<image class="icon" src="../../static/a2.png" mode=""></image>
				<text class="bm-txt">新鲜蔬菜</text>
			</view>
			<view class="col">
				<image class="icon" src="../../static/a3.png" mode=""></image>
				<text class="bm-txt">时令水果</text>
			</view>
			<view class="col">
				<image class="icon" src="../../static/a4.png" mode=""></image>
				<text class="bm-txt">肉禽蛋品</text>
			</view>
			<view class="col">
				<image class="icon" src="../../static/a5.png" mode=""></image>
				<text class="bm-txt">海鲜水产</text>
			</view>
			<view class="col">
				<image class="icon" src="../../static/a6.png" mode=""></image>
				<text class="bm-txt">粮油调味</text>
			</view>
			<view class="col">
				<image class="icon" src="../../static/a7.png" mode=""></image>
				<text class="bm-txt">休闲零食</text>
			</view>
			<view class="col">
				<image class="icon" src="../../static/a8.png" mode=""></image>
				<text class="bm-txt">酒饮冲调</text>
			</view>
        </view>
		
		<view class="hot">
			<text class="hot-tp-txt">限时秒杀</text>
			<view class="items-wrap">
				<view class="item" v-for="(item, index) in hotList" :key="index">
					<image class="goods-img" :src="item.src" :mode="item.mode"></image>
					<text class="price">￥{{item.price}}</text>
					<button type="primary" class="booking-btn">加入购物车</button>
				</view>
			</view>
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
						<button type="primary" class="booking-btn">立即抢购</button>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
import uniSwiperDot from "@/components/uni-swiper-dot/uni-swiper-dot.vue"
export default {
    data() {
        return {
			autoplay: true,
			interval: 5000,
			duration: 500,
            info: [{
                mode: 'scaleToFill',
				src: require('../../static/banner_01.jpg'),
            }, {
                mode: 'scaleToFill',
                src:  require('../../static/banner_02.jpg'),
            }, {
                mode: 'scaleToFill',
                src:  require('../../static/banner_03.jpg'),
            }],
            current: 0,
            mode: 'round',
			dotsStyles: {
				backgroundColor: 'rgba(255,255,255,.5)',
				selectedBackgroundColor: '#fff',
				border: '1px solid rgba(255,255,255,.5)',
				selectedBorder: '1px solid rgba(255,255,255,1)',
			},
			hotList: [
				{
					mode: 'scaleToFill',
					src: require('../../static/g1.jpg'),
					price:'5.9',
				},
				{
					mode: 'scaleToFill',
					src: require('../../static/g2.jpg'),
					price:'2.3',
				},
				{
					mode: 'scaleToFill',
					src: require('../../static/g3.jpg'),
					price:'4.5',
				}
			],
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
	components: {uniSwiperDot},
    methods: {
        change(e) {
            this.current = e.detail.current;
        },
    },
	 onLoad: function (option) { //option为object类型，会序列化上个页面传递的参数
		console.log(option.id); //打印出上个页面传递的参数。
		console.log(option.name); //打印出上个页面传递的参数。
	}
}

</script>

<style>
	.btn-area{
		margin-top: 40rpx;
	}
	.btn-area .col{
		width: 25%;
		display: inline-block;
		padding-bottom: 20rpx;
	}
	.btn-area .icon{
		width: 80rpx;
		height: 80rpx;
		display: block;
		margin: 0 auto;
	}
	.btn-area .bm-txt{
		color: #333;
		font-size: 32rpx;
		display: block;
		margin: 10rpx auto 0 auto; 
		text-align: center;
	}
	.hot{
		width: 700rpx;
		height: 340rpx;
		background: url('~@/static/hot.jpg');
		border-radius: 20rpx;
		margin: 20rpx auto 0 auto;
		padding: 20rpx;
		box-sizing: border-box;
		position: relative;
	}
	.hot-tp-txt{
		color: #fff;
		font-weight: bold;
		font-size: 36rpx;
		padding-bottom: 10rpx;
		box-sizing: border-box;
		display: block;
	}
	.item{
		width: 210rpx;
		height: 230rpx;
		background-color: #fff;
		display: inline-block;
		margin-right: 15rpx;
		box-sizing: border-box;
		border-radius: 10rpx;
		overflow: hidden;
	}
	.item:nth-child(3){
		margin-right: 0;
	}
	.item .goods-img{
		width: 100%;
		height: 120rpx;
	}
	.item .price{
		color: #FF5722;
		font-weight: bold;
		font-size: 32rpx;
		margin: -6rpx auto 6rpx auto;
		text-align: center;
		display: block;
	}
	.item .booking-btn{
		width: 80%;
		height: 44rpx;
		line-height: 44rpx;
		font-size: 24rpx;
		background-color: #4caf50;
		display: block;
		margin: 0 auto;
		border-radius: 22rpx;
		padding-left: 0;
		padding-right: 0;
	}
	.list{
		padding-left: 30rpx;
		padding-right: 30rpx;
		box-sizing: border-box;
		margin-top: 40rpx;
	}
	.list .row{
		width: 100%;
		height: 180rpx;
		display: flex;
		margin-bottom: 30rpx;
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
</style>
