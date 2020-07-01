<template>
	<view class="container">
		<view class="mark" :class="markActive" @click.stop="hidden"></view>
		<view class="markView" :class="move">
			<scroll-view scroll-y="true" class="scroll-view" >
				<view class="selectbox">
					<view class="selectbox-title">
						价格
					</view>
					<view class="selectPrice">
						<view>价格区间</view> <input type="number"  placeholder="最低价" placeholder-style="text-align: center;"/>-<input type="number"  placeholder="最高价" placeholder-style="text-align: center;"/>
					</view>
				</view>
				<view class="selectbox">
					<view class="selectbox-title">
						价格
					</view>
					<view class="selectPrice">
						<view>价格区间</view> <input type="number"  placeholder="最低价" placeholder-style="text-align: center;"/>-<input type="number"  placeholder="最高价" placeholder-style="text-align: center;"/>
					</view>
				</view>
				<view class="selectbox">
					<view class="selectbox-title">
						价格
					</view>
					<view class="selectPrice">
						<view>价格区间</view> <input type="number"  placeholder="最低价" placeholder-style="text-align: center;"/>-<input type="number"  placeholder="最高价" placeholder-style="text-align: center;"/>
					</view>
				</view>
				<view class="selectbox">
					<view class="selectbox-title">
						价格
					</view>
					<view class="selectPrice">
						<view>价格区间</view> <input type="number"  placeholder="最低价" placeholder-style="text-align: center;"/>-<input type="number"  placeholder="最高价" placeholder-style="text-align: center;"/>
					</view>
				</view>
				<view class="selectbox">
					<view class="selectbox-title">
						价格
					</view>
					<view class="selectPrice">
						<view>价格区间</view> <input type="number"  placeholder="最低价" placeholder-style="text-align: center;"/>-<input type="number"  placeholder="最高价" placeholder-style="text-align: center;"/>
					</view>
				</view>
				<view class="selectbox">
					<view class="selectbox-title">
						价格
					</view>
					<view class="selectPrice">
						<view>价格区间</view> <input type="number"  placeholder="最低价" placeholder-style="text-align: center;"/>-<input type="number"  placeholder="最高价" placeholder-style="text-align: center;"/>
					</view>
				</view>
				<view class="selectbox">
					<view class="selectbox-title">
						价格
					</view>
					<view class="selectPrice">
						<view>价格区间</view> <input type="number"  placeholder="最低价" placeholder-style="text-align: center;"/>-<input type="number"  placeholder="最高价" placeholder-style="text-align: center;"/>
					</view>
				</view>
				<view class="selectbox">
					<view class="selectbox-title">
						价格
					</view>
					<view class="selectPrice">
						<view>价格区间</view> <input type="number"  placeholder="最低价" placeholder-style="text-align: center;"/>-<input type="number"  placeholder="最高价" placeholder-style="text-align: center;"/>
					</view>
				</view>
				<view class="selectbox">
					<view class="selectbox-title">
						价格
					</view>
					<view class="selectPrice">
						<view>价格区间</view> <input type="number"  placeholder="最低价" placeholder-style="text-align: center;"/>-<input type="number"  placeholder="最高价" placeholder-style="text-align: center;"/>
					</view>
				</view>
				<view class="selectbox">
					<view class="selectbox-title">
						价格
					</view>
					<view class="selectPrice">
						<view>价格区间</view> <input type="number"  placeholder="最低价" placeholder-style="text-align: center;"/>-<input type="number"  placeholder="最高价" placeholder-style="text-align: center;"/>
					</view>
				</view>
				
			</scroll-view>
			<view class="btns">
				<view>重置</view>
				<view :class="markActive" @click.stop="hidden">完成</view>
			</view>
		</view>
		
		<view class="topSearch">
			<view class="topSearchArea">
				<view class="topSearch_pic" @click="back()"><image src="../../static/images/back.png" mode="" class="back"></image></view>
				<view class="search">
					<image src="../../static/images/idxsearch.png" mode=""></image>
					<view class="searchTxt">搜索</view>
				</view>
			</view>
			
		</view>

		<view class="shopView">
			<view class="shopViewPic">
				<image src="https://h2.appsimg.com/a.appsimg.com/upload/brand/upcb/2019/09/12/71/ias_156827113975541_1135x545_85.jpg" mode="widthFix"></image>
				<view class="shopViewHead">
					<view class="shopViewHead_name">
						<image src="../../static/logo.png" mode=""></image>
						巴尔曼
					</view>
					<view class="goshop">进入品牌</view>
				</view>
			</view>
		</view>
			
			<view class="selectArea">
				<view class="selectBoxUp">
					<view class="selectBoxUp_item">综合</view>
					<view class="selectBoxUp_item">
						销量
					</view>
					<view class="selectBoxUp_item" @click="show">
						<image src="../../static/images/selectitem.png" class="selectitem"></image>
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
					<view class="shopItem_price">
						<text>￥998</text> <text class="shopItem_num">99人已付款</text> <text class="shopItem-location">上海</text>
					</view>
				</view>
			</view>
			<view class="shopList_item">
				<view class="shopItem_pic">
					<image src="//img10.360buyimg.com/mobilecms/s372x372_jfs/t1/42931/24/7760/369143/5d15875bEa68ec1fc/bac64cbe3492a16a.jpg!q70.dpg.webp" mode=""></image>
				</view>
				<view class="shopItem_con">
					<view class="shopItem_txt">耐克阿迪达斯耐克阿迪达斯安踏美特斯邦威亚瑟士耐克阿迪达斯安踏美特斯邦威亚瑟士安踏美特斯邦威亚瑟士</view>
					<view class="shopItem_price">
				
					<text>￥998</text> <text class="shopItem_num">99人已付款</text> <text class="shopItem-location">上海</text>
					</view>
				</view>
			</view>
			<view class="shopList_item">
				<view class="shopItem_pic">
					<image src="//img10.360buyimg.com/mobilecms/s372x372_jfs/t1/42931/24/7760/369143/5d15875bEa68ec1fc/bac64cbe3492a16a.jpg!q70.dpg.webp" mode=""></image>
				</view>
				<view class="shopItem_con">
					<view class="shopItem_txt">耐克阿迪达斯安踏美特斯邦威亚瑟士</view>
					<view class="shopItem_price">
					<text>￥998</text> <text class="shopItem_num">99人已付款</text> <text class="shopItem-location">上海</text>
					</view>
				</view>
			</view>
			<view class="shopList_item">
				<view class="shopItem_pic">
					<image src="//img10.360buyimg.com/mobilecms/s372x372_jfs/t1/42931/24/7760/369143/5d15875bEa68ec1fc/bac64cbe3492a16a.jpg!q70.dpg.webp" mode=""></image>
				</view>
				<view class="shopItem_con">
					<view class="shopItem_txt">耐克阿迪达斯安踏美特斯邦威亚瑟士</view>
					<view class="shopItem_price">
					<text>￥998</text> <text class="shopItem_num">99人已付款</text> <text class="shopItem-location">上海</text>
					</view>
				</view>
			</view>
			<view class="shopList_item">
				<view class="shopItem_pic">
					<image src="//img10.360buyimg.com/mobilecms/s372x372_jfs/t1/42931/24/7760/369143/5d15875bEa68ec1fc/bac64cbe3492a16a.jpg!q70.dpg.webp" mode=""></image>
				</view>
				<view class="shopItem_con">
					<view class="shopItem_txt">耐克阿迪达斯安踏美特斯邦威亚瑟士</view>
					<view class="shopItem_price">
					<text>￥998</text> <text class="shopItem_num">99人已付款</text> <text class="shopItem-location">上海</text>
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
	.scroll-view{
		height: 99%;
		width: 100%;
		.selectbox{
			padding: 6px 0;
			.selectbox-title{
				font-size: 16px;
			}
			.selectPrice{
				display: flex;
				font-size: 13px;
				padding: 20px 6px 8px;
				border-bottom: 1px solid #F5F5F5;
				view{
					width: 30%;
					text-align: center;
					line-height: 29px;
				}
				input{
					margin: 0 6px;
					background-color: #F5F5F5;
					color: #808080;
					text-align: center;
				}
			}
		}
		
	}
	.btns{
		position: fixed;
		bottom: 0;
		left: 0;
		height: 5%;
		display: flex;
		width: 100%;
		view{
			flex: 1;
			font-size: 13px;
			text-align: center;
			line-height: 37px;
			color: #FFFFFF;
			background-color: #1A191E;
		}
		&>view:last-child{
			background-color: #FEB405;
		}
	}
	
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
.goshop{
	width: 60px;
	height: 20px;
	background-color: #FEB405;
	color: #F8F8F8;
	border-radius: 50px;
	font-size: 12px;
	text-align: center;
	line-height: 20px;
	margin: auto;
}
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
	width: 80%;
	height: 100%;
	background-color: #ffffff;
	transform: translateX(-100%);
	transition: 0.6s;
	position: fixed;
	top: 0;
	left: 0;
	z-index: 9999;
	padding: 30px 10px;
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
		margin: 5px 0 15px 0;
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
	padding:0 10px;
	.shopList_item {
		width: 100%;
		padding: 10px 0;
		display:flex;
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
	margin-top: 10px;
	border: 1px solid #eeeeee;
	.shopViewHead {
		width: 70%;
		display: flex;
		position: absolute;
		left: 50%;
		bottom: 15px;
		transform: translateX(-50%);
		background: rgba(255,255,255,.6);
		padding: 10upx;
		font-size: 14px;
		.shopViewHead_name {
			flex: 1;
			image {
				width: 50px;
				height: 50px;
				margin-right: 15upx;
			}
		}
	}
	.shopViewPic {
		position:relative;
		image {
			width: 100%;
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
.back {
	width: 50upx;
	height: 50upx;
	margin-right: 15upx;
}
.topSearch {
	width: 100%;
	background-color: #ffffff;
	padding: 25px 0 0 0;
}
.search {
	background-color: #f5f5f5;
	border-radius: 200rpx;
	padding: 0 20rpx;
	font-size: 12px;
	height: 30px;
	line-height: 30px;
	color: #555555;
	border: 1px solid #ffffff;
	display: flex;
	width: 80%;
	image {
		width: 16px;
		height: 16px;
		margin: auto;
	}
	.searchTxt {
		width: 80%;
		margin: 0 10rpx;
		font-style: normal;
	}
}
</style>
