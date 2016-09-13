<template>
	<div class="video-mask" v-show="maskStatus">
		<div class="video-content"
			v-show="videoStatus"
			transition="slideIn">
			<div class="video-header clearfix">
				<h3 class="title-txt">{{playConfig.title}}</h3>
				<div class="cancel-link"
					@click="evtCancel">
					<i class="cancel-btn fa fa-times"></i>
				</div>
			</div>
			<div class="video">
				<iframe :src="playConfig.videoUrl" frameborder="0" allowfullscreen=""></iframe>
			</div>
		</div>
	</div>
</template>

<script>
export default {
  data () {
    return {
      maskStatus: false
    }
  },
  computed: {
    videoStatus () {
      return this.playConfig.status
    }
  },
  watch: {
    videoStatus (newVal, oldVal) {
      let that = this
      if (!newVal) {
        setTimeout(function () {
          that.maskStatus = that.videoStatus
        }, 500)
      } else {
        that.maskStatus = that.videoStatus
      }
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
  iframe {
    width: 100%;
    height: 100%;
  }
}

.slideIn-transition {
  transition: all .3s ease-out;
	transform: translateY(30%);
}

.slideIn-enter, .slideIn-leave {
	transform: translateY(-100%);
}
</style>
