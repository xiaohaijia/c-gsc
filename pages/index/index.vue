<template>
	<view class="xc-container">
		<!-- 注意事项通知 -->
		<view class="inform" style="margin: 0rpx;">
			<uni-notice-bar showIcon showClose :single="true" scrollable single text="欢迎来到小陈使用uniapp开发小程序♪(^∇^*)" />
		</view>
		<!-- 轮播图 -->
		<view class="uni-margin-wrap">
			<swiper class="swiper" circular indicator-dots autoplay>
				<swiper-item>
					<image src=""></image>
				</swiper-item>
				<swiper-item>
					<image src=""></image>
				</swiper-item>
				<swiper-item>
					<image src=""></image>
				</swiper-item>
			</swiper>
		</view>
		<!-- 每日一诗 -->
		<view class="xc-yis">
			<view class="uni-title">每日一诗</view>
			<view class="xc-body">
				夜阑卧听风吹雨，铁马冰河入梦来。
			</view>
			<view class="xc-author">
				—— 陆游
			</view>
		</view>
		<!-- 精选tab -->
		<view class="body-view">
			<!-- 使用scroll-view实现tabs滑动切换 -->
			<scroll-view class="top-menu-view" scroll-x="true" :scroll-into-view="tabCurrent">
				<view class="menu-topic-view" v-for="item in tabs" :id="'tabNum'+item.id" :key="(item.id - 1)"
					@click="swichMenu(item.id - 1)">
					<view :class="currentTab==(item.id - 1) ? 'menu-topic-act' : 'menu-topic'">
						<text class="menu-topic-text">{{item.name}}</text>
						<view class="menu-topic-bottom">
							<view class="menu-topic-bottom-color"></view>
						</view>
					</view>
				</view>
			</scroll-view>
			<!-- 内容 -->
			<swiper class="swiper-box-list" :current="currentTab" @change="swiperChange">
				<swiper-item class="swiper-topic-list" v-for="item in swiperDateList" :key="item.id">
					<view class="swiper-item">
						{{item.content}}
					</view>
				</swiper-item>
			</swiper>
		</view>
		<!-- 底部提示 -->
		<view class="xc-di">
			<text>—— 到底了，更多请点击探索 ——</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tabs: [{
						id: 1,
						name: '精选'
					},
					{
						id: 2,
						name: '文案馆'
					},
					{
						id: 3,
						name: '英文美句'
					},
					{
						id: 4,
						name: '网易云'
					},
					{
						id: 5,
						name: '激励'
					}
				],
				currentTab: 0,
				tabCurrent: 'tabNum1',
				// Tab切换内容
				swiperDateList: [{
						id: 1,
						content: '精选'
					},
					{
						id: 2,
						content: '文案馆'
					},
					{
						id: 3,
						content: '英文美句'
					},
					{
						id: 4,
						content: '网易云'
					},
					{
						id: 5,
						content: '激励'
					}
				],
			}
		},
		methods: {
			swichMenu(id) {
				this.currentTab = id
				this.tabCurrent = 'tabNum' + id
			},
			swiperChange(e) {
				let index = e.detail.current
				this.swichMenu(index)
			}
		}
	}
</script>

<style lang="scss">
	.uni-margin-wrap {
		width: 94%;
		border-radius: 8px;
		background: #ffffff;
		margin: 0px auto;
	}

	.xc-yis {
		width: 94%;
		height: 100px;
		background: #ffffff;
		border-radius: 8px;
		margin: 0px auto;
		margin-top: 5px;
		padding-left: 10px;
		padding-top: 5px;
		line-height: 30px;

		.xc-author {
			float: right;
			padding-right: 10px;
		}
	}


	//华东tab栏目
	.body-view {
		height: 100vh;
		width: 94%;
		display: flex;
		flex: 1;
		flex-direction: column;
		overflow: hidden;
		align-items: flex-start;
		justify-content: center;
		margin: 0px auto;
		margin-top: 10px;
	}

	.top-menu-view {
		width: 100%;
		height: 86rpx;
		line-height: 86rpx;
		white-space: nowrap;
		background-color: #FFFFFF;
		border-bottom: 1rpx solid #d8dbe6;
		border-radius: 10px 10px 0px 0px;

		.menu-topic-view {
			display: inline-block;
			white-space: nowrap;
			height: 86rpx;
			position: relative;

			.menu-topic-text {
				font-size: 30rpx;
				color: #303133;
				padding: 10rpx 40rpx;
			}

			.menu-topic-bottom {
				position: absolute;
				bottom: 0;
				width: 100%;

				.menu-topic-bottom-color {
					width: 40rpx;
					height: 4rpx;
				}
			}

			.menu-topic-act .menu-topic-bottom {
				display: flex;
				justify-content: center;
			}

			.menu-topic-act .menu-topic-bottom-color {
				background: #74de92;
			}
		}
	}

	.swiper-box-list {
		width: 100%;
		flex: 1;
		background-color: #FFFFFF;

		.swiper-topic-list {
			width: 100%;
		}
	}
	
	.xc-di{
		height: 40px;
		display: flex;
		justify-content: center;
		align-items: center;
		color: #b1b1b1;
	}
</style>