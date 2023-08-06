<template>
	<view class="content">
		<!-- 顶部banner -->
		<view class="topbar">
			<span>M2V Cloud</span>
			<view class="scan">
				<image class="scan-img" src="../../static/scan.svg"></image>
			</view>
		</view>
		<view class="swiper-contents">
			<span class="title">中创孵化器</span>
			<span class="desc">由中创孵化器资深科技团队为您提供专业
				孵化方案</span>
		</view>
		<swiper class="swiper" circular :indicator-dots="true" indicator-color="rgba(255, 255, 255, 0.7)"
			indicator-active-color="#fff" :autoplay="true" :interval="2000" :duration="500">
			<swiper-item class="swiper-items" v-for="item in swipers">
				<image class="swiper-items-img" :src="item"></image>
			</swiper-item>
		</swiper>

		<!-- 中部菜单 -->
		<view class="mid-bar">
			<view class="service" v-for="item in services">
				<image class="icon" :src="item.img" mode=""></image>
				<span>{{item.title}}</span>
				<image v-show="item.redPoint" class="red-point" src="../../static/redPoint.png" mode=""></image>
			</view>
		</view>

		<!-- 园区介绍 -->
		<view class="area-desc">
			<topbar title="园区介绍" url="nmsl"></topbar>
			<view class="park-list">
				<introduceItem v-for="item in parks" :img="item.img" :name="item.name" :desc="item.desc">
				</introduceItem>
			</view>
		</view>

		<!-- 精彩活动 -->
		<view class="activity">
			<topbar title="精彩活动" url="nmsl"></topbar>
			<view class="act-list">
				<activityItem v-for="item in activities" :img="item.img" :name="item.name" :address="item.address"
					:time="item.time" :showHot="item.showHot" :showPast="item.showPast" :enter="item.enter">
				</activityItem>
			</view>
		</view>

		<!-- 底部导航栏 -->
		<tabbar></tabbar>
	</view>
</template>

<script>
	import topbar from '../../components/topbar/topbar.vue'
	import introduceItem from '../../components/introduceItem/introduceItem.vue'
	import activityItem from '../../components/activityItem/activityItem.vue'

	export default {
		// 注册需要用到的组件
		components: {
			topbar,
			introduceItem,
			activityItem,
		},
		data() {
			return {
				swipers: [
					'../../static/banner.png',
					'../../static/banner1.png',
					'../../static/banner2.png',
				],
				services: [{
						title: '企业服务',
						img: '../../static/企业服务.svg',
						redPoint: false,
					},
					{
						title: '公共空间预约',
						img: '../../static/公共空间预约.svg',
						redPoint: false,
					},
					{
						title: '缴费大厅',
						img: '../../static/缴费大厅.svg',
						redPoint: true,
					},
					{
						title: '能耗查看',
						img: '../../static/能耗查看.svg',
						redPoint: false,
					},
				],
				parks: [{
						img: '../../static/park1.png',
						name: '启盛会展产业园',
						desc: '广东省广州市海珠区新港东路2433号',
					},
					{
						img: '../../static/park2.png',
						name: '启盛会展产业园',
						desc: '广东省广州市海珠区新港东路2433号',
					},
					{
						img: '../../static/park3.png',
						name: '米哈游',
						desc: '广东省广州市海珠区新港东路2433号',
					},
				],
				activities: [{
						img: '../../static/act0.png',
						name: 'CICF',
						address: '广州市海珠区新港东路2433号',
						time: '2023-08-25 10：00',
						showHot: false,
						showPast: false,
						enter: 1,
					},
					{
						img: '../../static/act0.png',
						name: '米哈游6周年生日会',
						address: '广州市海珠区新港东路2433号',
						time: '2023-07-25 10：00',
						showHot: true,
						showPast: false,
						enter: 1,
					},
					{
						img: '../../static/act1.png',
						name: '“区块链”分享会',
						address: '广州市海珠区新港东路2433号',
						time: '2023-07-25 10：00',
						showHot: true,
						showPast: false,
						enter: 1,
					},
					{
						img: '../../static/act2.png',
						name: '“元宇宙”交流会',
						address: '广州市黄埔区伴河路136号',
						time: '2023-07-20 10：00',
						showHot: false,
						showPast: true,
						enter: 0,
					},
					{
						img: '../../static/act3.png',
						name: '产学研联合讨论会',
						address: '广州市海珠区新港东路2433号',
						time: '2023-07-25 10：00',
						showHot: false,
						showPast: true,
						enter: 0,
					},
				]
			}
		},
		onLoad() {

		},
		methods: {

		},
	}
</script>

<style lang="scss" scoped>
	.content {
		display: flex;
		flex-direction: column;
		width: 100%;
		height: 100%;
		padding-bottom: 100upx;
		overflow-y: scroll;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}

	// 轮播图
	.swiper {
		width: 100%;
		height: 608upx !important;

		&-items {
			width: 100%;
			height: 608upx !important;

			&-img {
				width: 100%;
				height: 608upx !important;
			}
		}
	}

	// 顶部标题
	.topbar {
		width: 100%;
		box-sizing: border-box;
		position: fixed;
		top: 0;
		z-index: 99;
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 18upx 28upx 18upx 36upx;

		>span {
			color: rgba(16, 16, 16, 1);
			font-size: 46upx;
			font-family: Times New Roman-bold;
			font-weight: 600;
		}

		.scan {
			display: flex;
			padding: 12upx;
			opacity: 0.77;
			border-radius: 6upx;
			background-color: rgba(255, 255, 255, 1);

			&-img {
				width: 48upx;
				height: 48upx;
			}
		}
	}

	// 描述
	.swiper-contents {
		position: fixed;
		box-sizing: border-box;
		top: 140upx;
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		z-index: 99;
		padding: 60upx 36upx;

		.title {
			color: rgba(255, 255, 255, 1);
			font-size: 46upx;
			font-family: SourceHanSansSC-bold;
			font-weight: 600;
		}

		.desc {
			width: 80%;
			color: rgba(255, 255, 255, 1);
			font-size: 32upx;
			font-family: SourceHanSansSC-regular;
			margin-top: 30upx;
		}
	}

	// 中部菜单
	.mid-bar {
		display: flex;
		justify-content: space-around;
		padding: 46upx 0;

		.service {
			position: relative;
			display: flex;
			flex-direction: column;
			align-items: center;

			.icon {
				width: 58upx;
				height: 58upx;
			}

			.red-point {
				position: absolute;
				top: 0;
				right: 0;
				width: 20upx;
				height: 20upx;
				background: red;
				border-radius: 20upx;
			}

			>span {
				color: rgba(16, 16, 16, 1);
				font-size: 22upx;
				font-family: SourceHanSansSC-regular;
				margin-top: 20upx;
			}
		}
	}

	.area-desc {

		.park-list {
			display: flex;
			width: 100%;
			overflow-x: scroll;
			padding: 0 20upx;
		}
	}
</style>