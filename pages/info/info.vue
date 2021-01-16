<template>
	<view>
		<view class="user-list x-bc">
			<text class="list-name">头像</text>
			<view class="x-f">
				<image class="avatar" :src="userData.avatar" mode=""></image>
				<text class="cuIcon-right"></text>
			</view>
		</view>
		<view class="user-list x-bc">
			<text class="list-name">昵称</text>
			<view class="x-f">
				<input class="list-val" v-model="userData.nickname" />
				<text class="cuIcon-right"></text>
			</view>
		</view>
		<picker style="width: 750rpx;" mode="date" :value="userData.birthday"  @change="onDateChange">
			<view class="user-list x-bc">
				<text class="list-name">生日</text>
				<view class="x-f">
					<text class="list-val">{{ userData.birthday || '请选择生日~' }}</text>
					<text class="cuIcon-right"></text>
				</view>
			</view>
		</picker>
		<view class="user-list x-bc">
			<text class="list-name">修改手机号</text>
			<view class="x-f">
				<text class="list-val">{{ userData.mobile }}</text>
				<text class="cuIcon-right"></text>
			</view>
		</view>
		<view class="btn-box flex align-center justify-center"><button class="cu-btn confirem-btn" @tap="editUserInfo">保存</button></view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				userData:{
					avatar:'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-uni-app-doc/6acec660-4f31-11eb-a16f-5b3e54966275.jpg',
					nickname: 'lcy',
					birthday: '12-01-25',
					mobile: '13600136000',
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
		
	.x-f{
		display: inline-block;
		float:right;
		
	}
		
	.list-val{
		line-height: 100rpx;
		height: 100rpx;
		float: right;
	}
   .user-list {
	background: #fff;
	height: 100rpx;
	border-bottom: 1rpx solid #f6f6f6;
	padding: 0 20rpx;
	}

	.list-name {
		font-size: 28rpx;
		line-height: 100rpx;
	}

	.avatar {
		width: 67rpx;
		height: 67rpx;
		border-radius: 50%;
		margin-top: 16rpx;
		float:right;
	}

	.cuIcon-right {
		margin-left: 25rpx;
	}

	.list-val {
		color: #999;
		font-size: 28rpx;
		text-align: right;
	}
.btn-box {
	margin-top: 60rpx;
}
.confirem-btn {
		width: 710rpx;
		height: 80rpx;
		background: linear-gradient(90deg, rgba(233, 180, 97, 1), rgba(238, 204, 137, 1));
		border: 1rpx solid rgba(238, 238, 238, 1);
		border-radius: 40rpx;
		font-size: 30rpx;
		color: rgba(255,255,255, 0.9);
	}
</style>
