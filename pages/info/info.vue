<template>
	<view class="page-wrap">
		<view class="info-top">
			<view class="info-top-wp">
				<image class="avatar" :src="userData.avatar" mode=""></image>
				<text class="nick-name">{{userData.nickname}}</text>
			</view>
		</view>
		<view class="tab-top">
			<view class="col">
				<navigator url="../../pages/status/status?tabIndex=0" hover-class="navigator-hover">
					<view class="icon">
						<image class="icon-img" src="../../static/d01.png" mode=""></image>
					</view>
					<text class="bm-txt">待付款</text>
				</navigator>
			</view>
			<view class="col">
				<navigator url="../../pages/status/status?tabIndex=1" hover-class="navigator-hover">
					<view class="icon">
						<image class="icon-img" src="../../static/d02.png" mode=""></image>
					</view>
					<text class="bm-txt">待发货</text>
				</navigator>
			</view>
			<view class="col">
				<navigator url="../../pages/status/status?tabIndex=2" hover-class="navigator-hover">
					<view class="icon">
						<image class="icon-img" src="../../static/d03.png" mode=""></image>
					</view>
					<text class="bm-txt">待收货</text>
				</navigator>
			</view>
		</view>
		<view class="list">
			<view class="row">
				<navigator url="../../pages/collect/collect" hover-class="navigator-hover">
                    <image class="icon" src="../../static/c1.png" mode=""></image>
                    <text class="lf-txt">我的收藏</text>
                </navigator>
			</view>
			<view class="row">
				<navigator url="../../pages/address/address" hover-class="navigator-hover">
					<image class="icon" src="../../static/c2.png" mode=""></image>
					<text class="lf-txt">收货地址</text>
				</navigator>
			</view>
			<view class="row">
				<navigator url="../../pages/help/help" hover-class="navigator-hover">
					<image class="icon" src="../../static/c3.png" mode=""></image>
					<text class="lf-txt">帮助中心</text>
				</navigator>
			</view>
			<view class="row">
				<navigator url="../../pages/about/about" hover-class="navigator-hover">
					<image class="icon" src="../../static/c4.png" mode=""></image>
					<text class="lf-txt">关于我们</text>
				</navigator>
			</view>
			<view class="row">
				<navigator url="../../pages/suggest/suggest" hover-class="navigator-hover">
					<image class="icon" src="../../static/c5.png" mode=""></image>
					<text class="lf-txt">意见反馈</text>
				</navigator>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				userData:{
					avatar:require('../../static/head_01.jpg'),
					nickname:'Amilly'
				}
			}
		},
		methods: {
			editUserInfo: function(res){
				console.log(res)
			},
			onDateChange: function(obj){
				this.userData.birthday = obj.detail.value;
			},
		}
	}
</script>

<style>
.page-wrap{
	height: calc( 100vh - 100rpx );
}
.info-top{
	padding-top: 80rpx;
	padding-bottom: 160rpx;
	padding-left: 40rpx;
	padding-right: 40rpx;
	background-color: #eee;
	box-sizing: border-box;
	position: relative;
	background: url('~@/static/bg.jpg');
	position: relative;
	z-index: 5;
}
.info-top-wp{
	position: relative;
}
.info-top .avatar{
	width: 160rpx;
	height: 160rpx;
	border-radius: 50%;
	border: 6rpx solid #fff;
}
.info-top .nick-name{
	color: #fff;
	font-size: 32rpx;
	margin-left: 40rpx;
	position: absolute;
	top: 50%;
	transform: translateY(-50%);
	font-weight: bold;
	height: 48rpx;
	line-height: 48rpx;
	padding-left: 20rpx;
	padding-right: 20rpx;
}
.info-top .avatar,.info-top .nick-name{
	display: inline-block;
	vertical-align: top;
}
.tab-top{
	width: 700rpx;
	height: 200rpx;
	background-color: #FFFFFF;
	margin: -100rpx auto 0 auto;
	display: flex;
	border-radius: 20rpx;
	box-shadow: 0 2rpx 2rpx 2rpx #ddd;
	padding-top: 24rpx;
	box-sizing: border-box;
	position: relative;
	z-index: 10;
}
.tab-top .col{
	width: 33.3%;
	height: 100%;
	display: inline-block;
}
.tab-top .col .icon{
	width: 100rpx;
	height: 100rpx;
	display: block;
	border-radius: 50%;
	margin: 0 auto;
	padding: 20rpx;
	box-sizing: border-box;
}
.tab-top .col .icon-img{
	width: 100%;
	height: 100%;
}
.tab-top .col:nth-child(1) .icon{
	background-color: #FF5722;
}
.tab-top .col:nth-child(2) .icon{
	background-color: #775cff;
	padding: 24rpx;
}
.tab-top .col:nth-child(3) .icon{
	background-color: #1698f9;
}
.tab-top .bm-txt{
	text-align: center;
	color: #333;
	font-size: 32rpx;
	margin: 10rpx auto 0 auto;
	display: block;
}
.list{
	padding-top: 40rpx;
}
.list .row{
	height: 100rpx;
	line-height: 100rpx;
	background-color: #fff;
	border-bottom: 2rpx solid #ddd;
	padding-left: 40rpx;
	padding-right: 40rpx;
}
.list .row .icon{
	width: 60rpx;
	height: 60rpx;
	border-radius: 50%;
	display: inline-block;
	float: left;
	margin-top: 20rpx;
}
.list .row .lf-txt{
	color: #333;
	font-size: 32rpx;
	padding-left: 20rpx;
	display: inline-block;
}
</style>
