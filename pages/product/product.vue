<template>
	<view class="container">
		<!-- 头部轮播 -->
		<view class="carousel-section">
			<swiper class="carousel" @change="swiperChange" autoplay interval="2000" duration="500">
				<swiper-item v-for="(item, index) in carouselList" :key="index" class="carousel-item">
					<image :src="item.src" mode="aspectFill" />
				</swiper-item>
			</swiper>
			<!-- 重置小圆点的样式 -->
			<view class="dots">
				<block v-for="(item, index) in carouselList" :key="index">
					<view :class="index == currentSwiper ? 'dot active' : 'dot'"></view>
				</block>
			</view>
		</view>
		<!-- 商品标题及价格 -->
		<view class="product-title-price">
			<text class="product-title">{{title}}</text>
			<text class="product-title-detail">{{titleDetail}}</text>
			<text class="product-price"><span>￥</span>{{price}}</text>
		</view>
		<!-- 商品规格及可选规格 -->
		<view class="specification"></view>
		<view class="choose-specification">
			<view class="choose-title"></view>
			<view class="choose-box">
				<view class="choose-item"></view>
				<view class=""></view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				carouselList: [{
						id: 0,
						src: '/static/logo.png',
						backgroundColor: 'rgba(203,87,60)'
					},
					{
						id: 1,
						src: '/static/logo.png',
						backgroundColor: 'rgba(205,216,218)'
					},
					{
						id: 2,
						src: '/static/logo.png',
						backgroundColor: 'rgba(183,73,68)'
					},
				],
				currentSwiper: 0,
				title: "医用外科口罩",
				titleDetail: '产品详情产品详情产品详情产品详情产品详情产品详情产品详情产品详情产品详情产品详情产品详情产品详情产品详情产品详情',
				price: "999.00"
			};
		},
		methods: {
			swiperChange(e) {
				this.currentSwiper = e.detail.current
			},
		}
	}
</script>

<style lang="scss">
	page {
		.carousel-section {
			padding: 0;
			position: relative;

			.carousel {
				width: 100%;
				height: 600upx;

				.carousel-item {
					width: 100%;
					height: 600upx;

					image {
						width: 100%;
						height: 100%;
					}
				}
			}

			/*用来包裹所有的小圆点 */
			.dots {
				height: 12upx;
				display: flex;
				flex-direction: row;
				justify-content: space-between;
				position: absolute;
				bottom: 20upx;
				left: 50%;
				transform: translateX(-50%);
			}

			/*未选中时的小圆点样式 */
			.dot {
				width: 12upx;
				height: 12upx;
				border-radius: 6upx;
				background: #599590;
				margin-right: 18upx;
			}

			.dot:last-child {
				margin-right: 0;
			}

			/*选中以后的小圆点样式 */
			.active {
				width: 39upx;
				height: 12upx;
				border-radius: 6upx;
				background-color: #55DACE;
			}
		}
	}
</style>
