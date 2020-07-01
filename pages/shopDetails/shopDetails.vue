<template>
	<view class="container">
		<view class="shopTopNav" :style="{ opacity: TopBarBgColor }">
			<view>主图</view>
			<view>评价</view>
			<view>详情</view>
		</view>
		<view class="shopDetailsView">
			<swiper :indicator-dots="true" :duration="300" class="mainSwiper" :style="{ height: swiperHeight + 'px' }">
				<swiper-item v-for="(swiperItem, index) in swiperPic" :key="index">
					<view class="swiper-item"><image id="swiper-pic" :src="swiperItem.src" mode="widthFix"></image></view>
				</swiper-item>
			</swiper>
			<view class="sdDescribeArea">
				<view class="sd_txt">sad尽快发货数量的就会发生大富豪闪电发货撒地方花了</view>
				<view class="sdPriceBox">
					<text>￥</text>
					<text>10</text>
				</view>
				<view class="bot-row">
					<view class="bot">
						<text>快递：</text>
						<text>0</text>
					</view>
					<view class="bot">
						<text>销量：</text>
						<text>99999</text>
					</view>
					<view class="bot"><text>广东广州</text></view>
				</view>
				<view class="sd-share">分享</view>
			</view>
			<view class="sdSelectArea">
				<view class="SelectTxt">
					<view class="SelectItem" @click="disShow">
						<view>优惠</view>
						<view>领券</view>
						<text class="icon icon-you"></text>
					</view>
					<view class="SelectItem" @click="sizeShow">
						<view>规格</view>
						<view>选择规格</view>
						<text class="icon icon-you"></text>
					</view>
					<view class="SelectItem" @click="showMark">
						<view>服务</view>
						<view>服务政策</view>
						<text class="icon icon-you"></text>
					</view>
				</view>
			</view>
			<view class="sdEvaluateArea">
				<view class="evaluateHead clearfix">
					<view class="evaluateHead_title fl">
						<text>商品评价</text>
						<text>(89)</text>
					</view>
					<view class="evaluateHead_go fr" @tap="navToEvaluatePage">
						<text>好评率</text>
						<text>100%</text>
						<text class="icon icon-you"></text>
					</view>
				</view>
				<view class="evaluateItem">
					<view class="evaluateItem_head">
						<image src="../../static/logo.png" mode=""></image>
						<text>快乐的买家</text>
					</view>
					<view class="evaluateItem_txt">氨基酸的会发生的发挥sad立法会</view>
					<view class="evaluateItem_con">
						<text>2019-9-9</text>
						<text>的技术开发和卡萨丁</text>
					</view>
				</view>
			</view>
			<view class="sdDetailsArea">
				<view class="sdDetails_head">———— 商品详情 ————</view>
				<view class="sdDetails_con">
					<image
						src="https://h2a.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2019/06/01/155/56a7254f-1f14-441a-9518-7644c64614bf.jpg!85.webp"
						mode="widthFix"
					></image>
					<image
						src="https://h2a.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2019/06/01/89/b419fae1-9542-41f8-a276-c1259c018b65.jpg!85.webp"
						mode="widthFix"
					></image>
					<image
						src="https://h2a.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2019/06/01/44/95c9ba8e-dc88-427e-b63f-a8d9ccdb2737.jpg!85.webp"
						mode="widthFix"
					></image>
				</view>
			</view>
		</view>
		<view class="goShopBox">
			<view class="share goShopIcon">
				<image src="../../static/images/dp.png"></image>
				<view>店铺</view>
			</view>
			<navigator class="goshopCar goShopIcon" url="/pages/shopCart/shopCart" open-type="switchTab">
				<image src="../../static/images/kf.png" mode=""></image>
				<view>客服</view>
			</navigator>
			<view class="goCollection goShopIcon">
				<image src="../../static/images/sc.png" mode=""></image>
				<view>收藏</view>
			</view>
			<view class="action-btn-group">
				<button type="primary" class=" action-btn no-border">加入购物车</button>
				<button type="primary" class=" action-btn no-border" @click="navToPlaceOrderPage">立即购买</button>
			</view>
		</view>
		<view class="mask" :class="show" @click="hide"></view>
		<view class="selectService coupon" :class="disMove">
			<scroll-view class="couponCon" scroll-y="true">
				<view class="row" v-for="(row, index) in couponValidList" :key="index">
					<view class="carrier">
						<view class="left">
							<view class="title">{{ row.title }}</view>
							<view class="term">{{ row.termStart }} - {{ row.termEnd }}</view>
							<view class="gap-top"></view>
							<view class="gap-bottom"></view>
						</view>
						<view class="right">
							<view class="ticket">
								<view class="num">{{ row.ticket }}元</view>
							</view>
							<view class="criteria">{{ row.criteria }}</view>
							<view class="use">立即领取</view>
						</view>
					</view>
				</view>
			</scroll-view>
			<view class="completeBtn" :class="show" @click="hide">完成</view>
		</view>
		<view class="selectService size" :class="SizeMove">
			<view class="sizeCon">
				<view class="sizeConTop">
					<view class="sizeConTop-pic">
						<image src="//img.alicdn.com/imgextra/i1/1660537871/O1CN01IWzE6v280xzGLB31p_!!1660537871.jpg_200x200Q50s50.jpg" mode=""></image>
					</view>
					<view class="sizeConTop-txt">
						<view class="sizeConTop-price">￥99.99</view>
						<view class="sizeConTop-z">库存11520件</view>
						<view class="sizeConTop-z">请选择：规格</view>
					</view>
					<view class="sizeConTop-close" :class="show" @click="hide"><image src="../../static/images/close.png" mode=""></image></view>
				</view>
				<view class="sizeConChoose">
					<view class="sizeConChoose-txt">尺码</view>
					<view class="sizeConChoose-item">
						<view>s</view>
						<view>xs</view>
						<view>S</view>
						<view>S</view>
						<view>S</view>
					</view>
				</view>
				<view class="sizeConNum">
					<view class="sizeConChoose-txt">购买数量</view>
					<view>
						<view class="">-</view>
						<input type="number" value="1" />
						<view class="">+</view>
					</view>
				</view>
			</view>
			<view class="sizeGoBtn">
				<view>加入购物车</view>
				<view>立即购买</view>
			</view>
		</view>
		<view class="selectService" :class="move"><view class="selectServiceCon">sdfsdklf</view></view>
	</view>
</template>

<script>
var _this = [];
export default {
	data() {
		return {
			show: 'none',
			move: '',
			disMove: '',
			SizeMove: '',
			swiperHeight: 0,
			TopBarBgColor: {},
			TopBarOpacity: 0,
			swiperPic: [
				{ id: 1, src: 'https://h2a.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/615409/2019/0808/55/7be13ffa-d5c6-422d-9285-28214c6df8e9_720x909_70.jpg!85.webp' },
				{ id: 2, src: 'https://h2a.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/615409/2019/0803/1/c659af8c-7c8f-485a-ba9f-69c3ac57c329_720x909_70.jpg!85.webp' },
				{ id: 3, src: 'https://h2a.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/615409/2019/0803/18/5e6ecb0c-f41f-4fbb-a8cc-ed0257fea7a6_720x909_70.jpg!85.webp' }
			],
			couponValidList: [
				{ id: 1, title: '日常用品立减10元', termStart: '2019-04-01', termEnd: '2019-05-30', ticket: '10', criteria: '满50使用' },
				{ id: 2, title: '家用电器立减100元', termStart: '2019-04-01', termEnd: '2019-05-30', ticket: '100', criteria: '满500使用' },
				{ id: 3, title: '全场立减10元', termStart: '2019-04-01', termEnd: '2019-05-30', ticket: '10', criteria: '无门槛' },
				{ id: 4, title: '全场立减50元', termStart: '2019-04-01', termEnd: '2019-05-30', ticket: '50', criteria: '满1000使用' },
				{ id: 5, title: '全场立减50元', termStart: '2019-04-01', termEnd: '2019-05-30', ticket: '50', criteria: '满1000使用' },
				{ id: 6, title: '全场立减50元', termStart: '2019-04-01', termEnd: '2019-05-30', ticket: '50', criteria: '满1000使用' }
			]
		};
	},
	beforeCreate: function() {
		_this = this;
	},
	mounted: function() {
		this.$nextTick(function() {
			let query = uni.createSelectorQuery().select('#swiper-pic');
			query
				.boundingClientRect(function(data) {
					_this.swiperHeight = data.height;
				})
				.exec();
		});
	},

	methods: {
		navToEvaluatePage() {
			uni.navigateTo({
				url: `/pages/evaluate/evaluate`
			});
		},
		navToPlaceOrderPage() {
			uni.navigateTo({
				url: `/pages/order/placeOrder`
			});
		},
		showMark() {
			(this.show = 'show'), (this.move = 'move');
		},
		disShow() {
			(this.show = 'show'), (this.disMove = 'disMove');
		},
		sizeShow() {
			(this.show = 'show'), (this.SizeMove = 'SizeMove');
		},
		hide() {
			(this.show = 'hide'), (this.move = 'stop'), (this.disMove = 'stop'), (this.SizeMove = 'stop');
			setTimeout(() => {
				this.show = 'none';
			}, 200);
		}
	},
	onPageScroll: function(e) {
		this.opacity = Math.abs(Math.round(e.scrollTop)) / 250;
		this.TopBarBgColor = this.opacity;
	}
};
</script>

<style lang="scss">
	
	
	
	.completeBtn {
		position: fixed;
		bottom: 0;
		left: 0;
		width: 100%;
		background: #f8a120;
		height: 30px;
		line-height: 30px;
		text-align: center;
		color: #ffffff;
		font-size: 12px;
	}
.couponCon {
	width: auto;
	padding: 15px 10px;
	height: 90%; 
}
.sizeGoBtn {
	position: fixed;
	bottom: 0;
	left: 0;
	display: flex;
	width: 100%;
	& > view {
		flex: 1;
		font-size: 12px;
		background-color: #1a191e;
		color: #ffffff;
		height: 48px;
		text-align: center;
		line-height: 48px;
	}
	& > view:last-child {
		background-color: #f8a120;
	}
}
.sizeConNum {
	border-bottom: 1px solid #e5e5e5;
	padding: 10px 0;
	display: flex;
	.sizeConChoose-txt {
		flex: 1;
	}
	& > view:last-child {
		display: flex;
		view {
			flex: 1;
			text-align: center;
		}
		input {
			flex: 1;
			text-align: center;
		}
	}
}
.sizeConChoose-txt {
	font-size: 14px;
	color: #666666;
	margin-bottom: 10px;
}
.sizeConChoose {
	width: 100%;
	border-bottom: 1px solid #e5e5e5;
	padding: 10px 0;
	.sizeConChoose-item {
		display: flex;
		view {
			flex: 1;
			padding: 3px 12px;
			border-radius: 8px;
			color: #555555;
			margin: 0 8px 8px 0;
			font-size: 13px;
			background-color: #f5f5f5;
			text-align: center;
			line-height: 23px;
		}
	}
}
.sizeConTop-close image {
	width: 20px;
	height: 20px;
}
.sizeCon {
	padding: 0 15px 10px;
}
.sizeConTop {
	width: 100%;
	border-bottom: 1px solid #e5e5e5;
	padding: 10px 0;
	display: flex;
	.sizeConTop-pic {
		width: 100px;
		height: 100px;
		margin-top: -40px;
		background-color: #ffffff;
		padding: 4px;
		image {
			width: 100%;
			height: 100%;
		}
	}
}
.sizeConTop-txt {
	flex: 1;
	margin: 0 8px;
	.sizeConTop-price {
		font-size: 16px;
		color: #b81c22;
	}
	.sizeConTop-z {
		font-size: 13px;
		color: #5f646e;
	}
}
@keyframes showLayer {
	0% {
		transform: translateY(110%);
	}
	100% {
		transform: translateY(0);
	}
}
@keyframes hideLayer {
	0% {
		transform: translateY(0);
	}
	100% {
		transform: translateY(110%);
	}
}
@keyframes showPopup {
	0% {
		opacity: 0;
	}
	100% {
		opacity: 1;
	}
}
@keyframes hidePopup {
	0% {
		opacity: 1;
	}
	100% {
		opacity: 0;
	}
}

.shopDetailsView {
	width: 100%;
}
.show.mask {
	display: block;
	animation: showPopup 0.3s linear both;
}
.hide.mask {
	animation: hidePopup 0.3s linear both;
}
.move.selectService {
	animation: showLayer 0.3s linear both;
}
.disMove.selectService {
	animation: showLayer 0.3s linear both;
}
.SizeMove.selectService {
	animation: showLayer 0.3s linear both;
}
.stop.selectService {
	animation: hideLayer 0.3s linear both;
}
.none.mask {
	display: none;
}
.mask {
	position: fixed;
	top: 0;
	width: 100%;
	height: 100%;
	z-index: 21;
	background-color: rgba(0, 0, 0, 0.6);
	transition: 0.6s;
}
.selectService {
	position: fixed;
	bottom: 0;
	background-color: #ffffff;
	width: 100%;
	height: 70%;
	transform: translateY(110%);
	z-index: 9999;
}
.action-btn-group {
	display: flex;
	overflow: hidden;
	box-shadow: 0 20upx 40upx -16upx #fa436a;
	box-shadow: 1px 2px 5px rgba(219, 63, 96, 0.4);
	// background: linear-gradient(to right, #ffac30,#fa436a,#F56C6C);
	margin-left: 20upx;
	position: relative;
	border: 0;
	flex: 1;

	.action-btn {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 100%;
		font-size: 28upx;
		padding: 0;
		border-radius: 0;
		background: #f8a120;
	}
}
.action-btn:first-child {
	background: #1a191e;
}
.goShopBox {
	display: flex;
	width: 100%;
	position: fixed;
	bottom: 0;
	background-color: #ffffff;

	.goShopIcon {
		width: 96upx;
		font-size: 24upx;
		color: #606266;
		text-align: center;
		padding: 12upx 0;
		image {
			width: 40upx;
			height: 40upx;
			margin-bottom: 10upx;
		}
	}
}

.sdDetails_con image {
	width: 100%;
}
.sdDetailsArea {
	.sdDetails_head {
		position: relative;
		width: 100%;
		font-size: 30upx;
		background: #ffffff;
		padding: 30upx 0;
		text-align: center;
	}
}

.evaluateItem_con {
	font-size: 24upx;
	color: #909399;
}
.evaluateItem {
	padding: 10upx 0;
}
.evaluateItem_txt {
	font-size: 32upx;
	margin: 15upx 0;
}
.evaluateItem_head {
	image {
		width: 40upx;
		height: 40upx;
		margin-right: 20upx;
	}
	text {
		font-size: 28upx;
		color: #606266;
	}
}
.evaluateHead {
	font-size: 26upx;
	color: #909399;
}
.evaluateHead_title text:first-child {
	font-size: 30upx;
	color: #303133;
}
.sdEvaluateArea {
	background-color: #ffffff;
	padding: 20upx 30upx;
	margin: 20upx 0;
}
.sdSelectArea {
	background-color: #ffffff;
	margin-top: 20upx;
	.SelectTxt {
		font-size: 24upx;

		.SelectItem {
			padding: 20upx 30upx;
			display: flex;
			border-bottom: 1px solid #f0f0f0;
			view:nth-of-type(2) {
				flex: 1;
				margin-left: 30upx;
			}
		}
	}
}
.sdDescribeArea {
	background-color: #ffffff;
	padding: 20upx 30upx;
	position: relative;
	.sd_txt {
		font-size: 14px;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 2;
		overflow: hidden;
	}
	.sdPriceBox {
		font-size: 48upx;
		color: red;
		margin: 30upx 0;
	}
	.bot-row {
		display: flex;
		font-size: 24upx;
		color: #909399;
		.bot {
			flex: 1;
			&:nth-of-type(2) {
				text-align: center;
			}
			&:last-child {
				text-align: right;
			}
		}
	}
	.sd-share {
		position: absolute;
		width: 50px;
		height: 20px;
		line-height: 20px;
		font-size: 12px;
		right: 0;
		top: 50%;
		transform: translateY(-50%);
		background-color: #f1f1f1;
		color: #969696;
		border-radius: 5px 0 0 5px;
		text-align: center;
	}
}
.mainSwiper {
}
.swiper-item image {
	width: 100%;
	height: 100vw;
}
.shopTopNav {
	position: fixed;
	top: 0;
	transition: 0.6s;
	width: 100%;
	height: 40px;
	line-height: 40px;
	z-index: 98;
	opacity: 0;
	background-color: #ffffff;
	box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
	display: flex;

	view {
		width: 33.3%;
		text-align: center;
		font-size: 14px;
	}
}

.couponCon {
	.tis {
		width: 100%;
		height: 60upx;
		justify-content: center;
		align-items: center;
		font-size: 32upx;
	}
	.row {
		width: 100%;
		height: 24vw;
		margin: 20upx auto 10upx auto;
		border-radius: 8upx;
		// box-shadow: 0upx 0 10upx rgba(0,0,0,0.1);
		align-items: center;
		overflow: hidden;
		.menu {
			.icon {
				color: #fff;
				font-size: 50upx;
			}
			position: absolute;
			width: 28%;
			height: 100%;
			right: 0;
			justify-content: center;
			align-items: center;
			background-color: red;
			color: #fff;
			z-index: 2;
		}
		.carrier {
			background-color: #f5f5f5;
			display: flex;
			width: 100%;
			height: 100%;
			.left {
				width: 100%;
				padding: 20px 10px;

				.title {
					font-size: 16px;
					margin-bottom: 15px;
				}
				.term {
					font-size: 13px;
					color: #999;
				}
				position: relative;
				.gap-top,
				.gap-bottom {
					position: absolute;
					width: 20upx;
					height: 20upx;
					right: -10upx;
					border-radius: 100%;
					background-color: #FFFFFF;
				}
				.gap-top {
					top: -10upx;
				}
				.gap-bottom {
					bottom: -10upx;
				}
				.shixiao {
					position: absolute;
					right: 20upx;
					font-size: 150upx;
					z-index: 6;
					color: rgba(153, 153, 153, 0.2);
				}
			}
			.right {
				flex-shrink: 0;
				width: 28%;
				color: #fff;
				background: linear-gradient(to right, #ec625c, #ee827f);
				justify-content: center;
							text-align: center;
				.ticket,
				.criteria {
					width: 100%;
				}
				.ticket {
					padding-top: 1vw;
					justify-content: center;
					align-items: baseline;
					.num {
						font-size: 20px;
						font-weight: 600;
					}
					.unit {
						font-size: 12px;
					}
				}
				.criteria {
					justify-content: center;
					margin: 6px 0;
					font-size: 28upx;
				}
				.use {
					width: 60%;
					height: 20px;
					line-height: 20px;
					justify-content: center;
					align-items: center;
					font-size: 12px;
					background-color: #fff;
					color: #ee827f;
					border-radius: 40upx; 
					margin: auto;
				}
			}
		}
	}
}
</style>
