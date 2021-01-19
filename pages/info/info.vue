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
				<image class="icon" src="../../static/i01.png" mode=""></image>
				<text class="bm-txt">余额</text>
			</view>
			<view class="col">
				<image class="icon" src="../../static/i02.png" mode=""></image>
				<text class="bm-txt">积分</text>
			</view>
			<view class="col">
				<image class="icon" src="../../static/i03.png" mode=""></image>
				<text class="bm-txt">等级</text>
			</view>
		</view>
		<view class="list">
			<view class="row">
				<image class="icon" src="../../static/c1.png" mode=""></image>
				<text class="lf-txt">我的收藏</text>
			</view>
			<view class="row">
				<image class="icon" src="../../static/c2.png" mode=""></image>
				<text class="lf-txt">收货地址</text>
			</view>
			<view class="row">
				<image class="icon" src="../../static/c3.png" mode=""></image>
				<text class="lf-txt">帮助中心</text>
			</view>
			<view class="row">
				<image class="icon" src="../../static/c4.png" mode=""></image>
				<text class="lf-txt">关于我们</text>
			</view>
			<view class="row">
				<image class="icon" src="../../static/c5.png" mode=""></image>
				<text class="lf-txt">意见反馈</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				userData:{
					avatar:'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-uni-app-doc/6acec660-4f31-11eb-a16f-5b3e54966275.jpg',
					nickname:'Vivi'
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
	z-index: -1;
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
	color: #333;
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
	background-color: rgba(255,255,255,.6);
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
	border-radius: 40rpx;
	box-shadow: 0 2rpx 2rpx 2rpx #ddd;
	padding-top: 24rpx;
	box-sizing: border-box;
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
}
.tab-top .bm-txt{
	text-align: center;
	color: #333;
	font-size: 32rpx;
	margin: 10rpx auto 0 auto;
	display: block;
}
.list{
	padding-left: 40rpx;
	padding-right: 40rpx;
	padding-top: 40rpx;
}
.list .row{
	height: 100rpx;
	line-height: 100rpx;
	background-color: #fff;
	border-bottom: 2rpx solid #ddd;
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
