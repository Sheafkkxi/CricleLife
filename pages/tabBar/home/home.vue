<template>
	<view>
	<view class="topbg">
		<image style ="width: 50upx;height: 50upx;"src="../../../static/com/LClog_trans.png" mode="scaleToFill"></image>
		<text>生活圈子</text>
		<text>LifeCircle</text>
		<text>专注智慧社区解决方案</text>
	</view>
	<view class="cu-list grid" :class="['col-' + gridCol,gridBorder?'':'no-border']">
		<view class="cu-item" v-for="(item,index) in iconList" :key="index" v-if="index<gridCol*2">
			<view :class="['cuIcon-' + item.icon,'text-' + item.color]">
				<view class="cu-tag badge" v-if="item.badge!=0">
					<block v-if="item.badge!=1">{{item.badge>99?'99+':item.badge}}</block>
				</view>
			</view>
			<text>{{item.name}}</text>
		</view>
	</view>
	<swiper class="screen-swiper" :class="dotStyle?'square-dot':'round-dot'" :indicator-dots="true" :circular="true"
	 :autoplay="true" interval="5000" duration="500">
		<swiper-item v-for="(item,index) in swiperList" :key="index">
			<image :src="item.url" mode="aspectFill" v-if="item.type=='image'"></image>
			<video :src="item.url" autoplay loop muted :show-play-btn="false" :controls="false" objectFit="cover" v-if="item.type=='video'"></video>
		</swiper-item>
	</swiper>
	</view>
</template>

<script>
	export default{
		data() {
			return {
				iconList: [{
					icon: 'cardboardfill',
					color: 'red',
					badge: 120,
					name: '物业缴费'
				}, {
					icon: 'recordfill',
					color: 'orange',
					badge: 1,
					name: '小区公告'
				}, {
					icon: 'picfill',
					color: 'yellow',
					badge: 0,
					name: '快递服务'
				}, {
					icon: 'noticefill',
					color: 'olive',
					badge: 22,
					name: '家政服务'
				}, {
					icon: 'upstagefill',
					color: 'cyan',
					badge: 0,
					name: '停车缴费'
				}, {
					icon: 'clothesfill',
					color: 'blue',
					badge: 0,
					name: '物业报修'
				}],
				modalName: null,
				gridCol: 3,
				gridBorder: false,
				cardCur: 0,
				swiperList: [{
					id: 0,
					type: 'image',
					url: "../../../static/banner/banner1.JPG"
				}, {
					id: 1,
					type: 'image',
					url: "../../../static/banner/banner2.jpg"
				}, {
					id: 2,
					type: 'image',
					url: "../../../static/banner/banner3.jpg"
				}, {
					id: 3,
					type: 'image',
					url: "../../../static/banner/banner4.jpg"
				}],
				dotStyle: true,
				towerStart: 0,
				direction: ''
			};
		},
		onLoad:function(){
			
		},
		methods: {
			openCarDeteil(e) {},
		}
	}
</script>

<style>
	.topbg {
		height:300upx ;
		width: 100%;
		background: #8BC34A;
	}
	
	.swiper {
		height: 400upx;
	}
	.swiper-item {
		display: block;
		height: 400upx;
		line-height: 400upx;
		text-align: center;
	}
	
	.swiper-list {
		margin-top: 40upx;
		margin-bottom: 0;
	}
	
	.uni-common-mt{
		margin-top:60upx;
		position:relative;
	}
	
	.info {
		position: absolute;
		right:20upx;
	}
	.uni-media-list-body {
		height: auto;
	}
	.uni-media-list-text-top {
		line-height: 1.6em;
	}
	.hostType{
		color: red;
	}
	.uni-media-list-logo{
		height: 300upx;
		width: 300upx;
		margin-right: 20upx;
	}
	.uni-flex-item{
	width: auto;
	}
	.flex-item {
		width: 33.3%;
		height: 200upx;
		text-align: center;
		line-height: 200upx;
	}
	
	.flex-item-V {
		width: 100%;
		height: 150upx;
		text-align: center;
		line-height: 150upx;
	}
	.text{
		margin:0 0upx;
		padding: 0 0upx;
		background-color: #FFFFFF;
		height: auto;
		flex: 1;
		line-height: auto;
		text-align: center;
		color: #777;
		font-size: 26upx;
	}
	.desc{
		/* text-indent: 40upx; */
	}
	.uni-base-img{
		margin:30upx 2%;
		padding: 0 0upx;
		background-color: #FFFFFF;
	
	}
	.uni-item-rate{
		margin:15upx 10upx;
		
	}
	.text-host{
		margin:8upx 10upx;
		padding: 0 20upx;
		background-color: #FFFFFF;
		height: auto;
		flex: 1;
		line-height: auto;
		text-align: center;
		color: #FF0000;
		font-size: 26upx;
	}
	.uni-topbar{
		margin:0upx 0upx ;
		padding: 0 0upx;
		background-color: #FFFFFF;
		width: 100%;
		height: 80upx;
		flex: 1;
		line-height: 80upx;
	}
	.text-caytype{
		margin:8upx 10upx;
		padding: 0 20upx;
		background-color: #FFFFFF;
		height: auto;
		flex: 1;
		line-height: auto;
		text-align: center;
		color: #777;
		font-size: 26upx;
	}
	
</style>
