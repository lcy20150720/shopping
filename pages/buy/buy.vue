<template>
	<view>
		<uni-fab 
            :pattern="pattern"
            :content="content"
            :horizontal="horizontal"
            :vertical="vertical"
            :direction="direction"
            @trigger="trigger"
        ></uni-fab>
		<view class="types-all">
			<view class="type-btns">
				<text class="type-lf-txt top-title">分类</text>
				<view class="type-wp">
					<text class="type-lf-txt">蔬菜</text>
					<text class="type-lf-txt">水果</text>
					<text class="type-lf-txt">肉禽</text>
					<text class="type-lf-txt">海鲜</text>
					<text class="type-lf-txt">粮油</text>
					<text class="type-lf-txt">零食</text>
					<text class="type-lf-txt">酒饮</text>
				</view>
			</view>
			<view class="type-panel">
				<view class="panel">
					<view class="box">
						<image class="goods-img" src="https://vkceyugu.cdn.bspapp.com/VKCEYUGU-uni-app-doc/6acec660-4f31-11eb-a16f-5b3e54966275.jpg" mode=""></image>
						<text class="goods-txt">测试标题测试标题测试标题测试标题</text>
						<view class="price-wp"><text class="goods-price-txt">￥</text><text class="goods-price">999</text></view>
						<button type="primary" class="booking-btn">购买</button>
					</view>
					<view class="box">
						<image class="goods-img" src="https://vkceyugu.cdn.bspapp.com/VKCEYUGU-uni-app-doc/6acec660-4f31-11eb-a16f-5b3e54966275.jpg" mode=""></image>
						<text class="goods-txt">测试标题测试标题测试标题测试标题</text>
						<view class="price-wp"><text class="goods-price-txt">￥</text><text class="goods-price">999</text></view>
						<button type="primary" class="booking-btn">购买</button>
					</view>
					<view class="box">
						<image class="goods-img" src="https://vkceyugu.cdn.bspapp.com/VKCEYUGU-uni-app-doc/6acec660-4f31-11eb-a16f-5b3e54966275.jpg" mode=""></image>
						<text class="goods-txt">测试标题测试标题测试标题测试标题</text>
						<view class="price-wp"><text class="goods-price-txt">￥</text><text class="goods-price">999</text></view>
						<button type="primary" class="booking-btn">购买</button>
					</view>
					<view class="box">
						<image class="goods-img" src="https://vkceyugu.cdn.bspapp.com/VKCEYUGU-uni-app-doc/6acec660-4f31-11eb-a16f-5b3e54966275.jpg" mode=""></image>
						<text class="goods-txt">测试标题测试标题测试标题测试标题</text>
						<view class="price-wp"><text class="goods-price-txt">￥</text><text class="goods-price">999</text></view>
						<button type="primary" class="booking-btn">购买</button>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	
import uniFab from '@/components/uni-fab/uni-fab.vue';
export default {
    data() {
        return {
            horizontal: 'right',
            vertical: 'bottom',
            direction: 'horizontal',
            pattern: {
                color: '#666',
                backgroundColor: '#fff',
                selectedColor: '#333',
                buttonColor:"#333"
            },
            content: [
                {
                    iconPath: 'static/icon_heart.png',
                    selectedIconPath: '',
                    text: '收藏',
                    active: false
                },
                {
                    iconPath: 'static/icon_shop.png',
                    selectedIconPath: '',
                    text: '购买',
                    active: false
                },
                {
                    iconPath: 'static/icon_hand.png',
                    selectedIconPath: '',
                    text: '推荐',
                    active: false
                }
            ]
        };
    },
    methods: {
        trigger(e) {
            console.log(e);
            this.content[e.index].active = !e.item.active;
            uni.showModal({
                title: '提示',
                content: `您${this.content[e.index].active?'选中了':'取消了'}${e.item.text}`,
                success: function(res) {
                    if (res.confirm) {
                        console.log('用户点击确定');
                    } else if (res.cancel) {
                        console.log('用户点击取消');
                    }
                }
            });
        }
    },
    components: {
        uniFab
    }
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
	background-color: #f5f5f5;
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
}
.type-lf-txt{
	width: 100%;
	height: 80rpx;
	line-height: 80rpx;
	text-align: center;
	font-size: 32rpx;
	color: #333;
	display:block;	
	border-bottom: 2rpx solid #ddd;
}
.top-title{
	font-weight: bold;
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
