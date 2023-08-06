<template>
	<view class="bar">
		<span class="title">{{title}}</span>
		<view class="right" @click="navigate">
			<span>全部</span>
			<image class="right-img" src="../../static/right.svg" mode=""></image>
		</view>
	</view>
</template>

<script>
	export default {
		name:"topbar",
		// props属性一定要写在前面，写方法后面不生效
		props: {
			title: '',
			url: '',
		},
		data() {
			return {
				
			};
		},
		methods: {
			// 跳转
			navigate() {
				console.log(this.url)
				uni.navigateTo({
					url: this.url
				})
			}
		},
	}
</script>

<style lang="scss" scoped>
.bar {
	box-sizing: border-box;
	width: 100%;
	display: flex;
	justify-content: space-between;
	padding: 30upx;
	
	.title {
		color: rgba(16, 16, 16, 1);
		font-size: 40upx;
		font-family: SourceHanSansSC-bold;
		font-weight: 600;
	}
	
	.right {
		display: flex;
		align-items: center;
		
		> span {
			color: rgba(108, 108, 108, 1);
			font-size: 24upx;
			font-family: SourceHanSansSC-regular;
			margin-right: 14upx;
		}
		
		&-img {
			width: 18upx;
			height: 18upx;
		}
	}
}
</style>