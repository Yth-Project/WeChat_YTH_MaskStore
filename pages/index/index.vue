<template>
	<!-- 头部轮播 -->
	<view class="carousel-section">
		<!-- 标题栏和状态栏占位符 -->
		<view class="titleNview-placing"></view>
		<!-- 背景色区域 -->
		<view class="titleNview-background" :style="{backgroundColor:titleNViewBackground}"></view>
		<swiper class="carousel" circular @change="swiperChange">
			<swiper-item v-for="(item, index) in carouselList" :key="index" class="carousel-item" @click="navToDetailPage({title: '轮播广告'})">
				<image :src="item.src" />
			</swiper-item>
		</swiper>
		<!-- 自定义swiper指示器 -->
		<view class="swiper-dots">
			<text class="num">{{swiperCurrent+1}}</text>
			<text class="sign">/</text>
			<text class="num">{{swiperLength}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				carouselList: [],
			}
		},
		onLoad() {

		},
		methods: {
			swiperChange() {},
		}
	}
</script>

<style lang="scss">
/* 头部 轮播图 */
.carousel-section {
	position: relative;
	padding-top: 10px;

	.titleNview-placing {
		height: var(--status-bar-height);
		padding-top: 44px;
		box-sizing: content-box;
	}

	.titleNview-background {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 426upx;
		transition: .4s;
	}
}

</style>
