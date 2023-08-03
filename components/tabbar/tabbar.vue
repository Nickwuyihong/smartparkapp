<template>
	<view class="TabBar">
		<view class="tab" v-for="(item,index) in TabBarList" :key="index" @tap="navigatorTo(item.url)">
			<!-- 判断是否有点击，如果没有就不是激活样式，点击就是激活的样式 -->
			<image class="imgsize" v-if="item.type == 0" :src="current == index ? item.selectIcon : item.icon"
				mode="widthFix"></image>
			<!-- 设置一个状态值（type），判断加号是否展示 -->
			<view v-if="item.type == 1" class="addimgbox">
				<image class="imgsize" src="../../static/add.svg" mode="widthFix"></image>
			</view>
			<view class="text">{{item.name}}</view>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			current: {
				type: Number,
				default: 0 //默认第一个页面tabbar激活
			}
		},
		data() {
			return {
				TabBarList: [{
						type: 0,
						icon: '../../static/首页.png',
						selectIcon: '../../static/首页.png',
						name: '首页',
						url: '../index/index'
					},
					{
						type: 0,
						icon: '../../static/发现.png',
						selectIcon: '../../static/发现.png',
						name: '发现',
						url: '../demand/demand'
					},
					{
						type: 1,
						icon: '../../static/add.svg',
						selectIcon: '../../static/add.svg',
						name: '预约参观',
						url: '../edit/edit'
					},
					{
						type: 0,
						icon: '../../static/消息.png',
						selectIcon: '../../static/消息.png',
						name: '消息',
						url: '../company/company'
					},
					{
						type: 0,
						icon: '../../static/我的.png',
						selectIcon: '../../static/我的.png',
						name: '我的',
						url: '../personal/personal'
					},
				]
			}
		},
		methods: {
			navigatorTo(e) {
				console.log('mess')
				uni.redirectTo({
					url: e,
				});
			}
		}
	}
</script>

<style scoped>
	.TabBar {
		padding: 12upx 0;
		position: fixed;
		bottom: 0;
		height: 80upx;
		background-color: #fff;
		width: 100%;
		display: flex;
		justify-content: space-around;
		align-items: center;
	}

	.tab {
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.imgsize {
		width: 40upx;
		height: 40upx;
		margin: auto;
	}

	.addimgbox {
		width: 76upx;
		height: 76upx;
		background-color: rgba(15, 64, 245, 1);
		border-radius: 70upx;
		display: flex;
		margin-top: -50upx;
		margin-bottom: 14upx;
	}

	.text {
		font-size: 12px;
	}
</style>