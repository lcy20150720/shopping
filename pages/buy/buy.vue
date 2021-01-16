<template>
	<view>
		<uni-fab 
            :pattern="pattern"
            :content="content"
            :horizontal="horizontal"
            :vertical="vertical"
            :direction="direction"
            @trigger="trigger"
        ></uni-fab>
	</view>
</template>

<script>
	
import uniFab from '@/components/uni-fab/uni-fab.vue';
export default {
    data() {
        return {
            horizontal: 'right',
            vertical: 'bottom',
            direction: 'horizontal',
            pattern: {
                color: '#666',
                backgroundColor: '#fff',
                selectedColor: '#333',
                buttonColor:"#333"
            },
            content: [
                {
                    iconPath: 'static/icon_heart.png',
                    selectedIconPath: '',
                    text: '收藏',
                    active: false
                },
                {
                    iconPath: 'static/icon_shop.png',
                    selectedIconPath: '',
                    text: '购买',
                    active: false
                },
                {
                    iconPath: 'static/icon_hand.png',
                    selectedIconPath: '',
                    text: '推荐',
                    active: false
                }
            ]
        };
    },
    methods: {
        trigger(e) {
            console.log(e);
            this.content[e.index].active = !e.item.active;
            uni.showModal({
                title: '提示',
                content: `您${this.content[e.index].active?'选中了':'取消了'}${e.item.text}`,
                success: function(res) {
                    if (res.confirm) {
                        console.log('用户点击确定');
                    } else if (res.cancel) {
                        console.log('用户点击取消');
                    }
                }
            });
        }
    },
    components: {
        uniFab
    }
};
</script>

<style>

</style>
