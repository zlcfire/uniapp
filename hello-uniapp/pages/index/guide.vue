<template>
	<view class="page-section-spacing">
		<text>guide</text>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				homeSlide: [], // 定义值接收轮播图数据
			}
		},
		onLoad() {
			getHomeSlideFunc() 
			{
				var _self = this;
				uni.request({
					url: 'http://appblog.inacorner.top/wp-content/themes/wpApp/api/homeSlide.php',
					success: (res) => {
						_self.homeSlide = res.data.post;
					}
				})
			}
		}
	}
</script>

<style>
	.swiper {
		height: 400upx;
	}

	/*  swiper-item 里面的图片高度 */
	swiper-item image {
		width: 100%;
		height: 400upx;
	}
</style>
