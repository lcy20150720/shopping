<template>
	<view class="page-wrap">
		<view class="img-item" v-for="(item, index) in arr" :key="index">
			<image style="width: 100%;" :mode="item.mode" :src="item.src"></image>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				arr:[
					{
						src: require('../../static/y1.jpg'),
						mode: 'scaleToFill',
					},
					{
						src: require('../../static/y1.jpg'),
						mode: 'scaleToFill',
					},
					{
						src: require('../../static/y1.jpg'),
						mode: 'scaleToFill',
					},
				]
			}
		},
		methods: {
			
		}
	}
</script>

<style>
.page-wrap{
	padding: 30rpx;
	box-sizing: border-box;
}
.img-item{
	width: 640rpx;
	margin: 0 auto 40rpx auto;
}
</style>
