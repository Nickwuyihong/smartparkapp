<template>
	<view class="activity-item">
		<image class="item-img" :src="img" mode=""></image>
		<view class="right">
			<view v-if="showHot" class="hot">
				<image class="icon" src="../../static/hot.png" mode=""></image>
				<span>火热报名</span>
			</view>
			<view v-if="showPast" class="hot">
				<image class="icon" src="../../static/hot2.png" mode=""></image>
				<span style="color: #9A9A9A;">往期活动</span>
			</view>
			<span class="name">{{name}}</span>
			<span class="addr">{{address}}</span>
			<span class="time">{{time}}</span>
			<view class="enter" :style="getEnterStyle()">{{enter === 2 ? '已报名' : '报名'}}</view>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			img: '',
			name: '',
			address: '',
			time: '',
			// 显示火热报名
			showHot: false,
			// 显示往期活动
			showPast: false,
			// 0： 不可报名， 1：可报名， 2：已报名
			enter: 0,
		},
		name:"activityItem",
		data() {
			return {
				
			};
		},
		methods: {
			// 获取报名样式
			getEnterStyle() {
				if (this.enter === 0) return {color: 'rgba(154, 154, 154, 1)', backgroundColor: 'rgba(206, 206, 206, 0.15)'}
				if (this.enter === 1) return {color: 'rgba(15, 64, 245, 1)', backgroundColor: 'rgba(15, 64, 245, 0.15)'}
				return {color: '#23C343', backgroundColor: '#E8FFE9'}
			}
		},
	}
</script>

<style lang="scss" scoped>
	.activity-item {
		display: flex;
		padding: 10upx;
		
		.item-img {
			width: 376upx;
			height: 264upx;
			border-radius: 20upx;
		}
		
		.right {
			width: 45%;
			display: flex;
			flex-direction: column;
			position: relative;
			padding-left: 18upx ;
			
			.hot {
				display: flex;
				margin-bottom: 10upx;
				
				.icon {
					width: 30upx;
					height: 30upx;
				}
				
				> span {
					color: rgba(233, 157, 66, 1);
					font-size: 24upx;
				}
			}
			
			.name {
				color: rgba(16, 16, 16, 1);
				font-size: 26upx;
				font-family: SourceHanSansSC-medium;
				font-weight: 600;
				margin-bottom: 10upx;
			}
			
			.addr {
				color: rgba(16, 16, 16, 1);
				font-size: 22upx;
				font-family: SourceHanSansSC-light;
				margin-bottom: 10upx;
			}
			
			.time {
				color: rgba(154, 154, 154, 1);
				font-size: 22upx;
				font-family: SourceHanSansSC-light;
			}
			
			.enter {
				width: fit-content;
				padding: 8upx 24upx;
				border-radius: 3px 3px 3px 3px;
				font-size: 24upx;
				font-family: SourceHanSansSC-regular;
				position: absolute;
				right: 20upx;
				bottom: 10upx;
			}
		}
	}
</style>