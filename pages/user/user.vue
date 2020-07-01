<template>
	<view class="container">
		<view class="topBgColor bg-gradual-orange">
			<view class="headIconArea">
				<!-- <image src="../../static/images/idxmsg.png" class="msgBtn" @tap="navToMsgPage"></image> -->
				<view class="headIcon" @tap="navToUserSetPage">
					<image src="../../static/logo.png" mode=""></image>
				</view>
				<view class="headIcontxt">
					<view class="personalTitle">
						VIP会员
					</view>
					<view class="personalName">
						快乐的买家
					</view>
				</view>
			
			</view>
		</view>
		<view style="height: 200px;"></view>
		<view class="myOrderArea">
			<view class="myOrderTop clearfix" @tap="navToOrderPage">
				<text class="myOrdertitle fl">我的订单</text>
				<text class="myOrderMore fr">查看全部订单 <text class="icon icon-you"></text></text>
			</view>
			<view class="myOrderDown">
				<view class="myOrderCon" v-for="(row,index) in orderList" :key="index" @tap="toOrderList(index)">
					<view class="myOrderIcon">
						<image :src="row.icon"  mode=""></image>
					</view>
					<view class="myOrderTxt">
						{{row.text}}
					</view>
				</view>
			</view>
		</view>
		
		<view class="serviceArea">
			<view class="serviceItem" @tap="navToAdressPage">
				<view class="serviceItem_pic">
					<image src="../../static/images/userIcon/adress.png" mode=""></image>
				</view>
				<view class="serviceItem_name">
					收货地址
				</view>
			</view>
			<view class="serviceItem" @click="navToGetCouponPage">
				<view class="serviceItem_pic">
					<image src="../../static/images/userIcon/yhq.png" mode=""></image>
				</view>
				<view class="serviceItem_name">
					领券中心
				</view>
			</view>
			<view class="serviceItem" @tap="navToIntegralPage">
				<view class="serviceItem_pic">
					<image src="../../static/images/userIcon/jf.png" mode=""></image>
				</view>
				<view class="serviceItem_name">
					积分中心
				</view>
			</view>
			<view class="serviceItem" @tap="navToSettingPage">
				<view class="serviceItem_pic">
					<image src="../../static/images/userIcon/set.png" mode=""></image>
				</view>
				<view class="serviceItem_name">
					设置
				</view>
			</view>
			<view class="serviceItem">
				<view class="serviceItem_pic">
					<image src="../../static/images/userIcon/yhq.png" mode=""></image>
				</view>
				<view class="serviceItem_name" @tap="navToDetailPage">
					收藏夹
				</view>
			</view>
			<view class="serviceItem">
				<view class="serviceItem_pic">
					<image src="../../static/images/userIcon/yhq.png" mode=""></image>
				</view>
				<view class="serviceItem_name">
					店铺
				</view>
			</view>
			<view class="serviceItem"> 
				<view class="serviceItem_pic">
					<image src="../../static/images/userIcon/yhq.png" mode=""></image>
				</view>
				<view class="serviceItem_name" @tap="navToFootMarkPage">
					足迹
				</view>
			</view>
			<view class="serviceItem">
				<view class="serviceItem_pic">
					<image src="../../static/images/userIcon/yhq.png" mode=""></image>
				</view>
				<view class="serviceItem_name" @tap="navToCouponPage">
					优惠券
				</view>
			</view>
		
			
			
		</view>

		<view class="saleCenter">
			<view class="saleCenterTitle clearfix">
				<text class="myOrdertitle fl">分销中心</text>
				<text class="myOrderMore fr"> 详情 <text class="icon icon-you"></text></text>
			</view>
			<view class="saleCenterCon">
				<view class="saleCenter_pic">
					<image src="../../static/images/userIcon/fx.png" mode=""></image>
				</view>
				<view class="saleCenter_txt">
					成为分销员，分分钟赚得佣金
				</view>
			</view>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				orderList:[
					{text:'待付款',icon:"../../static/images/userIcon/dfk.png"},
					{text:'待发货',icon:"../../static/images/userIcon/dfh.png"},
					{text:'待收货',icon:"../../static/images/userIcon/dsh.png"},
					{text:'待评价',icon:"../../static/images/userIcon/dpj.png"},
					{text:'退款/售后',icon:"../../static/images/userIcon/tk.png"}
				],
			}
		},
		methods: {
			navToDetailPage() {
				uni.navigateTo({
					url: `/pages/collection/collection`
				})
			},
			navToOrderPage() {
				uni.navigateTo({
					url: `/pages/order/order`
				})
			},
			toOrderList(index){
				uni.setStorageSync('tbIndex',index);
				uni.navigateTo({url:`../order/order?tbIndex=`+index})  
			},
			navToSettingPage() {
				uni.navigateTo({
					url: `/pages/setting/setting`
				})
			},
			navToAdressPage() {
				uni.navigateTo({
					url: `/pages/adress/adress`
				})
			},
			navToMsgPage() {
					uni.navigateTo({
						url: `/pages/msg/msg`
				})
			},
			navToUserSetPage() {
					uni.navigateTo({
						url: `/pages/setting/userSet`
				})
			},
			navToCouponPage() {
					uni.navigateTo({
						url: `/pages/Coupon/Coupon`
				})
			},
			navToFootMarkPage(){
				uni.navigateTo({
						url: `/pages/footmark/footmark`
				})
			},
			navToIntegralPage(){
				uni.navigateTo({
						url: `/pages/integral/integral`
				})
			},
			navToGetCouponPage(){
				uni.navigateTo({
						url: `/pages/Coupon/getCoupon`
				})
			}
		}
	}
</script>

<style lang="scss">
	$con-flex:flex;
	$con-width:100%;
	.saleCenter_txt{
		font-size: 24upx;
		color: #cccccc;
		text-align: center;
	}
	.saleCenter_pic{
		width: 100%;
		text-align: center;
		margin: 30upx 0;
		image{
			width: 80px;
			height: 80px;
		}
	}
.serviceItem_pic image{
	width: 60upx;
	height: 60upx;
	margin-bottom: 10upx;
}
.serviceItem:nth-of-type(3n){
	border-right: 0!important;
}
.serviceArea{
	width: $con-width;
	display: flex;
	flex-wrap: wrap;
	margin:10px auto;
	background-color: #ffffff;
	text-align: center;

	.serviceItem{
		flex: 0 0 33%;
		border-bottom: 1px solid #f0f0f0;
		border-right: 1px solid #f0f0f0;
		padding: 40upx 0;
		.serviceItem_name{
			font-size: 28upx;
		}
	}
	

}
.saleCenter{
	width: $con-width;
	background-color: #ffffff;
	margin:0 auto 30upx auto;
	padding: 15upx;
	box-sizing: border-box;
	.saleCenterTitle{
		font-size: 30upx;
		font-weight: 600;
		padding: 10upx 0;
		border-bottom: 1px solid #f0f0f0; 
		.myOrderMore{
			font-size: 24upx;
			font-weight: 100;
		}
	}
}
.myOrderArea{
	width: $con-width;
	background-color: #ffffff;
	padding: 6px;
	box-sizing: border-box;
	.myOrderTop{
		font-size: 30upx;
		font-weight: 600;
		padding: 10upx 0;
		border-bottom: 1px solid #f0f0f0; 
		.myOrderMore{
			font-size: 24upx;
			font-weight: 100;
		}
	}
	.myOrderDown{
		display: flex;
		text-align: center;
		.myOrderCon{
			flex: 0 0 20%;
			font-size: 24upx;
			margin: 15upx 0;
		}
	}
}
.myOrderCon image{
	width: 50upx;
	height: 50upx;
	margin-bottom: 10upx;
}

.topBgColor{
	background: linear-gradient(to bottom, #FEB405,#FFC63A);
	width: 100%;
	height: 200px;
	position: fixed;
	top: 0;
	z-index: 99;
}
.headIconArea{
	width: $con-width;
	margin:120upx  auto 0 auto;
	text-align: center;
	position: relative;
	.headIcon{
		flex: 0 0 10%;
		image{
			width: 60px;
			height: 60px;
			border-radius: 100%;
		}
	}
	.headIcontxt{
		flex: 0 0 60%;
		color: #ffffff;
		.personalName{
			font-size: 16px;
			margin: 10upx 0;
			color: #323232;
		}
		.personalTitle{
			width: 50px;
			padding: 2upx;
			font-size: 20upx;
			background-color: rgba(0,0,0,.3);
			border-radius: 200upx;
			text-align: center;
			margin: 10px auto;
		}
	}
}
.headIconArea>image{
		width: 50upx;
		height: 50upx;
		position: absolute;
		top: 50%;
		transform: translateY(-50%);
		right: 20upx;
}
.headIconArea>.setBtn{
	right: 100upx;
}

</style>
