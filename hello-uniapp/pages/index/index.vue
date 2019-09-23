<template>
	<view class="content">
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" class="swiper" :style="{'height':windowHeight}"
		 @animationfinish="animationfinish">
			<swiper-item>
				<view class="swiper-item" :style="{'height':windowHeight,'background-color':'red'}">A</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item" :style="{'height':windowHeight,'background-color':'red'}">B</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item" :style="{'height':windowHeight,'background-color':'red'}">C</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item" :style="{'height':windowHeight,'background-color':'red'}">进入首页</view>
			</swiper-item>
		</swiper>
		<text :style="{'color':'red','font-weight':'200'}">这是一个sssH1</text>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				windowHeight: '603px',
				title: 'Hello uni-app'
			}
		},
		onLoad() {
			var that = this;
			uni.getSystemInfo({
				success: function(res) {
					// console.log(res)
					that.windowHeight = res.windowHeight + 'px'
				}
			})
		},
		methods: {
			animationfinish(e) {
				console.log(JSON.stringify(e.detail.current))
				if (e.detail.current == 3) {
					console.log('动画已经播放结束')
					setTimeout(function() {
						uni.switchTab({
							url: "../view/index/index"
						});
					}, 1000)
				}
			}
		}
	}
</script>

<style>
	.swiper {
		width: 100%;
	}
</style>
