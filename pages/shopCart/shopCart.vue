<template>
	<view class="container">
		<view class="shopCarHead clearfix">
			<text class="fl">
				购物车共
				<text>{{ shopNum }}</text>
				件商品
			</text>
			<text class="fr">管理</text>
		</view>

		<view class="shopCarList">
			<view class="shopCarView">
				<scroll-view scroll-x="true" class="scrollView" v-for="(list, index) in shopList" :key="index" >
					<view class="shopCarView_con">
						<view class="shopCarView_txt">
							<checkbox value="" :checked="list.selected" @click="listSelected(index)" />
							<view class="storePic"><image :src="list.img" mode="widthFix"></image></view>
							<view class="storeSelectBox">
								<view class="storeSelectBox_txt">{{ list.title }}</view>
								<view class="storeSelectBox_data">
									<view></view>
									<view>码数：{{ list.spec }}</view>
								</view>
								<view class="storeSelectBox_price clearfix">
									<view class="shopPrice fl">
										<text>￥</text>
										<text>{{ list.price }}</text>
									</view>
									<view class="shopNumber fr">
										<view @tap.stop="sub(index)">-</view>
										<input type="number" v-model="list.number" @input="sum()" disabled />
										<view @tap.stop="add(index)">+</view>
									</view>
								</view>
							</view>
						</view>
						<view class="shopDel">删除</view>
					</view>
				</scroll-view>
			</view>
			<view class="noMore">没有更多了......</view>
		</view>
		<view class="sumBox">
			<view class="sumAll">
				<checkbox value="" :checked="allChecked" @tap="allCheckedFun" />
				<view>全选</view>
			</view>
			<view class="sumPrice">
				<view>
					<text>合计：</text>
					<text>￥{{ shopSum }}</text>
				</view>
			</view>
			<view class="sumbtn" @click="navPlaceOrderPage">
				去结算(
				<text>{{ total }}</text>
				)
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			shopNum: 0,
			shopSum: 0,
			total: 0,
			allChecked: false,
			shopList: [
				{
					id: 1,
					img: '//img10.360buyimg.com/mobilecms/s360x360_jfs/t16063/300/2604272150/140226/87f305a9/5ab481beNf4b97620.jpg!q70.dpg.webp',
					title: '萨克大萨达卡莎时空间的哈市空间的啊是爱啥啥抠脚大汉啥肯定会',
					spec: '36',
					price: 1,
					number: 1,
					selected: false
				},
				{
					id: 2,
					img: '//img10.360buyimg.com/mobilecms/s360x360_jfs/t16063/300/2604272150/140226/87f305a9/5ab481beNf4b97620.jpg!q70.dpg.webp',
					title: '萨克大萨达卡莎时空间的哈市空间的啊是爱啥啥抠脚大汉啥肯定会',
					spec: '36',
					price: 2,
					number: 1,
					selected: false
				},
				{
					id: 3,
					img: '//img10.360buyimg.com/mobilecms/s360x360_jfs/t16063/300/2604272150/140226/87f305a9/5ab481beNf4b97620.jpg!q70.dpg.webp',
					title: '萨克大萨达卡莎时空间的哈市空间的啊是爱啥啥抠脚大汉啥肯定会',
					spec: '36',
					price: 3,
					number: 1,
					selected: false
				},
				{
					id: 4,
					img: '//img10.360buyimg.com/mobilecms/s360x360_jfs/t16063/300/2604272150/140226/87f305a9/5ab481beNf4b97620.jpg!q70.dpg.webp',
					title: '萨克大萨达卡莎时空间的哈市空间的啊是爱啥啥抠脚大汉啥肯定会',
					spec: '36',
					price: 4,
					number: 1,
					selected: false
				}
			]
		};
	},
	onLoad() {
		this.shopNum = this.shopList.length;
	},
	methods: {
		listSelected(index) {
			this.shopList[index].selected = this.shopList[index].selected ? false : true;
			if (this.shopList[index].selected) {
				this.total = this.total + this.shopList[index].number;
			} else {
				this.total = this.total - this.shopList[index].number;
			}
			this.sum();

			var itemisChecked = [];
			for (let i = 0; i < this.shopList.length; i++) {
				if (this.shopList[i].selected) {
					itemisChecked.push(this.shopList[i]);
				}
			}
			if (itemisChecked.length === this.shopList.length) {
				this.allChecked = true;
			} else {
				this.allChecked = false;
			}
		},
		allCheckedFun(index) {
			this.allChecked = this.allChecked ? false : true;
			if (this.allChecked) {
				for (var i = 0; i < this.shopList.length; i++) {
					this.shopList[i].selected = true;
					this.total= this.total +this.shopList[i].number;
				}
			} else {
				for (var i = 0; i < this.shopList.length; i++) {
					this.shopList[i].selected = false;
					this.total = 0;
				}
			}
			this.sum();
		},
		sub(index) {
			if (this.shopList[index].number <= 1) return;
			this.shopList[index].number--;
			if (this.shopList[index].selected) {
				this.total--;
			} else {
				return;
			}
			this.sum();
		},
		add(index) {
			this.shopList[index].number++;
			if (this.shopList[index].selected) {
				this.total++;
			} else {
				return;
			}
			this.sum();
		},
		sum() {
			this.shopSum = 0;
			for (var i = 0; i < this.shopList.length; i++) {
				if (this.shopList[i].selected) {
					this.shopSum = this.shopSum + this.shopList[i].number * this.shopList[i].price;
				}
			}
		},
		navPlaceOrderPage() {
			uni.navigateTo({
				url: `/pages/order/placeOrder`
			});
		}
	}
};
</script>

<style lang="scss">
checkbox .wx-checkbox-input {
	border-radius: 50%;
	width: 20px;
	height: 20px;
}
checkbox .wx-checkbox-input.wx-checkbox-input-checked {
	background: #000000;
	color: #ffffff !important;
}
/* #ifdef H5 */
uni-checkbox .uni-checkbox-input {
	border-radius: 50% !important;
	width: 20px;
	height: 20px;
}
checkbox.uni-checkbox-input.uni-checkbox-input-checked {
	background: #000000;
	color: #ffffff !important;
}
/* #endif */

.noMore {
	width: 100%;
	text-align: center;
	font-size: 12px;
	margin-top: 20px;
}
.sumAll {
	margin-left: 10px;
	view {
		font-size: 12px;
		margin-top: 4px;
	}
}
.sumBox {
	position: fixed;
	bottom: 0;
	z-index: 95;
	display: flex;
	align-items: center;
	width: 100%;
	height: 50px;
	box-sizing: border-box;
	background: #ffffff;
	box-shadow: 0 0 20upx 0 rgba(0, 0, 0, 0.1);
	.sumPrice {
		flex: 0 0 45%;
		font-size: 28upx;
		color: red;
		text-align: right;
		margin: auto;
		view {
			font-size: 10px;
			text:last-child {
				font-size: 16px;
			}
		}
	}
	.sumbtn {
		width: 36%;
		padding: 0 38rpx;
		margin: 0;
		height: 100%;
		line-height: 50px;
		font-size: 14px;
		color: #ffffff;
		background: #000000;
		text-align: center;
		box-shadow: 1px 2px 5px rgba(0, 0, 0, 0.1);
	}
}
.shopNumber {
	color: #999999;
	display: flex;
	view {
		width: 45upx;
		height: 45upx;
		background-color: #f3f3f3;
		border-radius: 5upx;
		text-align: center;
		line-height: 45upx;
	}
	input {
		width: 45upx;
		height: 45upx;
		margin: 0 10rpx;
		line-height: 45upx;
		text-align: center;
		font-size: 14px;
	}
}

.storeSelectBox {
	flex: 0 0 60%;
	margin-left: 30upx;
	.storeSelectBox_txt {
		width: 100%;
		font-size: 24upx;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 2;
		overflow: hidden;
	}
	.storeSelectBox_data {
		display: flex;
		margin: 20upx 0;
		view {
			font-size: 20upx;
			color: #a7a7a7;
			padding: 6upx;
			text-align: center;
			background-color: #f3f3f3;
			border-radius: 15rpx;
			margin-right: 8upx;
		}
	}
	.storeSelectBox_price {
		.shopPrice {
			font-size: 28upx;
			color: red;
		}
	}
}

.scrollView {
	width: 750upx;
	padding: 30upx 0;
	.shopCarView_con {
		width: 900upx;
		display: flex;
		transition: all 0.2s ease-in 0s;
		.shopCarView_txt {
			width: 750upx;
			display: flex;
			.storePic {
				image {
					width: 22vw;
					height: 22vw;
				}
			}
			checkbox {
				line-height: 80px;
			}
		}
	}
	.shopDel {
		width: 150upx;
		background-color: #fd395b;
		color: #ffffff;
		text-align: center;
		display: flex;
		justify-content: center;
		align-items: center;
	}
}

.shopCarView {
	width: 100%;
	padding: 0 0 0 30upx;
	background: #ffffff;
}
.shopCarList {
	padding: 35px 0 80px 0;
}
.shopCarHead {
	width: 100%;
	height: 60upx;
	line-height: 60upx;
	text-align: center;
	position: fixed;
	top: 0;
	background-color: #ffffff;
	font-size: 24upx;
	padding: 0 30upx;
	z-index: 9;
	border-bottom: 1px solid #f2f4f6;
}
</style>
