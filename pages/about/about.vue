<template>
	<view class="page-wrap">
		<view class="list">
			<view class="row">
				<navigator url="../../pages/qualification/qualification" hover-class="navigator-hover">
					<text>平台资质</text>
				</navigator>
			</view>
			<view class="row">
				<navigator url="../../pages/policy/policy" hover-class="navigator-hover">
					<text>隐私政策</text>
				</navigator>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
.list{
	padding-top: 30rpx;
	padding-left: 30rpx;
	padding-right: 30rpx;
	box-sizing: border-box;
}
.list .row{
	height: 80rpx;
	line-height: 80rpx;
	border-bottom: 2rpx solid #eee;
	font-size: 28rpx;
}
</style>
