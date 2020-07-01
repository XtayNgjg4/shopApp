<template>
	<view class="container">
		<view class="swiper">
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
		<view class="themeArea">
			<view class="themeItem">
				<view class="themeItem_pic">
					<image src="https://i1.ygimg.cn/pics/mobile/homepage/2019/05/1558418890257.jpg" mode="widthFix"></image>
				</view>
				<view class="themeItem_scroll">
					<scroll-view scroll-x="true">
						<view class="scrollView_con">
							<view class="newproItem" @tap="navToDetailPage">
								<image src="//i2.ygimg.cn/pics/adidasclassic/2019/101212062/101212062_01_mb.jpg?4"
								 mode="widthFix"></image>
								<view class="newproItem_con">
									<view class="newproItem_price">
										<view><text>￥</text><text>564</text></view>
									</view>
								</view>
							</view>
							<view class="newproItem" @tap="navToDetailPage">
								<image src="//i2.ygimg.cn/pics/adidasclassic/2019/101212062/101212062_01_mb.jpg?4"
								 mode="widthFix"></image>
								<view class="newproItem_con">
									<view class="newproItem_price">
										<view><text>￥</text><text>564</text></view>
									</view>
								</view>
							</view>
							<view class="newproItem" @tap="navToDetailPage">
								<image src="//i2.ygimg.cn/pics/adidasclassic/2019/101212062/101212062_01_mb.jpg?4"
								 mode="widthFix"></image>
								<view class="newproItem_con">
									<view class="newproItem_price">
										<view><text>￥</text><text>564</text></view>
									</view>
								</view>
							</view>
							<view class="newproItem" @tap="navToDetailPage">
								<image src="//i2.ygimg.cn/pics/adidasclassic/2019/101212062/101212062_01_mb.jpg?4"
								 mode="widthFix"></image>
								<view class="newproItem_con">
									<view class="newproItem_price">
										<view><text>￥</text><text>564</text></view>
									</view>
								</view>
							</view>
							<view class="newproItem" @tap="navToDetailPage">
								<image src="//i2.ygimg.cn/pics/adidasclassic/2019/101212062/101212062_01_mb.jpg?4"
								 mode="widthFix"></image>
								<view class="newproItem_con">
									<view class="newproItem_price">
										<view><text>￥</text><text>564</text></view>
									</view>
								</view>
							</view>
							<view class="newproItem" @tap="navToDetailPage">
								<image src="//i2.ygimg.cn/pics/adidasclassic/2019/101212062/101212062_01_mb.jpg?4"
								 mode="widthFix"></image>
								<view class="newproItem_con">
									<view class="newproItem_price">
										<view><text>￥</text><text>564</text></view>
									</view>
								</view>
							</view>
							<view class="newproItem" @tap="navToDetailPage">
								<image src="//i2.ygimg.cn/pics/adidasclassic/2019/101212062/101212062_01_mb.jpg?4"
								 mode=""></image>
								<view class="newproItem_con">
									<view class="newproItem_price">
										<view><text>￥</text><text>564</text></view>
									</view>
								</view>
							</view>
						</view>
					</scroll-view>
				</view>
			</view>
			<view class="themeItem">
				<view class="themeItem_pic">
					<image src="https://i1.ygimg.cn/pics/mobile/homepage/2019/05/1558418890257.jpg" mode="widthFix"></image>
				</view>
				<view class="themeItem_scroll">
					<scroll-view scroll-x="true">
						<view class="scrollView_con">
							<view class="newproItem" @tap="navToDetailPage">
								<image src="//i2.ygimg.cn/pics/adidasclassic/2019/101212062/101212062_01_mb.jpg?4"
								 mode=""></image>
								<view class="newproItem_con">
									<view class="newproItem_price">
										<view><text>￥</text><text>564</text></view>
									</view>
								</view>
							</view>
							<view class="newproItem" @tap="navToDetailPage">
								<image src="//i2.ygimg.cn/pics/adidasclassic/2019/101212062/101212062_01_mb.jpg?4"
								 mode=""></image>
								<view class="newproItem_con">
									<view class="newproItem_price">
										<view><text>￥</text><text>564</text></view>
									</view>
								</view>
							</view>
							<view class="newproItem" @tap="navToDetailPage">
								<image src="//i2.ygimg.cn/pics/adidasclassic/2019/101212062/101212062_01_mb.jpg?4"
								 mode=""></image>
								<view class="newproItem_con">
									<view class="newproItem_price">
										<view><text>￥</text><text>564</text></view>
									</view>
								</view>
							</view>
							<view class="newproItem" @tap="navToDetailPage">
								<image src="//i2.ygimg.cn/pics/adidasclassic/2019/101212062/101212062_01_mb.jpg?4"
								 mode=""></image>
								<view class="newproItem_con">
									<view class="newproItem_price">
										<view><text>￥</text><text>564</text></view>
									</view>
								</view>
							</view>
						</view>
					</scroll-view>
				</view>
			</view>
			<view class="themeItem">
				<view class="themeItem_pic">
					<image src="https://i1.ygimg.cn/pics/mobile/homepage/2019/05/1558418890257.jpg" mode="widthFix"></image>
				</view>
				<view class="themeItem_scroll">
					<scroll-view scroll-x="true">
						<view class="scrollView_con">
							<view class="newproItem" @tap="navToDetailPage">
								<image src="//i2.ygimg.cn/pics/adidasclassic/2019/101212062/101212062_01_mb.jpg?4"
								 mode=""></image>
								<view class="newproItem_con">
									<view class="newproItem_price">
										<view><text>￥</text><text>564</text></view>
									</view>
								</view>
							</view>
							<view class="newproItem" @tap="navToDetailPage">
								<image src="//i2.ygimg.cn/pics/adidasclassic/2019/101212062/101212062_01_mb.jpg?4"
								 mode=""></image>
								<view class="newproItem_con">
									<view class="newproItem_price">
										<view><text>￥</text><text>564</text></view>
									</view>
								</view>
							</view>
							<view class="newproItem" @tap="navToDetailPage">
								<image src="//i2.ygimg.cn/pics/adidasclassic/2019/101212062/101212062_01_mb.jpg?4"
								 mode=""></image>
								<view class="newproItem_con">
									<view class="newproItem_price">
										<view><text>￥</text><text>564</text></view>
									</view>
								</view>
							</view>
							<view class="newproItem" @tap="navToDetailPage">
								<image src="//i2.ygimg.cn/pics/adidasclassic/2019/101212062/101212062_01_mb.jpg?4"
								 mode=""></image>
								<view class="newproItem_con">
									<view class="newproItem_price">
										<view><text>￥</text><text>564</text></view>
									</view>
								</view>
							</view>
						</view>
					</scroll-view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
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
			}
		},
		onLoad() {
			this.animation = uni.createAnimation();
			this.animation.scale(this.zoomParam).step();
			this.animationData[0] = this.animation.export();
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
			}
		}
	}
</script>

<style lang="scss">
	.swiper-item {
		display: flex;
		align-items: center;
	}
	
	.swiper-item image {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		margin-left: auto;
		margin-right: auto;
		width: 92%;
		text-align: center;
		broder-radius: 10px;
	}
	.themeArea{
		width: 100%;
		margin-top: 15upx;
	}
	.themeItem{
		background-color: #ffffff;
		padding:15upx; 
		margin-bottom: 15upx;
		.themeItem_pic{
			image{
				width: 100%;
			}
		}
	}
	.themeItem_scroll{
		padding: 20upx;
	}
	.scrollView_con{
		 display: flex;
		  white-space: nowrap;
	}
	
	.newproItem_price{
		font-size: 32upx;
		color: red;
	}
	.newproItem{
		width: 200upx;
		margin-right: 30upx;
	}
	.newproItem image{
		width: 200upx;
		height: 200upx;
	}
</style>
