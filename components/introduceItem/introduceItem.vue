<template>
	<view class="introduce" @click="goDetail">
		<image class="in-img" :src="img" mode=""></image>
		<span class="name">{{name}}</span>
		<span class="desc">{{desc}}</span>
	</view>
</template>

<script>
	export default {
		props: {
			img: '',
			name: '',
			desc: '',
		},
		data() {
			return {
				
			}
		},
		methods: {
			goDetail() {
				console.log('goDetail')
			}
		},
	}
</script>

<style lang="scss" scoped>
	.introduce {
		display: flex;
		flex-direction: column;
		margin-right: 20upx;
		
		.in-img {
			width: 376upx;
			height: 264upx;
			border-radius: 10upx;
		}
		
		.name {
			color: rgba(16, 16, 16, 1);
			font-size: 26upx;
			font-family: SourceHanSansSC-regular;
		}
		
		.desc {
			color: rgba(154, 154, 154, 1);
			font-size: 22upx;
			font-family: SourceHanSansSC-light;
		}
	}
</style>
