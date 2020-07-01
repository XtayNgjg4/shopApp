<template>
	<view class="container">
			
		<view class="headerNav">
			<view class="nav-item" :class="{ current: 0 === tabCurrentIndex }" :id="'tab' + 0" @click="changeTab(0)">推荐</view>
			<view class="nav-item" :class="{ current: 1 === tabCurrentIndex }" :id="'tab' + 1" @click="changeTab(1)">活动</view>
			<view class="nav-item" :class="{ current: 2 === tabCurrentIndex }" :id="'tab' + 2" @click="changeTab(2)">限时特惠</view>
		</view>

		<swiper id="swiper" class="swiper-box" :current="tabCurrentIndex" @change="changeTab">
			<swiper-item class="swiperItem">
				<scroll-view class="panel-scroll-box" :scroll-y="true" @scrolltolower="">
					<view class="contantList-item">
						<view class="activeItem">
							<view class="activeItem-pic">
								<image src="https://h2.appsimg.com/a.appsimg.com/upload/brand/upcb/2019/08/22/187/ias_156645224887402_1135x545_85.jpg" mode=""></image>
							</view>
							<view class="activeItem-con">
								<view>秋季商品限时特价</view>
								<view>
									<text class="acNum">5</text>
									折起
								</view>
							</view>
						</view>
						<view class="activeItem">
							<view class="activeItem-pic">
								<image src="https://h2.appsimg.com/a.appsimg.com/upload/brand/upcb/2019/08/22/187/ias_156645224887402_1135x545_85.jpg" mode=""></image>
							</view>
							<view class="activeItem-con">
								<view>秋季商品限时特价</view>
								<view>
									<text class="acNum">5</text>
									折起
								</view>
							</view>
						</view>
					</view>
				</scroll-view>
			</swiper-item>
			<swiper-item class="swiperItem">
				<scroll-view :scroll-y="enableScroll" @scrolltolower="loadMore">
					<view class="contantList-item">
						<view class="activeItem">
							<view class="activeItem-pic">
								<image src="https://h2.appsimg.com/a.appsimg.com/upload/brand/upcb/2019/08/22/187/ias_156645224887402_1135x545_85.jpg" mode=""></image>
							</view>
							<view class="activeItem-con">
								<view>秋季商品限时特价</view>
								<view>
									<text class="acNum">5</text>
									折起
								</view>
							</view>
						</view>
						<view class="activeItem">
							<view class="activeItem-pic">
								<image src="https://h2.appsimg.com/a.appsimg.com/upload/brand/upcb/2019/08/22/187/ias_156645224887402_1135x545_85.jpg" mode=""></image>
							</view>
							<view class="activeItem-con">
								<view>秋季商品限时特价</view>
								<view>
									<text class="acNum">5</text>
									折起
								</view>
							</view>
						</view>
						<view class="activeItem">
							<view class="activeItem-pic">
								<image src="https://h2.appsimg.com/a.appsimg.com/upload/brand/upcb/2019/08/22/187/ias_156645224887402_1135x545_85.jpg" mode=""></image>
							</view>
							<view class="activeItem-con">
								<view>秋季商品限时特价</view>
								<view>
									<text class="acNum">5</text>
									折起
								</view>
							</view>
						</view>
					</view>
				</scroll-view>
			</swiper-item>
			<swiper-item class="swiperItem">
				<scroll-view :scroll-y="enableScroll" @scrolltolower="loadMore">
					<view class="contantList-item">
						<view class="activeItem">
							<view class="activeItem-pic">
								<image src="https://h2.appsimg.com/a.appsimg.com/upload/brand/upcb/2019/08/22/187/ias_156645224887402_1135x545_85.jpg" mode=""></image>
							</view>
							<view class="activeItem-con">
								<view>秋季商品限时特价</view>
								<view>
									<text class="acNum">5</text>
									折起
								</view>
							</view>
						</view>
						<view class="activeItem">
							<view class="activeItem-pic">
								<image src="https://h2.appsimg.com/a.appsimg.com/upload/brand/upcb/2019/08/22/187/ias_156645224887402_1135x545_85.jpg" mode=""></image>
							</view>
							<view class="activeItem-con">
								<view>秋季商品限时特价</view>
								<view>
									<text class="acNum">5</text>
									折起
								</view>
							</view>
						</view>
						<view class="activeItem">
							<view class="activeItem-pic">
								<image src="https://h2.appsimg.com/a.appsimg.com/upload/brand/upcb/2019/08/22/187/ias_156645224887402_1135x545_85.jpg" mode=""></image>
							</view>
							<view class="activeItem-con">
								<view>秋季商品限时特价</view>
								<view>
									<text class="acNum">5</text>
									折起
								</view>
							</view>
						</view>
					</view>
				</scroll-view>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
 let windowWidth = 0,
	scrollTimer = false,
	tabBar;
 export default {
	data() {
		return {
			tabCurrentIndex: 0, //当前选项卡索引
			scrollLeft: 0, //顶部选项卡左滑距离
			enableScroll: true,
			tabBars: []
		};
	},
	async onLoad() {
		// 获取屏幕宽度
		windowWidth = uni.getSystemInfoSync().windowWidth;
	},
	methods: {
		setEnableScroll(enable) {
			if (this.enableScroll !== enable) {
				this.enableScroll = enable;
			}
		},
		async changeTab(e) {
			if (scrollTimer) {
				//多次切换只执行最后一次
				clearTimeout(scrollTimer);
				scrollTimer = false;
			}
			let index = e;
			//e=number为点击切换，e=object为swiper滑动切换
			if (typeof e === 'object') {
				index = e.detail.current;
			}
			if (typeof tabBar !== 'object') {
				tabBar = await this.getElSize('nav-bar');
			}
			//计算宽度相关
			// let tabBarScrollLeft = tabBar.scrollLeft;
			let width = 0;
			let nowWidth = 0;
			//获取可滑动总宽度
			for (let i = 0; i <= index; i++) {
				let result = await this.getElSize('tab' + i);
				width += result.width;
				if (i === index) {
					nowWidth = result.width;
				}
			}
			if (typeof e === 'number') {
				//点击切换时先切换再滚动tabbar，避免同时切换视觉错位
				this.tabCurrentIndex = index;
			}
			//延迟300ms,等待swiper动画结束再修改tabbar
			scrollTimer = setTimeout(() => {
				if (width - nowWidth / 2 > windowWidth / 2) {
					//如果当前项越过中心点，将其放在屏幕中心
					this.scrollLeft = width - nowWidth / 2 - windowWidth / 2;
				} else {
					this.scrollLeft = 0;
				}
				if (typeof e === 'object') {
					this.tabCurrentIndex = index;
				}
				this.tabCurrentIndex = index;
				//
				//
				// 	//第一次切换tab，动画结束后需要加载数据
				// 	let tabItem = this.tabBars[this.tabCurrentIndex];
				// 	if(this.tabCurrentIndex !== 0 && tabItem.loaded !== true){
				// 		this.loadNewsList('add');
				// 		tabItem.loaded = true;
				// 	}
			}, 300);
		},
		getElSize(id) {
			return new Promise((res, rej) => {
				let el = uni.createSelectorQuery().select('#' + id);
				el.fields(
					{
						size: true,
						scrollOffset: true,
						rect: true
					},
					data => {
						res(data);
					}
				).exec();
			});
		}
	}
};
</script>

<style lang="scss">

page,
.container {
	height: 100%;
	overflow: hidden;
}

.contantList-item {
	width: 100%;
	padding: 20px 0;
}
.headerNav {
	width: 100%;
	background-color: #ffffff;
	height: 5%;
	display: flex;
	.nav-item {
		flex: 1;
		text-align: center;
		font-size: 14px;
		position: relative;
	}
}
.nav-item:after {
	content: '';
	width: 0;
	height: 0;
	border-bottom: 4rpx solid #feb405;
	position: absolute;
	left: 50%;
	bottom: 0;
	transform: translateX(-50%);
	transition: 0.3s;
}

.swiper-box {
	height: 95%;
	width: 100%;
}
.current {
	color: #feb405;
}
.current:after {
	width: 50%;
}
scroll-view {
	height: 100%;
}
.contantList {
	width: 100%;
	position: relative;
}

.activeItem {
	width: 95%;
	background: #ffffff;
	border-radius: 15px;
	overflow: hidden;
	margin: 0 auto 20px auto;
	.activeItem-con {
		padding: 10px 5px;
		view:first-child {
			font-size: 18px;
			color: rgb(34, 34, 34);
			margin-bottom: 5px;
		}
		view:last-child {
			font-size: 14px;
			color: rgb(34, 34, 34);
		}
	}
}
.activeItem-pic image {
	width: 100%;
	height: 200px;
}
.acNum {
	color: #b81c22;
}
</style>
