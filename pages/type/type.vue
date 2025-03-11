<template>
	<view class="xc-container">
		<view class="search">
			<uni-search-bar :radius="100" @confirm="search" v-model="searchValue"></uni-search-bar>
		</view>
		
		<view class="xc-container-items" v-for="(item,index) in 10" :key="index">
			<view class="uni-title">精选</view>
			<view>
				<scroll-view class="scroll-view" scroll-x="true" scroll-left="120">
					<view class="scroll-view-item">测试一</view>
					<view class="scroll-view-item">测试二</view>
					<view class="scroll-view-item">测试三</view>
					<view class="scroll-view-item">测试四</view>
					<view class="scroll-view-item">测试五</view>
				</scroll-view>
			</view>
		</view>
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
	.xc-container-items {
		background: #ffffff;
		margin-bottom: 9rpx;
		.uni-title {
			padding: 5px 0px 5px 10px;
		}
	}

	.scroll-view {
		white-space: nowrap;
		width: 100%;
	}

	.scroll-view-item {
		display: inline-block;
		width: 30%;
		height: 120rpx;
		line-height: 290rpx;
		text-align: center;
		border: 1px solid ye;
		
		background-color: rgba(216, 216, 216, 0.5);
		border-radius: 5px;
		margin: 0px 5px 0px 5px;
	}
</style>