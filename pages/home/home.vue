<template>
	<view class="content">
		<uni-swiper-dot :info="info" :current="current" field="content" :mode="mode">
			<swiper class="swiper-box" @change="change">
				<swiper-item v-for="(item ,index) in info" :key="index">
					<view class="swiper-item">
						 <image style="width: 100%;height: 300rpx;" :mode="item.mode" :src="item.src"></image>
					</view>
				</swiper-item>
			</swiper>
		</uni-swiper-dot>
		<view class="btn-area">
                <navigator url="navigate/navigate?title=navigate" hover-class="navigator-hover">
                  
                </navigator>
               
        </view>
	</view>
</template>

<script>
import uniSwiperDot from "@/components/uni-swiper-dot/uni-swiper-dot.vue"
export default {
    data() {
        return {
            info: [{
                mode: 'scaleToFill',
				src: 'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-uni-app-doc/6acec660-4f31-11eb-a16f-5b3e54966275.jpg'
            }, {
                mode: 'scaleToFill',
                src: 'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-uni-app-doc/6acec660-4f31-11eb-a16f-5b3e54966275.jpg'
            }, {
                mode: 'scaleToFill',
                src: 'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-uni-app-doc/6acec660-4f31-11eb-a16f-5b3e54966275.jpg'
            }],
            current: 0,
            mode: 'round',
        }
    },
	components: {uniSwiperDot},
    methods: {
        change(e) {
            this.current = e.detail.current;
        },
    },
	 onLoad: function (option) { //option为object类型，会序列化上个页面传递的参数
		console.log(option.id); //打印出上个页面传递的参数。
		console.log(option.name); //打印出上个页面传递的参数。
	}
}

</script>

<style>
	
</style>
