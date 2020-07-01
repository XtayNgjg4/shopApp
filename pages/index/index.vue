<template>
	<view class="container">
		
		<view class="topbar fixed" >
			<view class="topbarView">
				<view class="top-position">
					<view class="icon icon-dizhi"></view>
					<text>{{address}}</text> 
				</view>

				<view class="searchView">
					<view class="search" @tap="navToSearchPage">
						<image src="../../static/images/idxsearch.png" type="search" mode=""></image>
						<view class="searchTxt">请输入关键字</view>
					</view>
				</view>
				<view class="icon icon-saomiao"></view>
			</view>
		</view>
		
		<view class="swiperBox">
			<swiper class="swiper" :style="{ height: swiperHeight + 'px' }" :indicator-dots="true" :autoplay="true" :interval="3000" :duration="500" :circular="true">
				<swiper-item class="swiperItem">
					<image
						src="https://i1.ygimg.cn/pics/mobile/homepage/2019/09/1568008974410.jpg"
						mode="widthFix"
						id="swiper-pic"
					></image>
				</swiper-item>
				<swiper-item class="swiperItem">
					<image
						src="https://i1.ygimg.cn/pics/mobile/homepage/2019/09/1568707085642.jpg"
						mode="widthFix"
					></image>
				</swiper-item>
				<swiper-item class="swiperItem">
					<image
						src="https://i1.ygimg.cn/pics/mobile/homepage/2019/09/1568008969382.jpg"
						mode="widthFix"
					></image>
				</swiper-item>
			</swiper>
		</view>
		<view class="contentArea idxNav">
			<view class="hotNavView">
				<view class="hotNavItem" @click="navToActivePage">
					<image src="../../static/images/hd.png" mode=""></image>
					<view class="hotNavItem_txt">精选活动</view>
				</view>
				<view class="hotNavItem" @click="navToThemePage">
					<image src="../../static/images/rm.png" mode=""></image>
					<view class="hotNavItem_txt ">热卖专区</view>
				</view>
				<view class="hotNavItem" @click="navDiscountPage">
					<image src="../../static/images/xsyh.png" mode=""></image>
					<view class="hotNavItem_txt">特惠</view>
				</view>
				<view class="hotNavItem" @click="navToThemePage">
					<image src="../../static/images/rm.png" mode=""></image>
					<view class="hotNavItem_txt ">领劵</view>
				</view>
			</view>
		</view>
		
		<view class="contentArea">
			<view class="idxActivePic">
				<image src="../../static/images/indexpic/idxpic1.png" mode="widthFix"></image>
				<image src="../../static/images/indexpic/idxpic2.png" mode="widthFix" @click="navAssemblePage"></image>
				<image src="../../static/images/indexpic/idxpic3.png" mode="widthFix"></image>
			</view>
		</view>
		
		<view class="cardSwiper">
			<swiper  :duration="1000" class="swiper-container" previous-margin="50px"
		 next-margin="50px" :circular="true" @change="change" :current="swiperCurrentIndex">
				<swiper-item class="swiper-item" v-for="(item,index) in picItem" :key="index" :item-id="index.toString()">
					<image
						:src="item.src"
						mode="widthFix"
						:animation="animationData[index]"
					></image>
				</swiper-item>
			</swiper>
		</view>
		
		<view class="contentArea">
			<view class="brandTxt" @click="navBuyPage"><image src="../../static/images/mao_title.jpg" mode="widthFix"></image></view>
			<view class="brandPic"><image src="//h2.appsimg.com/b.appsimg.com/upload/mst/2019/09/04/39/6c2fa251d275384d17dd54c8f9d81bd1.jpg!75.webp" mode="widthFix"></image></view>
			<view class="contentView disArea">
				<view class="disView" @tap="navToShopListPage">
					<view class="disIteUp">
						<view class="disItemUp_pic">
							<image
								src="https://h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/105933/2019/0801/199/00f173d5-e504-4982-b2af-b92f5071f33c.jpg"
								mode=""
							></image>
						</view>
						<view class="disItem-box">
							<view class="disItem_title">阿迪达斯阿迪达斯阿迪达斯</view>
							<view class="disItem-price">低至一折起</view>
						</view>
					</view>
					<view class="disIteUp">
						<view class="disItemUp_pic">
							<image src="https://h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcimg/2019/08/14/183/286547521565765512955.jpg" mode=""></image>
						</view>
						<view class="disItem-box">
							<view class="disItem_title">阿迪达斯</view>
							<view class="disItem-price">限时8.8折</view>
						</view>
					</view>
					<view class="disIteUp">
						<view class="disItemUp_pic">
							<image
								src="https://h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/600529/2019/0806/107/de77928c-dc57-4caf-944c-2c2607bd3568.jpg"
								mode=""
							></image>
						</view>
						<view class="disItem-box">
							<view class="disItem_title">阿迪达斯</view>
							<view class="disItem-price">今日6.8折</view>
						</view>
					</view>
					<view class="disIteUp">
						<view class="disItemUp_pic">
							<image
								src="https://h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/600529/2019/0806/107/de77928c-dc57-4caf-944c-2c2607bd3568.jpg"
								mode=""
							></image>
						</view>
						<view class="disItem-box">
							<view class="disItem_title">阿迪达斯</view>
							<view class="disItem-price">限时8.8折</view>
						</view>
					</view>
					<view class="disIteUp">
						<view class="disItemUp_pic">
							<image
								src="https://h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/600529/2019/0806/107/de77928c-dc57-4caf-944c-2c2607bd3568.jpg"
								mode=""
							></image>
						</view>
						<view class="disItem-box">
							<view class="disItem_title">阿迪达斯</view>
							<view class="disItem-price">限时8.8折</view>
						</view>
					</view>
					<view class="disIteUp">
						<view class="disItemUp_pic"><image src="http://img60.ddimg.cn/upload_img/00670/qd/dttttt4tt-1562905886.jpg" mode=""></image></view>
						<view class="disItem-box">
							<view class="disItem_title">阿迪达斯</view>
							<view class="disItem-price">限时8.8折</view>
						</view>
					</view>
					<view class="disIteUp">
						<view class="disItemUp_pic"><image src="http://img60.ddimg.cn/upload_img/00670/qd/dttttt4tt-1562905886.jpg" mode=""></image></view>
						<view class="disItem-box">
							<view class="disItem_title">阿迪达斯</view>
							<view class="disItem-price">限时8.8折</view>
						</view>
					</view>
				</view>
			</view>
		</view>

		<view class="contentArea">
			<view class="brandTxt" @click="navNewProPage"><image src="../../static/images/indexpic/buyPic.jpg" mode="widthFix" ></image></view>
			<image src="../../static/images/indexpic/idxbn2.jpg" mode="widthFix" class="idxfullpic"></image>
			<view class="scrollbox">
				<scroll-view class="scrollView" scroll-x="true">
					<view class="scrollView_con">
						<view class="newproItem" @tap="navToVideoPage">
							<view class="newproItem-pic">
								<image
									src="https://h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2019/08/30/140/9bdeb8f2-9af7-4069-a246-421ef2470cba_202x202_100.jpg!75.webp"
									mode="widthFix"
								></image>
								<view class="video-btn">
									<image src="../../static/images/vbtn.png" mode="" class="vbtn-img"></image>
									<text>868</text>
								</view>
							</view>
							<view class="newproItem_con">
								<view class="newproItem_txt">九阳豆浆机可是东方航空技术的回复怂得</view>
								<view class="newproItem_price">
									<view>
										<text>￥</text>
										<text>564</text>
									</view>
								</view>
							</view>
						</view>
						<view class="newproItem" @tap="navToVideoPage">
							<view class="newproItem-pic">
								<image
									mode="widthFix"
									src="https://h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvop/00605481/10028114/772301638-174872700567748608-174872700567748610-1_202x202_100.jpg!75.webp"
								></image>
								<view class="video-btn">
									<image src="../../static/images/vbtn.png" mode="" class="vbtn-img"></image>
									<text>868</text>
								</view>
							</view>

							<view class="newproItem_con">
								<view class="newproItem_txt">九阳豆浆机可是东方航空技术的回复怂得</view>
								<view class="newproItem_price">
									<view>
										<text>￥</text>
										<text>564</text>
									</view>
								</view>
							</view>
						</view>
						<view class="newproItem" @tap="navToVideoPage">
							<view class="newproItem-pic">
								<image
									mode="widthFix"
									src="https://h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2019/04/25/67/7e443011-34f7-4312-8c42-abb361323456_202x202_100.jpg!75.webp"
								></image>
								<view class="video-btn">
									<image src="../../static/images/vbtn.png" mode="" class="vbtn-img"></image>
									<text>868</text>
								</view>
							</view>
						
							<view class="newproItem_con">
								<view class="newproItem_txt">九阳豆浆机可是东方航空技术的回复怂得</view>
								<view class="newproItem_price">
									<view>
										<text>￥</text>
										<text>564</text>
									</view>
								</view>
							</view>
						</view>
						<view class="newproItem" @tap="navToVideoPage">
							<view class="newproItem-pic">
								<image
									mode="widthFix"
									src="https://h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvop/00605481/10028114/772301638-174872700567748608-174872700567748610-1_202x202_100.jpg!75.webp"
								></image>
								<view class="video-btn">
									<image src="../../static/images/vbtn.png" mode="" class="vbtn-img"></image>
									<text>868</text>
								</view>
							</view>
						
							<view class="newproItem_con">
								<view class="newproItem_txt">九阳豆浆机可是东方航空技术的回复怂得</view>
								<view class="newproItem_price">
									<view>
										<text>￥</text>
										<text>564</text>
									</view>
								</view>
							</view>
						</view>
						<view class="newproItem" @tap="navToVideoPage">
							<view class="newproItem-pic">
								<image
									mode="widthFix"
									src="https://h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvop/00605481/10028114/772301638-174872700567748608-174872700567748610-1_202x202_100.jpg!75.webp"
								></image>
								<view class="video-btn">
									<image src="../../static/images/vbtn.png" mode="" class="vbtn-img"></image>
									<text>868</text>
								</view>
							</view>
						
							<view class="newproItem_con">
								<view class="newproItem_txt">九阳豆浆机可是东方航空技术的回复怂得</view>
								<view class="newproItem_price">
									<view>
										<text>￥</text>
										<text>564</text>
									</view>
								</view>
							</view>
						</view>
					</view>
				</scroll-view>
			</view>
		</view>
		<view class="contentArea">
			<view class="msTop">
				<view class="msTop_pic"><image src="/static/images/indexpic/ms.png" mode=""></image></view>
				<view class="msToptxt">
					距离结束
					<text>12</text>
					时
					<text>12</text>
					分
					<text>12</text>
					秒
				</view>
				<view class="msTopMore" @click="navToMsPage">
					更多
					<text class="icon icon-you"></text>
				</view>
			</view>
			<view class="msView">
				<view class="msItem" @tap="navToDetailPage">
					<view class="msItem_pic">
						<image src="//img14.360buyimg.com/mobilecms/s372x372_jfs/t1/61318/25/3170/87318/5d15d4cfE1817e110/61fdf78101f9aeac.jpg!q70.dpg.webp" mode=""></image>
					</view>
					<view class="msItem_con">
						<view class="msItemCon_txt">折叠蒸汽多功能家用电磁炉</view>
						 <view class="progress-box">
						    <progress percent="20" active="true" activeColor="#b81c22" stroke-width="6" /><text>已抢20%</text>
						 </view>
						<view class="msItem_pricebox">
							<view class="msPrice">
								<view class="msPrice_txt"><text>￥800</text></view>
								<view class="msPrice_distxt"><text>￥800</text></view>
							</view>
							<view class="msPrice_right"><view class="msPrice_btn">马上抢</view></view>
							<view class=""></view>
						</view>
					</view>
				</view>
				<view class="msItem" @tap="navToDetailPage">
					<view class="msItem_pic">
						<image src="//img12.360buyimg.com/mobilecms/s372x372_jfs/t1/47223/4/6410/278901/5d410aeeEb4ab2b44/231f47fd42d9db81.jpg!q70.dpg.webp" mode=""></image>
					</view>
					<view class="msItem_con">
						<view class="msItemCon_txt">折叠蒸汽多功能家用电磁炉</view>
						<view class="progress-box">
						   <progress percent="20" active="true" activeColor="#b81c22" stroke-width="6" /><text>已抢20%</text>
						</view>
						<view class="msItem_pricebox">
							<view class="msPrice">
								<view class="msPrice_txt">
									<text>￥</text>
									<text>800</text>
								</view>
								<view class="msPrice_distxt">
									<text>￥</text>
									<text>800</text>
								</view>
							</view>
							<view class="msPrice_right">
								<view class="msPrice_btn">马上抢</view>
								<view class=""></view>
							</view>
						</view>
					</view>
				</view>
			</view> 
		</view>

		<view class="shopItemArea">
			<view class="likeTxt"><image src="../../static/images/indexpic/gus.jpg" mode="widthFix"></image></view>
			<view class="shopItem" v-for="(sItem,index) in shopItem" :key="index" @tap="navToDetailPage">
				<view class="shopItemView">
					<view class="shopItem_pic">
						<image :src="sItem.pic" mode="widthFix"></image>
						<view class="shopItem_brand">{{sItem.brand}}</view>
					</view>
					<view class="shopItem_con">
						<view class="shopItem_txt">{{sItem.txt}}</view>
						<view class="shopItem_price">
							<text>￥{{sItem.price}}</text>
						</view>
					</view>
				</view>
			</view>
			<mix-load-more :status="loadMoreStatus"></mix-load-more>
		</view>
	</view>
</template>

<script>
var _this=[];
import amap from '@/components/SDK/amap-wx.js';
import mixLoadMore from '@/components/mix-load-more/mix-load-more';
export default {
	components:{
		mixLoadMore
	},
	data() {
		return {
			swiperHeight:"",
			scrolly:"",
			shopItem:[
				{id:1,pic:"//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2018/06/08/38/f31b8d08-0d4c-4e17-abd9-4e990225696e_5t_218x274_70.jpg",brand:"亚瑟士",txt:"XTEP 革面简约 国潮女板鞋",price:998},
				{id:2,pic:"//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2018/12/10/152/c82c2064-0b2b-4bec-96cc-84db68f0e1db_5t_218x274_70.jpg",brand:"亚瑟士",txt:"XTEP 革面简约 国潮男板鞋",price:998},
				{id:3,pic:"//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2018/11/13/124/dbb7e9a2-9936-4126-9af2-44f8f745be12_5t_218x274_70.jpg",brand:"亚瑟士",txt:"XTEP 革面简约 国潮女板鞋国潮女板鞋",price:998},
				{id:4,pic:"//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2018/09/28/153/e52e6746-1772-4ed7-9936-b2fdf871113e_5t_218x274_70.jpg",brand:"亚瑟士",txt:"XTEP 革面简约 国潮女板鞋国潮女板鞋国潮女板鞋",price:998},
			],
			addList:[
				{id:5,pic:"//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2018/07/11/80/da2b8c53-2816-4f3d-96f5-cb87d525ac11_420_531_218x274_70.jpg",brand:"亚瑟士",txt:"XTEP 革面简约 国潮女板鞋",price:998},
				{id:6,pic:"//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2019/08/12/189/c82f1233-d07a-4218-98dd-4b0f57b77055_420_531_218x274_70.jpg",brand:"亚瑟士",txt:"XTEP 革面简约 国潮女板鞋",price:998},
				{id:7,pic:"//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2019/01/16/124/3340da16-c231-47c1-a386-4ffc263f2524_5t_218x274_70.jpg",brand:"亚瑟士",txt:"XTEP 革面简约 国潮女板鞋",price:998},
				{id:8,pic:"//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2019/08/12/182/8826e395-c0a7-4041-b93e-bbfcd08bc6ac_420_531_218x274_70.jpg",brand:"亚瑟士",txt:"XTEP 革面简约 国潮女板鞋",price:998},
				{id:9,pic:"//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2019/08/28/21/41d6db79-05a0-48cb-8a3c-f8cfce21a289_420_531_218x274_70.jpg",brand:"亚瑟士",txt:"XTEP 革面简约 国潮女板鞋",price:998},
				{id:10,pic:"//h2.appsimg.com/a.appsimg.com/upload/merchandise/pdcvis/2018/10/16/193/cc737af7-8180-4012-aad4-7c894e16484e_420_531_218x274_70.jpg",brand:"亚瑟士",txt:"XTEP 革面简约 国潮女板鞋",price:998},
			],
			address:'北京',
			loadMoreStatus: 0,
			animationData: {
				0:{},
				1:{},
				2:{}
			},
			title: "0",
			swiperCurrentIndex: 0,
			zoomParam: 1.10,
			picItem:[
				{id:1,src:"//m.360buyimg.com/mobilecms/s700x280_jfs/t1/69851/15/9720/146469/5d75e658Ecf8ffa76/cb2c36cb3b86ff9e.jpg!cr_1125x445_0_171!q70.jpg.dpg"},
				{id:2,src:"//m.360buyimg.com/mobilecms/s700x280_jfs/t1/66664/10/11120/198164/5d8abd6fE02831e96/8683ed135d1e096f.jpg!cr_1125x445_0_171!q70.jpg.dpg"},
				{id:3,src:"//m.360buyimg.com/mobilecms/s700x280_jfs/t1/29602/28/6448/147417/5c5018e1Ed6bdfbfe/44777b12d731ad4b.jpg!cr_1125x445_0_171!q70.jpg.dpg"}
			],
		};
	},
	onLoad() {
		// this.loadData('add');
		this.amapPlugin = new amap.AMapWX({
			//高德地图KEY，随时失效，请务必替换为自己的KEY，参考：http://ask.dcloud.net.cn/article/35070
			key: '7c235a9ac4e25e482614c6b8eac6fd8e'
		});
		//定位地址
		this.amapPlugin.getRegeo({
			success: data => {
				this.address = data[0].regeocodeData.addressComponent.city.replace(/市/g, ''); 
			}
		});
		this.animation = uni.createAnimation();
		this.animation.scale(this.zoomParam).step();
		this.animationData[0] = this.animation.export();
	},
	onReachBottom(){
		//上滑加载
		this.loadData('add');
	},
	beforeCreate: function() {
		_this = this;
	},
	mounted: function() {
		this.$nextTick(function() {
			let query = uni.createSelectorQuery().select('#swiper-pic');
			query.boundingClientRect(function(data) {
					_this.swiperHeight = data.height;
				})
				.exec();
		});
	},
	methods: {
		change(e) {
			this.swiperCurrentIndex = e.detail.current;
			this.title = e.detail.currentItemId;
			for (let key in this.animationData) {
				if (e.detail.currentItemId == key) {
					this.animation.scale(this.zoomParam).step();
					this.animationData[key] = this.animation.export();
				} else {
					this.animation.scale(1.0).step();
					this.animationData[key] = this.animation.export();
				}
			}
		},
		loadData(type){
			if(type === 'add'){
				this.loadMoreStatus = 1;
			}
			setTimeout(()=>{
				if(type === 'refresh'){
					this.shopItem = [];
				}
				
				let length = this.addList.length;
				for(let i=0; i< length; i++){
					this.shopItem.push(this.addList[i]);
				}
				
				if(type === 'add'){
					this.loadMoreStatus = 0;
				}
				if(type === 'refresh'){
					this.$refs.mixPulldownRefresh && this.$refs.mixPulldownRefresh.endPulldownRefresh();
				}
			}, 1000)
			
		},
		navToDetailPage() {
			uni.navigateTo({
				url: `/pages/shopDetails/shopDetails`
			});
		},
		navToSearchPage() {
			uni.navigateTo({
				url: `/pages/search/search`
			});
		},
		navToMsgPage() {
			uni.navigateTo({
				url: `/pages/msg/msg`
			});
		},
		navToShopListPage() {
			uni.navigateTo({
				url: `/pages/shopList/shopList`
			});
		},
		navToMsPage() {
			uni.navigateTo({
				url: `/pages/index/ms`
			});
		},
		navToThemePage() {
			uni.navigateTo({
				url: `/pages/index/theme`
			});
		},
		navToVideoPage() {
			uni.navigateTo({
				url: `/pages/video/video`
			});
		},
		navToActivePage() {
			uni.navigateTo({
				url: `/pages/active/active`
			});
		},
		navDiscountPage() {
			uni.navigateTo({
				url: `/pages/Discount/Discount`
			});
		},
		navAssemblePage(){
			uni.navigateTo({
				url: `/pages/assemble/assemble`
			});
		},
		navBuyPage(){
			uni.navigateTo({
				url: `/pages/buy/buy`
			});
		},
		navNewProPage(){
			uni.navigateTo({
				url: `/pages/newPro/newPro`
			});
		}
	},
	// onPageScroll:function(e){
	// 	if(e.scrollTop>1){
	// 		this.scrolly="fixed";
	// 	}else{
	// 		this.scrolly=""
	// 	}
	// }
};
</script>

<style>
@import url('../../components/colorui/main.css');
@import url('../../static/css/index.css');
	.cardSwiper .swiper-item {
		display: flex;
		align-items: center;
	}

	.cardSwiper .swiper-item image {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		margin-left: auto;
		margin-right: auto;
		width: 92%;
		text-align: center;
		broder-radius: 10px;
		margin-bottom: 8px;
	}
</style>
