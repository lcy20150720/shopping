<template>
	<view class="page-wrap">
		<view class="tab">
			<view v-for="(item, index) in tabs" 
			:class="['tab-item', active==index ?'tab-cur':'']" 
			:key="index"
			@click="tabChange(index)">{{tabs[index]}}</view>
		</view>
		<view class="panels">
			<view class="panel-slide" :animation="animationData">
				<view class="tab-panel">
					<view class="order-item">
						<view class="order-item-top">
							<view class="lf-img">
								<image class="img" src="../../static/g1.jpg" mode=""></image>
							</view>
							<view class="rg-txt">
								<view class="txt-top">
									<text class="item-title">测试文字测试文字</text>
									<text class="item-price">￥12.99</text>
								</view>
								<text class="item-amount">×1</text>
							</view>
						</view>
						<view class="order-item-mid">
							实付￥12.99（免运费）
						</view>
						<view class="order-item-bom">
							<button type="default" class="pay-btn">去支付</button>
						</view>
					</view>
				</view>
				
				<view class="tab-panel">
						<view class="order-item">
						<view class="order-item-top">
							<view class="lf-img">
								<image class="img" src="../../static/g1.jpg" mode=""></image>
							</view>
							<view class="rg-txt">
								<view class="txt-top">
									<text class="item-title">测试文字测试文字</text>
									<text class="item-price">￥32.99</text>
								</view>
								<text class="item-amount">×1</text>
							</view>
						</view>
						<view class="order-item-mid">
							实付￥32.99（免运费）
						</view>
						<view class="order-item-bom">
							<button type="default" class="apply-btn">申请退款</button>
							<button type="default" class="prompt-btn">催发货</button>
						</view>
					</view>
				</view>
				<view class="tab-panel">
						<view class="order-item">
						<view class="order-item-top">
							<view class="lf-img">
								<image class="img" src="../../static/g1.jpg" mode=""></image>
							</view>
							<view class="rg-txt">
								<view class="txt-top">
									<text class="item-title">测试文字测试文字</text>
									<text class="item-price">￥22.99</text>
								</view>
								<text class="item-amount">×1</text>
							</view>
						</view>
						<view class="order-item-mid">
							实付￥22.99（免运费）
						</view>
						<view class="order-item-bom">
							<button type="default" class="apply-btn">申请退款</button>
							<button type="default" class="check-btn">查看物流</button>
							<button type="default" class="confirm-btn">确认收货</button>
						</view>
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
				tabs:['待付款','待发货','待收货'],
				active: 0,
				animationData: {},
				winW: '',
			}
		},
		onLoad(opt){
			if(opt.tabIndex!=''){
				this.active = parseInt(opt.tabIndex);
			}
			this.animation = uni.createAnimation({
				duration: 300,
				timingFunction: "ease-in-out",
				delay: 0
			});
		},
		methods: {
			tabChange: function(index){
				var { windowWidth, windowHeight } = uni.getSystemInfoSync();
				this.active = index;
				this.animation.translateX(-windowWidth*index).step();
				this.animationData = this.animation.export();
			}
		},
		
	}
</script>

<style>
.page-wrap{
	height: 100vh;
	background-color: #f5f5f5;
}
.tab{
	width: 100%;
	display: flex;
	box-shadow: 0 2rpx 2rpx 2rpx #eee;
	background-color: #fff;
}
.tab-item{
	width: 33.3%;
	height: 80rpx;
	line-height: 80rpx;
	text-align: center;
	font-size: 32rpx;
	color: #333;
	display: inline-block;
}
.tab-cur{
	color: #ff5722;
}
.panels{
	width: 100%;
	overflow: hidden;
}
.panel-slide{
	width: 300%;
}
.tab-panel{
	width: 750rpx;
	padding: 20rpx 0 30rpx 0;
	box-sizing: border-box;
	display: inline-block;
}
.order-item{
	width: 100%;
	display: block;
	background-color: #fff;
	padding-top: 20rpx;
	overflow: hidden;
	box-shadow: 0 2rpx 2rpx 2rpx #eee;
}
.order-item-top{
	width: 100%;
	height: 160rpx;
	display: flex;
	border-bottom: 2rpx solid #eee;
}
.order-item .lf-img{
	width: 30%;
	height: 160rpx;
}
.order-item .rg-txt{
	width: 70%;
	height: 160rpx;
	padding: 0 30rpx 0 20rpx;
	box-sizing: border-box;
}
.order-item .lf-img,.order-item .rg-txt{
	display: inline-block;
}
.order-item .img{
	width: 100%;
	height: 100%;
	display: block;
}
.order-item-top{
	font-size: 32rpx;
	color: #333;
}
.order-item-top .item-price,.order-item-top .item-amount{
	float: right;
}
.order-item-mid,.order-item-bom{
	color: #333;
	font-size: 32rpx;
	text-align: right;
	width: 100%;
	display: block;
	height: 80rpx;
	line-height: 80rpx;
	border-bottom: 2rpx solid #eee;
	padding: 0 30rpx;
	box-sizing: border-box;
}
.order-item-bom .apply-btn,.order-item-bom .prompt-btn,
.order-item-bom .pay-btn,.order-item-bom .check-btn,
.order-item-bom .confirm-btn{
	width: 176rpx;
	height: 60rpx;
	line-height: 60rpx;
	text-align: center;
	color: #333;
	font-size: 28rpx;
	background-color: #fff;
	border: 2rpx solid #ddd;
	border-radius: 30rpx;
	display: inline-block;
	margin-top: 10rpx;
	margin-left: 20rpx;
}
.order-item-bom .apply-btn:after,.order-item-bom .prompt-btn:after,
.order-item-bom .check-btn:after,.order-item-bom .pay-btn:after,
.order-item-bom .confirm-btn:after{
	display: none;
}
</style>
