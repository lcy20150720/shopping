<template>
	<view class="page-wrap">
		<view class="suggest-type">
			 <view class="uni-list">
				<view class="uni-list-cell">
					<view class="uni-list-cell-left">
						*建议类型
					</view>
					<view class="uni-list-cell-db">
						<picker @change="bindPickerChange" :value="index" :range="array">
							<view class="uni-input">{{array[index]}}</view>
						</picker>
					</view>
				</view>
			</view>
		</view>
		<view class="suggestion">
			<text class="tp-title">*建议详情</text>
			<textarea placeholder-style="color:#d3d3d3;background-color: #f5f5f5;padding: 20rpx;box-sizing: border-box;" 
			placeholder="请描述建议详情(不少于10字不多于500字)" class="textarea" v-model="suggestion"/>
		</view>
		<view class="submit-panel">
			<button type="default" :class="['submit-btn', index!=0&&suggestion!='' ? 'active':'']">提交</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				array: ['请选择','配送物流相关', '配送包装相关', '平台服务相关', '商品相关', '售后相关', '小程序相关'],
				index: 0,
				suggestion:'',
			}
		},
		methods: {
			bindPickerChange: function(e) {
				console.log('picker发送选择改变，携带值为', e.target.value)
				this.index = e.target.value
			},
		}
	}
</script>

<style>
.page-wrap{
	height: 100vh;
	background-color: #F5F5F5;
}
.tp-title,.uni-list-cell{
	width: 100%;
	height: 80rpx;
	line-height: 80rpx;
	color: #333;
	font-size: 32rpx;
}
.uni-list-cell-left,.uni-list-cell-db{
	display: inline-block;
	vertical-align: top;
}
.uni-list-cell-left{
	width: 25%;
}
.uni-list-cell-db{
	width: 75%;
	height: 80rpx;
	text-align: right;
}
.suggestion,.suggest-type{
	background-color: #fff;
	padding: 0 30rpx;
	box-sizing: border-box;
	margin-bottom: 40rpx;
}
.suggestion{
	padding-bottom: 30rpx;
}
.textarea{
	width: 100%;
	height: 200rpx;
	border-radius: 10rpx;
}
.submit-panel{
	width: 100%;
	padding: 30rpx 30rpx 80rpx 30rpx;
	box-sizing: border-box;
	background-color: #FFFFFF;
}
.submit-btn{
	width: 100%;
	height: 80rpx;
	line-height: 80rpx;
	border-radius: 40rpx;
	margin: 0 auto;
	font-size: 32rpx;
	background-color: #999;
	color: #fff;
	opacity: .3;
}
.submit-btn:after{
	display: none;
}
.active{
	background-color:#FF5722;
	color: #fff;
	opacity: 1;
}
</style>
