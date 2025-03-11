<template>
	<view class="xc-container">
		<swiper class="swiper" circular="false" :autoplay="autoplay" :interval="interval" :duration="700" :vertical="true">
			<swiper-item>
				<view class="swiper-item">
					<view>静夜思</view>
					<view>李白</view>
					<view>窗前明月光</view>
					<view>疑是地上霜</view>
					<view>举头望明月</view>
					<view>低头思故乡</view>
				</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">
					<view>xxxx</view>
					<view>李白</view>
					<view>xxxxxxxxx</view>
					<view>xxxxxxxxx</view>
					<view>xxxxxxxxx</view>
					<view>xxxxxxxxx</view>
				</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">
					<view>静夜思</view>
					<view>李白</view>
					<view>窗前明月光</view>
					<view>疑是地上霜</view>
					<view>举头望明月</view>
					<view>低头思故乡</view>
				</view>
			</swiper-item>
		</swiper>
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

<style lang="scss">
	page {
		width: 100%;
		height: 100%;
		background: #ffffff;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.xc-container {
		// height: 96%;
		width: 96%;

		.swiper {
			height: 500px;
			background-color: rgba(217, 217, 217, 0.5);
			border-radius: 8px;
		}
	}
</style>