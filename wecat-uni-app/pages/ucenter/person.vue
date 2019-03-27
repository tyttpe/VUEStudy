<template>
	<view class="content">
		<view class="div-top">
			<view class="tip">
				<image src="../../static/camera.png" class="camer"></image>
			</view>
			<view class="toptitle">
				<view class="con1">
					<image src="../../static/2.jpg" class="bg"></image>
				</view>
				<view class="con2">
					<view>
						<text class="name">{{name}}</text>
					</view>
					<view>
						<text class="wecatnum">微信号:{{wecatnum}}</text>
					</view>
				</view>
			</view>
		</view>
		<view class="div-cen">
			<view class="cen1">
				<image src="../../static/zhufu.png"></image>
			<text class="zhufu">支付</text>
			</view>
			<view class="cen2">
				<image src="../../static/join.png"></image>
			</view>
			
		</view>


		<view class="item" v-for="(title,index) in titles" :key="index">
			<view class="center">
				<view class="cen1">
					<image :src="title.ava"></image>
				<text>{{title.tit}}</text>
				</view>
				<view class="cen2">
					<image src="../../static/join.png"></image>
				</view>
				
			</view>
		</view>

		<view class="div-bot">
			<view class="cen1">
			<navigator url="setting">
			<image src="../../static/shezhi.png"></image>
			<text class="shezhi">设置</text>	
			</navigator>	
			</view>
 			<view class="cen2">
				<image src="../../static/join.png"></image>
			</view> 
			
		</view>

	</view>


</template>

<script>
	export default {
		data() {
			return {
				img: "2.jpg",
				name: 'tom',
				wecatnum: 'wxid_yd313cpuxq...',
				titles: [{
						ava: '../../static/shoucang.png',
						tit: "收藏"
					},
					{
						ava: '../../static/xiangce.png',
						tit: "相册"
					},
					{
						ava: '../../static/kabao.png',
						tit: "卡包"
					},
					{
						ava: '../../static/biaoqing.png',
						tit: "表情"
					}
				]
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.div-bot {
		display: flex;
		height: 120upx;
		background-color: #FFFFFF;
		margin-top: 25upx;
		margin-bottom: 100upx;
	}

	.div-bot image {
		height: 50upx;
		width: 50upx;
		margin-top: 35upx;
		margin-left: 35upx;
		margin-right: 35upx;
	}

	.div-cen {
		display: flex;
		height: 120upx;
		background-color: #FFFFFF;
		margin-bottom: 25upx;
		justify-content: space-between;
	}
	.cen1{
		flex: 1 1 90%;
	}
	.cen2{
		flex: 1 1 10%;
	}

	.div-cen image {
		height: 50upx;
		width: 50upx;
		margin-top: 35upx;
		margin-left: 35upx;
		margin-right: 35upx;
	}

	.tip {
		height: 120upx;
	}

	.camer {
		height: 50upx;
		width: 50upx;
		margin-top: 20upx;
		margin-right: 30upx;
		float: right;
	}

	.content {
		height: 100%;
		background-color: #ededed;
	}

	.bg {
		height: 150upx;
		width: 150upx;
		border-radius: 10upx;
	}

	.toptitle {
		display: flex;
		height: 250upx;
	}

	.con1 {
		flex: 1 1 20%;
		margin-left: 40upx;
		margin-right: 40upx;
	}

	.con2 {
		flex: 1 1 80%;
		display: block;
	}

	.name {
		font-size: 60upx;
	}

	.wecatnum {
		font-size: 35upx;
		color: #8F8F94;
	}

	.item {
		font: 10upx;

	}

	.center {
		height: 120upx;
		background-color: #FFFFFF;
		border: 1px solid #eee;
		display: flex;
	}

	.item image {
		height: 50upx;
		width: 50upx;
		margin-top: 35upx;
		margin-left: 35upx;
		margin-right: 35upx;
	}

	.div-top {
		background-color: #FFFFFF;
		margin-bottom: 25upx;
	}
</style>
