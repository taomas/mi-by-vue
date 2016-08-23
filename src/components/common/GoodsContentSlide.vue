<template>
	<div class="content"
		:class="content.type">
		<h3 class="title">{{content.title}}</h3>
		<div class="slide-wrap">
			<span
				@click="slidePre($index)"
				class="slide-pre">
				<i class="fa fa-chevron-left fa-fw icon-chevron-left"></i>
			</span>
			<span
				@click="slideNext($index)"
				class="slide-next">
				<i class="fa fa-chevron-right fa-fw icon-chevron-right"></i>
			</span>
			<ul class="sub-content clearfix"
				:style="{'margin-left': this.currPage * (-296) + 'px'}">
				<li class="content-item"
					v-for="item in content.list">
					<template v-if="item.type === 0">
						<h3 class="subTitle">{{item.title}}</h3>
						<p class="desc">
							{{item.desc}}
						</p>
						<img class="content-image" :src="item.imgUrl" alt="" />
					</template>
					<template v-if="item.type === 1">
						<h3 class="subTitle">{{item.title}}</h3>
						<p class="desc">
							{{item.desc}}
						</p>
						<p class="price">
							{{item.price}}
						</p>
						<img class="content-image" :src="item.imgUrl" alt="" />
					</template>
					<template v-if="item.type === 2">
						<p class="desc">
							{{item.desc1}}<br/>{{item.desc2}}
						</p>
						<p class="btn-txt">
							{{item.btnTxt}}
						</p>
						<img class="content-image" :src="item.imgUrl" alt="" />
					</template>
				</li>
			</ul>
		</div>
	</div>
</template>

<script>
export default {
	data () {
		return {
			currPage: 0
		}
	},
	props: {
		content: {
			require: true,
			type: Object
		}
	},
	methods: {
		slidePre () {
			if (this.currPage !== 0) {
				this.currPage--
			}
		},
		slideNext () {
			if (this.currPage < Math.floor((this.content.list.length - 1))) {
				this.currPage++
			}
		},
		evtMouseEnter () {

		},
		evtMouseLeave () {

		}
	}
}
</script>

<style>
.content {
	position: relative;
	float: left;
	width: 296px;
	height: auto;
	margin: 0 0 14px 14px;
	padding-top: 45px;
	background: #fff;
	transition: all 0.3s;
	&:hover {
		transform: translateY(-3px);
		box-shadow: 5px 5px 20px #ccc;
		.slide-pre, .slide-next {
			opacity: 1;
		}
	}
	&:nth-child(1) {
		margin-left: 0;
	}
	.title {
		margin: 0 10px 18px;
		font-size: 16px;
		font-weight: 400;
		text-align: center;
	}
}
.book {
	border-top: 1px solid #ffac13;
	.title {
		color: #ffac13;
	}
}

.slide-wrap {
	width: 296px;
	height: 340px;
	overflow: hidden;
	.sub-content {
		width: 1200px;
		height: 340px;
		transition: all 0.5s ease;
		.content-item {
			position: relative;
			float: left;
			width: 296px;
			height: 340px;
		}
	}
	.slide-pre, .slide-next {
		display: block;
		width: 20px;
		height: 46px;
		line-height: 46px;
		font-size: 15px;
		text-align: center;
		margin-top: -24px;
		cursor: pointer;
		z-index: 11;
		background: #b0b0b0;
		color: #fff;
	}
	.slide-pre {
		position: absolute;
		left: 0;
		top: 50%;
		opacity: 0;
		transition: all 0.3s;
	}
	.slide-next {
		position: absolute;
		right: 0;
		top: 50%;
		opacity: 0;
		transition: all 0.3s;
	}
}

.subTitle {
	font-weight: normal;
	font-size: 20px;
	text-align: center;
	color: #333;
}
.desc {
	font-size: 12px;
	line-height: 1.5;
	text-align: center;
	color: #b0b0b0;
}
.content-image {
	display: block;
	width: 216px;
	height: 154px;
	margin: 0 auto;
}
.price {
	font-size: 14px;
	text-align: center;
	color: #333;
}
.btn-txt {
	width: 130px;
	height: 30px;
	line-height: 30px;
	font-size: 12px;
	text-align: center;
	margin: 0 auto;
	margin-bottom: 14px;
	border: 1px solid #ffac13;
	color: #ffac13;
	background: #fff;
	cursor: pointer;
	&:hover {
		color: #fff;
		background: #ffac13;
	}
}
</style>
