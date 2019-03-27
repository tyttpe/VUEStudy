<template>
	<view class="content">
		<text class="title">{{name}}</text>
		<navigator url="setting">
			<button type="primary">个人设置</button>
		</navigator>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				name: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.content {
		text-align: center;
		height: 400upx;
	}
	.title {
		font-size: 36upx;
		color: #8f8f94;
	}
</style>
