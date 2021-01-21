<template>
	<view class="page-wrap">
		<view class="top-map">
			<map style="width: 100%; height: 300px;" :latitude="latitude" :longitude="longitude" :markers="covers"></map>
			<view class="search-box">
				<view class="search-wp">
					<input type="text" value="" class="search-inp" placeholder="搜索收货地址"/>
				</view>
			</view>
		</view>
		<view class="address-list">
			<radio-group>
				<view class="address-row" v-for="(item,index) in addressList" :key="index">
					<label class="radio" @change="radioChange">
						<image class="address-img" :src="item.img" mode=""></image>
						<view class="rg-txt">
							<text class="address-name">{{item.name}}</text>
							<view class="distance"><text>{{item.distance}}</text></view>
							<text class="pos-txt">{{item.pos}}</text>
							<radio :value="item.value" class="radio-op" :color="radioColor" :checked="index === current"/>
						</view>
					</label>
				</view>
			</radio-group>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				radioColor: '#FF5722',
				id:0, 
				title: 'map',
				latitude: 23.1207,
				longitude: 113.26406,
				covers: [{
					latitude: 23.1207,
					longitude: 113.26406,
					iconPath: '../../static/map.png'
				}, {
					latitude: 23.1207,
					longitude: 113.26406,
					iconPath: '../../static/map.png'
				}],
				current: 0,
				addressList: [
					{
						img: require('../../static/store.jpg'),
						name:'美宜佳便利店',
						distance:'距离您8公里',
						pos:'广州市同和榕树西街32号',
						value:'r1',
						checked: true,
					},
					{
						img: require('../../static/store.jpg'),
						name:'美宜佳便利店',
						distance:'距离您8公里',
						pos:'广州市同和榕树西街32号',
						value:'r2',
						checked: false,
					},
					{
						img: require('../../static/store.jpg'),
						name:'美宜佳便利店',
						distance:'距离您8公里',
						pos:'广州市同和榕树西街32号',
						value:'r2',
						checked: false,
					},
				]
			}
		},
		methods: {
			 radioChange: function(evt) {
				for (let i = 0; i < this.items.length; i++) {
					if (this.items[i].value === evt.target.value) {
						this.current = i;
						break;
					}
				}
			}
		}
	}
</script>

<style>
.top-map{
	height: 600rpx;
}
.search-box{
	width: 600rpx;
	height: 80rpx;
	position: absolute;
	top: 60rpx;
	left: 50%;
	margin-left: -300rpx;
	background-color: #FFFFFF;
	border-radius: 40rpx;
	overflow: hidden;
}
.search-box .search-inp{
	padding-left: 40rpx;
	box-sizing: border-box;
	height: 80rpx;
	line-height: 80rpx;
}
.address-list{
	width: 100%;
	height: calc( 100vh - 560rpx );
	background-color: #FFFFFF;
	border-top-left-radius: 20rpx;
	border-top-right-radius: 20rpx;
	margin-top: -40rpx;
	position: relative;
	z-index: 5;
	padding: 30rpx 30rpx 0 30rpx;
	box-sizing: border-box;
}
.address-row .radio{
	width: 100%;
	display: flex;
}
.address-row{
	width: 100%;
	height: 200rpx;
	background-color: #f5f5f5;
	border: 2rpx solid #ddd;
	border-radius: 20rpx;
	padding: 20rpx;
	box-sizing: border-box;
	margin-bottom: 20rpx;
}
.address-row .address-img{
	width: 30%;
	height: 160rpx;
	display: inline-block;
	border-radius: 10rpx;
}
.address-row .rg-txt{
	width: 70%;
	display: inline-block;
	height: 160rpx;
	padding-left: 20rpx;
	box-sizing: border-box;
	position: relative;
}
.address-row .address-img,
.address-row .rg-txt{
	vertical-align: top;
}
.address-row .address-name{
	color: #333333;
	font-size: 32rpx;
	font-weight: bold;
}
.address-row .distance{
	color: #666;
	font-size: 28rpx;
}
.address-row .pos-txt{
	color: #666;
	font-size: 30rpx;
}
.address-row .radio-op{
	position: absolute;
	right: 0;
	top: 50%;
	margin-top: -26rpx;
}
</style>
