<template>
	<view>
		<view class="header" :style="{ position: headerPosition }">
			<view class="input-box">
				<input placeholder="默认关键字" placeholder-style="color:#c0c0c0;" @tap="toSearch()" />
				<view class="icon search"></view>
			</view>
		</view>
		<!-- 占位 -->
		<view class="place"></view>
		<view class="category-list">
			<!-- 左侧分类导航 -->
			<scroll-view scroll-y="true" class="left">
				<view class="row" v-for="(category, index) in categoryList" :key="category.id" :class="[index == showCategoryIndex ? 'on' : '']" @tap="showCategory(index)">
					<view class="text">
						<view class="block"></view>
						{{ category.title }}
					</view>
				</view>
			</scroll-view>
			<!-- 右侧子导航 -->
			<scroll-view scroll-y="true" class="right">
				<view class="category" v-for="(category, index) in categoryList" :key="category.id" v-show="index == showCategoryIndex">
					<view class="banner"><image :src="category.banner"></image></view>
					<view class="list">
						<view class="box" v-for="(box, i) in category.list" :key="i" @tap="toShopList">
							<image :src="'/static/images/category/list/' + box.img"></image>
							<view class="text">{{ box.name }}</view>
						</view>
					</view>
				</view>
			</scroll-view>
		</view>
	</view>
</template>
<script>
//高德SDK
export default {
	data() {
		return {
			showCategoryIndex: 0,
			headerPosition: 'fixed',

			//分类列表
			categoryList: [
				{
					id: 1,
					title: '家用电器',
					banner: '/static/images/category/banner.jpg',
					list: [{ name: '冰箱', img: '1.jpg' }, { name: '电视', img: '2.jpg' }, { name: '空调', img: '3.jpg' }]
				},
				{ id: 2, title: '时装', banner: '/static/images/category/banner.jpg', list: [{ name: '打印机', img: '1.jpg' }, { name: '路由器', img: '2.jpg' }] },
				{ id: 3, title: '手机', banner: '/static/images/category/banner.jpg', list: [{ name: '茶具', img: '1.jpg' }, { name: '花瓶', img: '2.jpg' }] }
			]
		};
	},
	onPageScroll(e) {
		//兼容iOS端下拉时顶部漂移
		if (e.scrollTop >= 0) {
			this.headerPosition = 'fixed';
		} else {
			this.headerPosition = 'absolute';
		}
	},
	onLoad() {
		
	},
	methods: {
		//消息列表
		toMsg() {
			uni.navigateTo({
				url: '../../msg/msg'
			});
		},
		toShopList() {
			uni.navigateTo({
				url: `/pages/shopList/shopList`
			});
		},
		//分类切换显示
		showCategory(index) {
			this.showCategoryIndex = index;
		},
		toCategory(e) {
			uni.setStorageSync('catName', e.name);
			uni.navigateTo({
				url: '../../goods/goods-list/goods-list?cid=' + e.id + '&name=' + e.name
			});
		},
		//搜索跳转
		toSearch() {
			uni.showToast({ title: '建议跳转到新页面做搜索功能' });
		}
	}
};
</script>
<style lang="scss">
.status {
	width: 100%;
	height: 0;
	position: fixed;
	z-index: 10;
	background-color: #fff;
	top: 0;
	/*  #ifdef  APP-PLUS  */
	height: var(--status-bar-height); //覆盖样式
	/*  #endif  */
}

.header {
	width: 100%;
	padding: 0 4%;
	height: 100upx;
	display: flex;
	align-items: center;
	position: fixed;
	top: 0;
	z-index: 10;
	background-color: #fff;
	/*  #ifdef  APP-PLUS  */
	top: var(--status-bar-height);
	/*  #endif  */

	.addr {
		width: 120upx;
		height: 60upx;
		flex-shrink: 0;
		display: flex;
		align-items: center;
		font-size: 28upx;
		.icon {
			height: 60upx;
			margin-right: 5upx;
			display: flex;
			align-items: center;
			font-size: 42upx;
			color: #ffc50a;
		}
	}
	.input-box {
		width: 100%;
		height: 60upx;
		background-color: #f5f5f5;
		border-radius: 30upx;
		position: relative;
		display: flex;
		align-items: center;
		.icon {
			display: flex;
			align-items: center;
			position: absolute;
			top: 0;
			right: 0;
			width: 60upx;
			height: 60upx;
			font-size: 34upx;
			color: #c0c0c0;
		}
		input {
			padding-left: 28upx;
			height: 28upx;
			font-size: 28upx;
		}
	}
	.icon-btn {
		width: 60upx;
		height: 60upx;
		flex-shrink: 0;
		display: flex;
		.icon {
			width: 60upx;
			height: 60upx;
			display: flex;
			justify-content: flex-end;
			align-items: center;
			font-size: 42upx;
		}
	}
}
.place {
	background-color: #ffffff;
	height: 100upx;
	/*  #ifdef  APP-PLUS  */
	margin-top: var(--status-bar-height);
	/*  #endif  */
}
.category-list {
	width: 100%;
	background-color: #fff;
	display: flex;
	.left,
	.right {
		position: absolute;
		background: #ffffff;
		top: 100upx;
		/*  #ifdef  APP-PLUS  */
		top: calc(100upx + var(--status-bar-height));
		/*  #endif  */
		bottom: 0upx;
	}
	.left {
		width: 24%;
		left: 0upx;
		background-color: #f2f2f2;
		.row {
			width: 100%;
			height: 90upx;
			display: flex;
			align-items: center;
			.text {
				width: 100%;
				position: relative;
				font-size: 28upx;
				display: flex;
				justify-content: center;
				color: #3c3c3c;
				.block {
					position: absolute;
					width: 0upx;
					left: 0;
				}
			}
			&.on {
				height: 100upx;
				background-color: #fff;
				.text {
					font-size: 30upx;
					font-weight: 600;
					color: #2d2d2d;
					.block {
						width: 10upx;
						height: 80%;
						top: 10%;
						background-color: #feb405;
					}
				}
			}
		}
	}
	.right {
		width: 76%;
		left: 24%;
		.category {
			width: 100%;
			padding: 20upx 3%;
			.banner {
				width: 100%;
				height: 24.262vw;
				border-radius: 10upx;
				overflow: hidden;
				box-shadow: 0upx 5upx 20upx rgba(0, 0, 0, 0.3);
				image {
					width: 100%;
					height: 24.262vw;
				}
			}
			.list {
				margin-top: 40upx;
				width: 100%;
				display: flex;
				flex-wrap: wrap;
				.box {
					width: calc(71.44vw / 3);
					margin-bottom: 30upx;
					display: flex;
					justify-content: center;
					align-items: center;
					flex-wrap: wrap;
					image {
						width: 60%;
						height: calc(71.44vw / 3 * 0.6);
					}
					.text {
						margin-top: 5upx;
						width: 100%;
						display: flex;
						justify-content: center;
						font-size: 26upx;
					}
				}
			}
		}
	}
}
</style>
