<template>
	<view class="page-wrap">
		<text class="h1">猜你想问</text>
		<view class="problems">
			<view class="pro-row" v-for="(item, index ) in proList" :key="index">
				<view class="pro-top">
					<text>{{index+1}}、{{item.text}}</text>
				</view>
				<view class="pro-bom">
					{{item.cont}}
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	
	export default {
		data() {
			return {
				proList:[
					{
						text:'测试标题测试标题',
						cont:'测试内容',
					},
					{
						text:'测试标题测试标题',
						cont:'测试内容',
					},
					{
						text:'测试标题测试标题',
						cont:'测试内容',
					},
					
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style>
.h1{
	font-weight: bold;
	font-size: 36rpx;
	padding: 30rpx 0 0 30rpx;
	display: block;
}
.problems{
	padding-left: 30rpx;
	padding-right: 30rpx;
	box-sizing: border-box;
}
.pro-top{
	height: 80rpx;
	line-height: 80rpx;
	border-bottom: 2rpx solid #eee;
	font-size: 28rpx;
	color: #333;
}
.pro-bom{
	font-size: 28rpx;
	color: #333;
	padding: 30rpx;
	box-sizing: border-box;
	background-color: #F5F5F5;
	display: none;
}
</style>
