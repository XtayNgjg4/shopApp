<template>
	<view class="container">
		<view class="headerNav">
			<view class="nav-item" :class="{ current: 0 === tabCurrentIndex }" :id="'tab' + 0" @click="changeTab(0)">
				<view class="">今日推荐</view>
			</view>
			<view class="nav-item" :class="{ current: 1 === tabCurrentIndex }" :id="'tab' + 1" @click="changeTab(1)">
				<view class="">热门商品</view>
			</view>
			<view class="nav-item" :class="{ current: 2 === tabCurrentIndex }" :id="'tab' + 2" @click="changeTab(2)">
				<view class="">男装</view>
			</view>
		</view>

		<swiper id="swiper" class="swiper-box" :current="tabCurrentIndex" @change="changeTab">
			<swiper-item class="swiperItem">
				<scroll-view class="panel-scroll-box" :scroll-y="true" @scrolltolower="">
					<view class="contantList-item">
						<view class="item-box">
							<image
								mode="widthFix"
								src="http://img3m2.ddimg.cn/94/23/1426369522-1_h_2.jpg"
							></image>
							<view class="item-box-con">
								<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
								<view class="itemDown">
									<view class="item-box-price">￥888</view>
									<view class="buyBtn">
										立即抢购
									</view>
								</view>
								
							</view>
						</view>
						<view class="item-box">
							<image
								mode="widthFix"
								src="//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/606799/2019/0904/133/1b4fb12f-5e56-409c-9fe9-ab7e7e242c9a_420_531_218x274_70.jpg"
							></image>
							<view class="item-box-con">
								<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
								<view class="item-box-price">￥888</view>
							</view>
						</view>
						<view class="item-box">
							<image
								mode="widthFix"
								src="//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/606799/2019/0904/133/1b4fb12f-5e56-409c-9fe9-ab7e7e242c9a_420_531_218x274_70.jpg"
							></image>
							<view class="item-box-con">
								<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
								<view class="item-box-price">￥888</view>
							</view>
						</view>
						<view class="item-box">
							<image
								mode="widthFix"
								src="//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/606799/2019/0904/133/1b4fb12f-5e56-409c-9fe9-ab7e7e242c9a_420_531_218x274_70.jpg"
							></image>
							<view class="item-box-con">
								<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
								
								<view class="item-box-price">￥888</view>
							</view>
						</view>
						<view class="item-box">
							<image
								mode="widthFix"
								src="//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/606799/2019/0904/133/1b4fb12f-5e56-409c-9fe9-ab7e7e242c9a_420_531_218x274_70.jpg"
							></image>
							<view class="item-box-con">
								<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
								<view class="item-box-price">￥888</view>
							</view>
						</view>
					</view>
				</scroll-view>
			</swiper-item>
			<swiper-item class="swiperItem">
				<scroll-view :scroll-y="enableScroll" @scrolltolower="loadMore">
					<view class="contantList-item">
						<view class="item-box">
							<image
								mode="widthFix"
								src="//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/606799/2019/0904/133/1b4fb12f-5e56-409c-9fe9-ab7e7e242c9a_420_531_218x274_70.jpg"
							></image>
							<view class="item-box-con">
								<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
								<view class="item-box-price">￥888</view>
							</view>
						</view>
						<view class="item-box">
							<image
								mode="widthFix"
								src="//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/606799/2019/0904/133/1b4fb12f-5e56-409c-9fe9-ab7e7e242c9a_420_531_218x274_70.jpg"
							></image>
							<view class="item-box-con">
								<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
								<view class="item-box-price">￥888</view>
							</view>
						</view>
						<view class="item-box">
							<image
								mode="widthFix"
								src="//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/606799/2019/0904/133/1b4fb12f-5e56-409c-9fe9-ab7e7e242c9a_420_531_218x274_70.jpg"
							></image>
							<view class="item-box-con">
								<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
								<view class="item-box-price">￥888</view>
							</view>
						</view>
						<view class="item-box">
							<image
								mode="widthFix"
								src="//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/606799/2019/0904/133/1b4fb12f-5e56-409c-9fe9-ab7e7e242c9a_420_531_218x274_70.jpg"
							></image>
							<view class="item-box-con">
								<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
								<view class="item-box-price">￥888</view>
							</view>
						</view>
						<view class="item-box">
							<image
								mode="widthFix"
								src="//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/606799/2019/0904/133/1b4fb12f-5e56-409c-9fe9-ab7e7e242c9a_420_531_218x274_70.jpg"
							></image>
							<view class="item-box-con">
								<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
								<view class="item-box-price">￥888</view>
							</view>
						</view>
					</view>
				</scroll-view>
			</swiper-item>
			<swiper-item class="swiperItem">
				<scroll-view :scroll-y="enableScroll" @scrolltolower="loadMore">
				<view class="contantList-item">
					<view class="item-box">
						<image
							mode="widthFix"
							src="//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/606799/2019/0904/133/1b4fb12f-5e56-409c-9fe9-ab7e7e242c9a_420_531_218x274_70.jpg"
						></image>
						<view class="item-box-con">
							<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
							<view class="item-box-price">￥888</view>
						</view>
					</view>
					<view class="item-box">
						<image
							mode="widthFix"
							src="//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/606799/2019/0904/133/1b4fb12f-5e56-409c-9fe9-ab7e7e242c9a_420_531_218x274_70.jpg"
						></image>
						<view class="item-box-con">
							<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
							<view class="item-box-price">￥888</view>
						</view>
					</view>
					<view class="item-box">
						<image
							mode="widthFix"
							src="//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/606799/2019/0904/133/1b4fb12f-5e56-409c-9fe9-ab7e7e242c9a_420_531_218x274_70.jpg"
						></image>
						<view class="item-box-con">
							<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
							<view class="item-box-price">￥888</view>
						</view>
					</view>
					<view class="item-box">
						<image
							mode="widthFix"
							src="//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2018/04/16/77/4c0df8de-2ff6-42e3-818d-c20ecd2f7953_218x274_70.jpg"
						></image>
						<view class="item-box-con">
							<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
							<view class="item-box-price">￥888</view>
						</view>
					</view>
					<view class="item-box">
						<image
							mode="widthFix"
							src="//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2019/08/07/96/f9924a57-f19a-451b-90f2-9685db37215b_420_531_218x274_70.jpg"
						></image>
						<view class="item-box-con">
							<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
							<view class="item-box-price">￥888</view>
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
	.buyBtn{
		width: 70px;
		height: 25px;
		font-size: 12px;
		line-height: 25px;
		text-align: center;
		background-color: #FEB405;
		color: #FFFFFF;
	}
	.itemDown{
		width: 100%;
		display: flex;
	}
page,
.container {
	height: 100%;
	overflow: hidden;
}

.contantList-item {
	.item-box {
		width: 100%;
		display: flex;
		padding: 10px;
		border-bottom: 1px solid #F5F5F5;
		background-color: #ffffff;
		image {
			width: 100%;
			margin-right: 10px;
		}
		.item-box-con {
			.item-box-title {
				display: -webkit-box;
				font-size: 14px;
				-webkit-box-orient: vertical;
				-webkit-line-clamp: 2;
				overflow: hidden;
				margin: 10px 0;
			}
			.item-box-price {
				flex: 1;
				font-size: 16px;
				color: #b81c22;
			}
		}
	}
}
.headerNav {
	width: 100%;
	height: 100%;
	background-color: #ffffff;

	display: flex;
	.nav-item {
		flex: 1;
		text-align: center;
		font-size: 14px;
		position: relative;
		padding: 8px 0;
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
	padding: 0 10px;
	height: 93%;
	width: 100%;
	
}
.current {
	color: #feb405;
}
.current:after {
	width: 100%;
}
scroll-view {
	height: 100%;
}
.contantList {
	width: 100%;
	position: relative;
	.contantList-item {
	}
}
.msPic{width: 100%;height: 100%;}
</style>
