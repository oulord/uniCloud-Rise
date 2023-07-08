<template>
	<view class="home">
		<view class="topnav">
			<u-tabs :list="list1" @click="click" :activeStyle="{
			    color: '#303133',
			    fontWeight: 'bold',
			    transform: 'scale(1.05)'
			}" :inactiveStyle="{
			            color: '#606266',
			            transform: 'scale(1)'
			}"></u-tabs>
		</view>

		<!-- 骨架屏 -->
		<view class="loadingState" v-show="loadState">
			<u-skeleton rows="4" title loading v-show="loadState"></u-skeleton>
		</view>

		<view class="content">
			<view class="item" v-for="item in dataList">
				<blog-item></blog-item>
			</view>
		</view>

		<view class="edit">
			<text class="iconfont icon-a-21-xiugai"></text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list1: [{
					name: "最新",
				}, {
					name: "热门"
				}],
				loadState: false,
				dataList: [1, 2, 3]
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style lang="scss" scoped>
	.home {
		.topnav {
			margin-bottom: 30rpx;
		}

		.loadingState {
			padding: 30rpx;
		}

		.content {
			.item {
				padding: 30rpx;
			}
		}

		.edit {
			width: 120rpx;
			height: 120rpx;
			background: #0199FE;
			border-radius: 50%;
			color: #fff;
			position: fixed;
			z-index: 100;
			bottom: 150rpx;
			right: 50rpx;
			display: flex;
			justify-content: center;
			align-items: center;
			box-shadow: 0 0 20rpx rgba(1, 153, 254, 0.8);

			.iconfont {
				font-size: 50rpx;
			}
		}
	}
</style>