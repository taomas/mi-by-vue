<template>
	<div class="video-container">
		<div class="header clearfix">
			<h2 class="title">{{title}}</h2>
			<a href="//www.mi.com/video/" target="_blank">
				<span class="top-sub">
					查看全部
					<i class="sub-icon fa fa-fw fa-chevron-circle-right"></i>
				</span>
			</a>
		</div>
		<div class="video-content">
			<ul class="video-wrap clearfix">
				<li class="video-item"
					v-for="item in videos"\
					@click="evtPlayVideo(item)">
					<div class="item-top">
						<img :src="item.imgUrl" alt="" />
						<span class="play">
							<i class="fa fa-play"></i>
						</span>
					</div>
					<h3 class="video-title">{{item.title}}</h3>
					<p class="video-desc">
						{{item.desc}}
					</p>
				</li>
			</ul>
		</div>
	</div>
</template>

<script>
import GoodsHeader from './common/GoodsHeader'
export default {
	data () {
		return {
			title: '视频',
			videos: [{
				videoUrl: 'http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTY1ODg5ODA0MA==',
				imgUrl: 'http://i3.mifile.cn/a4/73d67577-cbc7-4bd0-8678-4b1e95f4f4dc',
				title: '红米年度品牌视频',
				desc: '一亿人喜爱你，是一种责任。'
			},
			{
				videoUrl: 'http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTY1OTg3NjQ4OA==',
				imgUrl: 'http://i3.mifile.cn/a4/f7e434fb-8ce4-4442-bf78-0d66e409dfc3',
				title: '小米笔记本Air最全介绍视频',
				desc: '带独立显卡的轻薄笔记本'
			},
			{
				videoUrl: 'http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTY1OTg4NjY0OA==',
				imgUrl: 'http://i3.mifile.cn/a4/e2df3ad8-4147-44e1-8a54-b6bcafdc6c66',
				title: '小米笔记本Air可靠性测试视频',
				desc: '小米笔记本Air是如何炼成的？'
			},
			{
				videoUrl: 'http://hd.mi.com/f/zt/hd/misc/youku.html?vid=XMTU2NDM3NjEzMg==',
				imgUrl: 'http://i3.mifile.cn/a4/T1v3LgBTxv1RXrhCrK.jpg',
				title: '小米Max 绝美外观视频',
				desc: '6.44" 大屏黄金尺寸，看什么都震撼'
			}]
		}
	},
	methods: {
		evtPlayVideo (opts) {
			let videoOpt = {
				status: true,
				title: opts.title,
				videoUrl: opts.videoUrl
			}
			this.$dispatch('play', videoOpt)
		}
	},
	components: {
		'goods-header': GoodsHeader
	}
}
</script>

<style>
.video-container {
	width: 1226px;
	height: auto;
	margin: 0 auto;
}
.header {
	position: relative;
	.title {
		display: block;
		float: left;
		margin: 0;
		font-size: 22px;
		font-weight: 200;
		line-height: 58px;
		color: #333;
	}
	.top-sub {
	  float: right;
	  display: block;
	  font-size: 16px;
	  line-height: 58px;
	  color: #424242;
	  cursor: pointer;
	  .sub-icon {
	    color: #b0b0b0;
	    font-size: 20px;
	  }
	  &:hover {
	    color: #ff6700;
	    .sub-icon {
	      color: #ff6700;
	    }
	  }
	}
}

.video-wrap {
	.video-item {
		position: relative;
		float: left;
		width: 296px;
		height: 285px;
		margin: 0 0 14px 14px;
		background: #fff;
		cursor: pointer;
		transition: all 0.3s;
		&:hover {
			transform: translateY(-3px);
			box-shadow: 5px 5px 20px #ccc;
			.play {
				background: #ff6700;
			}
		}
		&:nth-child(1) {
			margin-left: 0;
		}
		img {
			width: 296px;
			height: 180px;
		}
		.video-title {
			color: #333;
			font-size: 14px;
			font-weight: normal;
			text-align: center;
		}
		.video-desc {
			height: 18px;
	    margin: 0;
	    font-size: 12px;
			text-align: center;
	    color: #b0b0b0;
		}
	}
}

.item-top {
	position: relative;
	.play {
		position: absolute;
		display: block;
		left: 20px;
		bottom: 10px;
		width: 32px;
		height: 20px;
		line-height: 20px;
		color: #fff;
		text-align: center;
		font-size: 12px;
		border: 2px solid #fff;
		border-radius: 12px;
		background: #333;
	}
}
</style>
