<template>
	<view class="container">
		<view class="mark" :class="markActive" @click.stop="hidden"></view>
		<view class="markView" :class="move">
			<view class="">
				
			</view>
		</view>
		<image src="https://i1.ygimg.cn/pics/mobile/homepage/2019/09/1567505071910.jpg" mode="widthFix" class="assemblePic"></image>	
		<view class="topSearch">
			<view class="selectArea">
				<view class="selectBoxUp">
					<view class="selectBoxUp_item">综合</view>
					<view class="selectBoxUp_item">
						销量
						<image src="../../static/images/sxjt.png"></image>
					</view>
					<view class="selectBoxUp_item" @click="show">
						<image src="../../static/images/selectitem.png" class="selectitem"></image>
					</view>
				</view>
			</view>
		</view>

		<view class="shopListArea">
			<view class="shopList_item">
				<view class="shopItem_pic">
					<image src="//img10.360buyimg.com/mobilecms/s372x372_jfs/t1/42931/24/7760/369143/5d15875bEa68ec1fc/bac64cbe3492a16a.jpg!q70.dpg.webp" mode=""></image>
				</view>
				<view class="shopItem_con">
					<view class="shopItem_txt">耐克阿迪达斯安踏美特斯邦威亚瑟士耐克阿迪达斯安踏美特斯邦威亚瑟士耐克阿迪达斯安踏美特斯邦威亚瑟士</view>
					<view class="assembleNum">
						6人团
					</view>
					<view class="shopItem_price">
						<text>￥998</text> <text class="shopItem_num">已团99人</text> 
						<view class="goAssBtn">去拼团</view>
					</view>
				</view>
			</view>
			<view class="shopList_item">
				<view class="shopItem_pic">
					<image src="//img10.360buyimg.com/mobilecms/s372x372_jfs/t1/42931/24/7760/369143/5d15875bEa68ec1fc/bac64cbe3492a16a.jpg!q70.dpg.webp" mode=""></image>
				</view>
				<view class="shopItem_con">
					<view class="shopItem_txt">耐克阿迪达斯安踏美特斯邦威亚瑟士耐克阿迪达斯安踏美特斯邦威亚瑟士耐克阿迪达斯安踏美特斯邦威亚瑟士</view>
					<view class="assembleNum">
						6人团
					</view>
					<view class="shopItem_price">
						<text>￥998</text> <text class="shopItem_num">已团99人</text> 
						<view class="goAssBtn">去拼团</view>
					</view>
				</view>
			</view>
			<view class="shopList_item">
				<view class="shopItem_pic">
					<image src="//img10.360buyimg.com/mobilecms/s372x372_jfs/t1/42931/24/7760/369143/5d15875bEa68ec1fc/bac64cbe3492a16a.jpg!q70.dpg.webp" mode=""></image>
				</view>
				<view class="shopItem_con">
					<view class="shopItem_txt">耐克阿迪达斯安踏美特斯邦威亚瑟士耐克阿迪达斯安踏美特斯邦威亚瑟士耐克阿迪达斯安踏美特斯邦威亚瑟士</view>
					<view class="assembleNum">
						6人团
					</view>
					<view class="shopItem_price">
						<text>￥998</text> <text class="shopItem_num">已团99人</text> 
						<view class="goAssBtn">去拼团</view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			markActive: 'none',
			move:'',
		};
	},
	methods: {
		back() {
			uni.navigateBack({});
		},
		show() {
			this.markActive = 'markActive';
			this.move='move'
		},
		hidden() {
			this.markActive = 'hideActive';
			this.move='stop'
			setTimeout(() => {
				this.markActive = 'none';
			}, 300);
		}
	}
};
</script>

<style lang="scss">
	@keyframes moveActive {
		0% {
			transform: translateX(-100%);
		}
		100% {
			transform: translateX(0);
		}
	}
	@keyframes stopActive {
		0% {
			transform: translateX(0);
		}
		100% {
			transform: translateX(-100%);
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
.goAssBtn{
		width: 60px;
		height: 20px;
		text-align: center;
		line-height: 20px;
		font-size: 14px;
		color: #FFFFFF;
		background-color: #B81C22;
		margin: auto;
}
.assembleNum{
	width: 40px;
	height: 14px;
	border: 1px solid #FEB405;
	font-size: 10px;
	line-height: 12px;	
	text-align: center;
	color: #FEB405;
	margin: 10px 0;
}
.assemblePic{width: 100%;}
.shopItem_num{
	margin: 0 5px;
}
.shopItem_num,.shopItem-location{
	font-size: 10px;
	color: #000000;
	line-height: 24px;
}
.selectitem{
	width: 20px!important;
	height: 20px!important;
}
.markActive.mark {
	display: block;
	animation: showPopup 0.3s linear both;
}
.move.markView {
	animation: moveActive 0.3s linear both;
}
.stop.markView{
	animation: stopActive 0.3s linear both;
}
.hideActive.mark {
	animation: hidePopup 0.3s linear both;
}
.none.mark {
	display: none;
}
.mark {
	width: 100%;
	height: 100%;
	position: fixed;
	top: 0;
	left: 0;
	background-color: rgba(0, 0, 0, 0.6);
	opacity: 0;
	z-index: 999;
}
.markView {
	width: 70%;
	height: 100%;
	background-color: #ffffff;
	transform: translateX(-100%);
	transition: 0.6s;
	position: fixed;
	top: 0;
	left: 0;
	z-index: 9999;
}
.shopItem_con {
		margin-left: 5px;
		flex: 1;
	.shopItem_txt {
		font-size: 14px;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 2;
		text-align: justify;
		overflow: hidden;
		display: -webkit-box;
		margin-top: 5px;
	}
	.shopItem_price {
		display:flex;
		text:first-child{
			font-size: 18px;
			color: red;
			flex: 1;
		}
	}
}
.shopItem_pic {
	position: relative;
	image {
		width: 100px;
		height: 100px;
	}
}
.shopListArea {
	width: 100%;
	.shopList_item {
		width: 100%;
		padding: 10px 10px;
		display:flex;
		border-bottom: 1px solid #F1F1F1;
	}
}
.selectArea {
	width: 100%;

	.selectBoxUp {
		display: flex;
		padding: 10px 0;
		border-bottom: 1px solid #eeeeee;
		.selectBoxUp_item {
			width: 33.33%;
			font-size: 14px;
			text-align: center;
			image {
				width: 14px;
				height: 14px;
			}
		}
	}
	.selectBoxDown {
		display: flex;
		margin: 25upx 0;
		.selectBoxDown_item {
			width: 23%;
			font-size: 32upx;
			text-align: center;
			background-color: #f5f5f5;
			margin-left: 20upx;
			&:first-child {
				margin-left: 0;
			}
		}
	}
}
.shopView {
	width: 100%;
	margin: 105px 0 30upx 0;
	border: 1px solid #eeeeee;
	.shopViewHead {
		display: flex;
		padding: 10upx;
		font-size: 28upx;
		.shopViewHead_name {
			flex: 1;
			image {
				width: 38upx;
				height: 38upx;
				margin-right: 15upx;
			}
		}
	}
	.shopViewPic {
		image {
			width: 100%;
			height: 300upx;
		}
	}
}
.container {
	background-color: #ffffff;
}
.topSearchArea {
	padding: 0 20upx;
	width: 100%;
	display: flex;
}

.topSearch {
	width: 100%;
	background-color: #ffffff;
}

</style>
