<template>
	<div class="video-mask" v-show="playConfig.status">
		<div class="video-content"
			v-show="playConfig.status"
			transition="fadeIn">
			<div class="video-header clearfix">
				<h3 class="title-txt">{{playConfig.title}}</h3>
				<div class="cancel-link"
					@click="evtCancel">
					<i class="cancel-btn fa fa-times"></i>
				</div>
			</div>
			<div class="video">
				<iframe width="880" height="536" :src="playConfig.videoUrl" frameborder="0" allowfullscreen=""></iframe>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data () {
		return {
			scrollTop: 0
		}
	},
	watch: {
		playConfig: function (newVal, oldVal) {
		}
	},
	methods: {
		evtCancel () {
			let config = {
				status: false,
				title: this.playConfig.title
			}
			this.$dispatch('play', config)
		}
	},
	props: {
		playConfig: {
			required: true,
			type: Object
		}
	}
}
</script>

<style scoped>
.video-mask {
	position: fixed;
	left: 0;
	top: 0;
	width: 100%;
	height: 100%;
	background: rgba(0, 0, 0, 0.5);
	z-index: 12;
}

.video-content {
	position: absolute;
	left: 50%;
	margin-left: -440px;
	width: 880px;
	height: 596px;
	background: #fff;
}

.video-header {
	padding: 14px 20px;
	background: #f5f5f5;
	.title-txt {
		margin: 0;
		font-size: 18px;
		font-weight: 400;
		line-height: 32px;
		color: #424242;
	}
	.cancel-link {
		display: block;
		position: absolute;
		top: 10px;
		right: 20px;
		width: 30px;
		height: 30px;
		line-height: 30px;
		text-align: center;
		border-radius: 30px;
		font-size: 24px;
		color: #757575;
		transition: all .2s;
		cursor: pointer;
		&:hover {
			color: #fff;
			background: #e53935;
		}
	}
}

.video {
	width: 880px;
	height: 536px;
}

.fadeIn-transition {
  transition: all .3s ease-out;
	transform: translateY(30%);
	will-change: transform;
}

.fadeIn-enter, .fadeIn-leave {
	transform: translateY(0);
}
</style>
