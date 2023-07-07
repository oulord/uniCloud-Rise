<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
	</view>
</template>

<script>
	const cloudObj1 = uniCloud.importObject("cloudObj1")
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {
			this.getData(),
				cloudObj1.add().then(res => {
					console.log(res);
				})
		},
		methods: {
			getData() {
				cloudObj1.get(3).then(res => {
					console.log(res);
				})

				return

				uniCloud.callFunction({
					name: "cloudFun1",
					data: {
						num: 2
					}
				}).then(res => {
					console.log(res);
				})
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
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
</style>