<template>
	<div class="banner">
		<span
			@click="slidePre"
			class="slide-pre">
			<i class="fa fa-chevron-left fa-2x fa-fw icon-chevron-left"></i>
		</span>
		<span
			@click="slideNext"
			class="slide-next">
			<i class="fa fa-chevron-right fa-2x fa-fw icon-chevron-right"></i>
		</span>
		<div
			class="slide"
			transition="fadeIn"
			v-show="$index === curpage"
			v-for="item in banners">
			<a :href="item.sourceUrl" target="_blank">
				<img :src="item.imgUrl" alt="" />
			</a>
		</div>
	</div>
</template>

<script>
export default {
	data () {
		return {
			prevTid: '',
			curpage: 0,
			slideDirection: 1
		}
	},
	props: {
		banners: {
			type: Array,
      required: true
		}
	},
	ready () {
		this.autoSlide()
	},
	methods: {
		slideNext () {
			const lastPage = this.banners.length - 1
			if (this.curpage < lastPage) {
				this.curpage += 1
			} else {
				this.curpage = 0
			}
		},
		slidePre () {
			const lastPage = this.banners.length - 1
			if (this.curpage > 0) {
				this.curpage -= 1
			} else {
				this.curpage = lastPage
			}
		},
		autoSlide () {
			clearInterval(this.prevTid)
			this.prevTid = setInterval(() => {
				this.slideNext()
			}, 5000)
		}
	}
}
</script>

<style scoped>
.banner {
	position: relative;
	width: 1226px;
	height: 460px;
	z-index: 0;
}

.slide-pre {
	display: block;
	position: absolute;
	left: 235px;
	top: 50%;
	width: 40px;
	height: 70px;
	margin-top: -35px;
	z-index: 10;
	cursor: pointer;
	&:hover{
		background: rgba(0, 0, 0, 0.3);
	}
}

.slide-next {
	display: block;
	position: absolute;
	right: 0;
	top: 50%;
	width: 40px;
	height: 70px;
	margin-top: -35px;
	z-index: 10;
	cursor: pointer;
	&:hover{
		background: rgba(0, 0, 0, 0.3);
	}
}

.slide {
	position: absolute;
	left: 0;
	top: 0;
	width: 1226px;
	height: 460px;
	transition: all 0.3s;
	img {
		width: 100%;
		height: 100%;
	}
}

.icon-chevron-left, .icon-chevron-right {
	position: absolute;
	left: 50%;
	top: 50%;
	width: 30px;
	height: 30px;
	margin-left: -15px;
	margin-top: -15px;
	color: #ecf0f1;
}

/* 必需 */
.fadeIn-transition {
  transition: all .5s ease;
	opacity: 1;
}

/* .expand-enter 定义进入的开始状态 */
/* .expand-leave 定义离开的结束状态 */
.fadeIn-enter, .fadeIn-leave {
  opacity: 0;
}

</style>
