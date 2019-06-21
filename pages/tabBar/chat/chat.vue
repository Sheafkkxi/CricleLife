<template>
    <view >
        <!-- <video class="video" id="demoVideo" :controls="disable" :show-fullscreen-btn="disable" :show-play-btn="disable"
         :show-center-play-btn="disable" :enable-progress-gesture="disable" @fullscreenchange="fullscreenchange" src="https://dcloud-img.oss-cn-hangzhou.aliyuncs.com/guide/uniapp/%E7%AC%AC1%E8%AE%B2%EF%BC%88uni-app%E4%BA%A7%E5%93%81%E4%BB%8B%E7%BB%8D%EF%BC%89-%20DCloud%E5%AE%98%E6%96%B9%E8%A7%86%E9%A2%91%E6%95%99%E7%A8%8B@20181126.mp4">
            <cover-view class="controls-title">简单的自定义 controls</cover-view>
            <cover-image class="controls-play img" @click="play" src="../../../static/play.png"></cover-image>
            <cover-image class="controls-pause img" @click="pause" src="../../../static/pause.png"></cover-image>
        </video> -->
		<calendar 
        :date="date"
        :lunar="true" 
        :disable-before="true" 
        :start-date="'2019-3-2'"
        :end-date="'2019-5-20'"
        @change="change"
        @to-click="toClick"
         />
    </view>
</template>
<script>
	import calendar from "@/components/uni-calendar/uni-calendar"

    export default {
		components:{
			calendar
		},
        data() {
            return {
                videoCtx: null,
                disable: false,
				 date:'2019-03-10'
            }
        },
        mounted() {
            this.videoCtx = uni.createVideoContext('demoVideo')
        },
        methods: {
            play(event) {
                this.videoCtx.play();
                uni.showToast({
                    title: '开始播放',
                    icon: 'none'
                });
            },
            pause(event) {
                this.videoCtx.pause();
                uni.showToast({
                    title: '暂停播放',
                    icon: 'none'
                });
            },
			change(e) {
				console.log(e);
			},
			toClick(e) {
				console.log(e);
			}
        }
    }
</script>
<style>
    .page {
        display: flex;
        justify-content: center;
    }

    .video {
        position: relative;
    }

    cover-view,
    cover-image {
        display: inline-block;
    }

    .img {
        position: absolute;
        width: 100upx;
        height: 100upx;
        top: 50%;
        margin-top: -50upx;
    }

    .controls-play {
        left: 50upx;
    }

    .controls-pause {
        right: 50upx;
    }

    .controls-title {
        width: 100%;
        text-align: center;
        color: #FFFFFF;
    }
</style>