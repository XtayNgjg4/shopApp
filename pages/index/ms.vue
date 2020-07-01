<template>
	<view class="container">
		<!-- <image src="../../static/images/indexpic/idxbn1.jpg" mode="" class="msPic"></image> -->
		<view class="headerNav">
			<view class="nav-item" :class="{ current: 0 === tabCurrentIndex }" :id="'tab' + 0" @click="changeTab(0)"><view class="">即将售罄</view></view>
			<view class="nav-item" :class="{ current: 1 === tabCurrentIndex }" :id="'tab' + 1" @click="changeTab(1)"><view class="">抢购中</view></view>
			<view class="nav-item" :class="{ current: 2 === tabCurrentIndex }" :id="'tab' + 2" @click="changeTab(2)"><view class="">即将开抢</view></view>
		</view>
		<view class="endTime">
			———— 距离结束 ————
		</view>

		<swiper id="swiper" class="swiper-box" :current="tabCurrentIndex" @change="changeTab">
			<swiper-item class="swiperItem">
				<scroll-view class="panel-scroll-box" :scroll-y="true" @scrolltolower="">
					<view class="contantList-item">
						<view class="item-box">
							<image mode="widthFix" src="http://img3m2.ddimg.cn/94/23/1426369522-1_h_2.jpg"></image>
							<view class="item-box-con">
								<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
								<view class="progress-box">
									<progress percent="40" active="true" backgroundColor="#FFCAC1" activeColor="#e93b3d" stroke-width="16" />
									<view class="progress-txt">
										已抢40%
									</view>
								</view>
								<view class="itemDown">
									<view class="item-box-price">
										<view>￥888</view>
										<view class="disPrice">￥8888</view>
									</view>
									<view class="buyBtn">立即抢购</view>
								</view>
							</view>
						</view>
						<view class="item-box">
							<image mode="widthFix" src="http://img3m2.ddimg.cn/94/23/1426369522-1_h_2.jpg"></image>
							<view class="item-box-con">
								<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
								<view class="progress-box">
									<progress percent="40" active="true" backgroundColor="#FFCAC1" activeColor="#e93b3d" stroke-width="16" />
									<view class="progress-txt">
										已抢40%
									</view>
								</view>
								<view class="itemDown">
									<view class="item-box-price">
										<view>￥888</view>
										<view class="disPrice">￥8888</view>
									</view>
									<view class="buyBtn">立即抢购</view>
								</view>
							</view>
						</view>
						<view class="item-box">
							<image mode="widthFix" src="http://img3m2.ddimg.cn/94/23/1426369522-1_h_2.jpg"></image>
							<view class="item-box-con">
								<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
								<view class="progress-box">
									<progress percent="40" active="true" backgroundColor="#FFCAC1" activeColor="#e93b3d" stroke-width="16" />
									<view class="progress-txt">
										已抢40%
									</view>
								</view>
								<view class="itemDown">
									<view class="item-box-price">
										<view>￥888</view>
										<view class="disPrice">￥8888</view>
									</view>
									<view class="buyBtn">立即抢购</view>
								</view>
							</view>
						</view>
						<view class="item-box">
							<image mode="widthFix" src="http://img3m2.ddimg.cn/94/23/1426369522-1_h_2.jpg"></image>
							<view class="item-box-con">
								<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
								<view class="progress-box">
									<progress percent="40" active="true" backgroundColor="#FFCAC1" activeColor="#e93b3d" stroke-width="16" />
									<view class="progress-txt">
										已抢40%
									</view>
								</view>
								<view class="itemDown">
									<view class="item-box-price">
										<view>￥888</view>
										<view class="disPrice">￥8888</view>
									</view>
									<view class="buyBtn">立即抢购</view>
								</view>
							</view>
						</view>
						<view class="item-box">
							<image mode="widthFix" src="http://img3m2.ddimg.cn/94/23/1426369522-1_h_2.jpg"></image>
							<view class="item-box-con">
								<view class="item-box-title">（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫（独家新品）ERDOS 19秋冬新品纯山羊绒圆领男式羊绒衫</view>
								<view class="progress-box">
									<progress percent="40" active="true" backgroundColor="#FFCAC1" activeColor="#e93b3d" stroke-width="16" />
									<view class="progress-txt">
										已抢40%
									</view>
								</view>
								<view class="itemDown">
									<view class="item-box-price">
										<view>￥888</view>
										<view class="disPrice">￥8888</view>
									</view>
									<view class="buyBtn">立即抢购</view>
								</view>
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
	.endTime{
		width: 100%;
		font-size: 14px;
		text-align: center;
		height: 30px;
		line-height: 30px;
	}
.buyBtn {
	width: 70px;
	height: 25px;
	font-size: 12px;
	line-height: 25px;
	text-align: center;
	background-color: #feb405;
	color: #ffffff;
}
.itemDown {
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
		border-bottom: 1px solid #f5f5f5;
		background-color: #ffffff;
		image {
			width: 100%;
			margin-right: 10px;
		}
		.item-box-con {
			// padding: 10px 0;
			.item-box-title {
				display: -webkit-box;
				font-size: 12px;
				-webkit-box-orient: vertical;
				-webkit-line-clamp: 2;
				overflow: hidden;
				line-height: 20px;
			}
			.item-box-price {
				display: flex;
				flex: 1;
				font-size: 16px;
				color: #b81c22;
			}
		}
	}
}
.headerNav {
	width: 100%;
	background-image:url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAu4AAABmCAIAAAAbA4MBAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAyhpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw/eHBhY2tldCBiZWdpbj0i77u/IiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8+IDx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IkFkb2JlIFhNUCBDb3JlIDUuNi1jMTM4IDc5LjE1OTgyNCwgMjAxNi8wOS8xNC0wMTowOTowMSAgICAgICAgIj4gPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4gPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIgeG1sbnM6eG1wPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvIiB4bWxuczp4bXBNTT0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wL21tLyIgeG1sbnM6c3RSZWY9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9zVHlwZS9SZXNvdXJjZVJlZiMiIHhtcDpDcmVhdG9yVG9vbD0iQWRvYmUgUGhvdG9zaG9wIENDIDIwMTcgKE1hY2ludG9zaCkiIHhtcE1NOkluc3RhbmNlSUQ9InhtcC5paWQ6N0QxMjU1MEM5NEJBMTFFOEIxNjdBM0MyREU3MjEyMUQiIHhtcE1NOkRvY3VtZW50SUQ9InhtcC5kaWQ6N0QxMjU1MEQ5NEJBMTFFOEIxNjdBM0MyREU3MjEyMUQiPiA8eG1wTU06RGVyaXZlZEZyb20gc3RSZWY6aW5zdGFuY2VJRD0ieG1wLmlpZDo3RDEyNTUwQTk0QkExMUU4QjE2N0EzQzJERTcyMTIxRCIgc3RSZWY6ZG9jdW1lbnRJRD0ieG1wLmRpZDo3RDEyNTUwQjk0QkExMUU4QjE2N0EzQzJERTcyMTIxRCIvPiA8L3JkZjpEZXNjcmlwdGlvbj4gPC9yZGY6UkRGPiA8L3g6eG1wbWV0YT4gPD94cGFja2V0IGVuZD0iciI/Pr1BR2IAAKUaSURBVHja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);
	background-size: cover;
	display: flex;
	.nav-item {
		flex: 1;
		text-align: center;
		font-size: 14px;
		position: relative;
		padding: 8px 0;
		color: hsla(0,0%,100%,.6);
	}
}
.nav-item:after {
	content: '';
	width: 0;
	height: 0;
	border-bottom: 4rpx solid #FFFFFF;
	position: absolute;
	left: 50%;
	bottom: 0;
	transform: translateX(-50%);
	transition: 0.3s;
}

.swiper-box {
	height: 90%;
	width: 100%;
}
.current {
	color: #FFFFFF!important;
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
.msPic {
	width: 100%;
	height: 100%;
}
.progress-box {
	position: relative;
	width: 70%;
	margin: 8% 0;
}

.progress-txt{
	width: 100%;
	position: absolute;
	top: 50%;
	left: 50%;
	transform: translate(-50%,-50%);
	font-size: 12px;
	color: #F8F8F8;
	
}
.disPrice {
	flex: 1;
	font-size: 12px;
	color: #CCCCCC;
	text-decoration: line-through;
}
</style>
