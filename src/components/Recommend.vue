<template>
	<div class="recommend-container">
		<div class="recommend-header">
			<h2 class="title">为你推荐</h2>
			<div class="control-part">
				<span
					@click="slidePre"
					class="control control-left"
					:class="{'disable': this.currPage === 0}">
					<i class="fa fa-chevron-left icon-arrow"></i>
				</span>
				<span
					@click="slideNext"
					class="control control-right"
					:class="{'disable': this.currPage === Math.floor((this.recomends.length - 1) / 5)}">
					<i class="fa fa-chevron-right icon-arrow"></i>
				</span>
			</div>
		</div>
		<div class="recommend-wrap">
			<ul class="recommend-content">
				<li class="recomend-item"
					v-for="item in recomends">
					<img class="item-image" :src="item.imageUrl" alt="" />
					<h3 class="item-name">{{item.name}}</h3>
					<p class="item-price">
						{{item.price}}
					</p>
					<p class="item-favorable">
						{{item.favorable}}人评价
					</p>
				</li>
			</ul>
		</div>
	</div>
</template>

<script>
export default {
	data () {
		return {
			currPage: 0,
			evtNextStatus: true,
			evtPreStatus: true,
			recomends: [
				{imageUrl: '//i1.mifile.cn/a1/T18EWQBjWT1RXrhCrK.jpg?width=140&height=140', name: '智能显示保护套1', price: '59元', favorable: '4114'},
				{imageUrl: '//i1.mifile.cn/a1/pms_1469523170.25518983.jpg?width=140&height=140', name: 'USB-C至HDMI多功能转接器1', price: '149元', favorable: '82'},
				{imageUrl: '//i1.mifile.cn/a1/T1jsDgBXdv1RXrhCrK.jpg?width=140&height=140', name: '智能翻盖保护套1', price: '49元', favorable: '1.5万'},
				{imageUrl: '//i1.mifile.cn/a1/T1_tEgBmVv1RXrhCrK.jpg?width=140&height=140', name: '米兔儿童电话手表1', price: '299元', favorable: '7743'},
				{imageUrl: '//i1.mifile.cn/a1/T1CDbjBgAT1RXrhCrK.jpg?width=140&height=140', name: '90分旅行箱 24寸1', price: '349元', favorable: '1.1万'},
				{imageUrl: '//i1.mifile.cn/a1/T18EWQBjWT1RXrhCrK.jpg?width=140&height=140', name: '智能显示保护套2', price: '59元', favorable: '4114'},
				{imageUrl: '//i1.mifile.cn/a1/pms_1469523170.25518983.jpg?width=140&height=140', name: 'USB-C至HDMI多功能转接器2', price: '149元', favorable: '82'},
				{imageUrl: '//i1.mifile.cn/a1/T1jsDgBXdv1RXrhCrK.jpg?width=140&height=140', name: '智能翻盖保护套2', price: '49元', favorable: '1.5万'},
				{imageUrl: '//i1.mifile.cn/a1/T1_tEgBmVv1RXrhCrK.jpg?width=140&height=140', name: '米兔儿童电话手表2', price: '299元', favorable: '7743'},
				{imageUrl: '//i1.mifile.cn/a1/T1CDbjBgAT1RXrhCrK.jpg?width=140&height=140', name: '90分旅行箱 24寸2', price: '349元', favorable: '1.1万'},
				{imageUrl: '//i1.mifile.cn/a1/T18EWQBjWT1RXrhCrK.jpg?width=140&height=140', name: '智能显示保护套3', price: '59元', favorable: '4114'},
				{imageUrl: '//i1.mifile.cn/a1/pms_1469523170.25518983.jpg?width=140&height=140', name: 'USB-C至HDMI多功能转接器3', price: '149元', favorable: '82'},
				{imageUrl: '//i1.mifile.cn/a1/T1jsDgBXdv1RXrhCrK.jpg?width=140&height=140', name: '智能翻盖保护套3', price: '49元', favorable: '1.5万'},
				{imageUrl: '//i1.mifile.cn/a1/T1_tEgBmVv1RXrhCrK.jpg?width=140&height=140', name: '米兔儿童电话手表3', price: '299元', favorable: '7743'},
				{imageUrl: '//i1.mifile.cn/a1/T1CDbjBgAT1RXrhCrK.jpg?width=140&height=140', name: '90分旅行箱 24寸3', price: '349元', favorable: '1.1万'}
			]
		}
	},
	methods: {
		slideNext () {
			if (this.currPage < Math.floor((this.recomends.length - 1) / 5)) {
				this.currPage++
				$('.recommend-content').css('margin-left', this.currPage * (-1224) + 'px')
			}
		},
		slidePre () {
			if (this.currPage !== 0) {
				this.currPage--
				$('.recommend-content').css('margin-left', this.currPage * (-1224) + 'px')
			}
		}
	}
}
</script>

<style>
.recommend-container {
	width: 1226px;
	height: auto;
	margin: 0 auto;
}

.recommend-header {
	position: relative;
	.title {
		margin: 0;
		font-size: 22px;
		font-weight: 200;
		line-height: 58px;
		color: #333;
	}
	.control-part {
		position: absolute;
		top: 10px;
		right: 0;
		float: left;
		display: block;
		.control {
			display: block;
			float: left;
			width: 34px;
			height: 23px;
			line-height: 23px;
			text-align: center;
			border: 1px solid #e0e0e0;
			cursor: pointer;
			&:hover {
				.icon-arrow {
					color: #ff6700;
				}
			}
			&.disable {
				&:hover {
					.icon-arrow {
						color: #e0e0e0;
					}
				}
				.icon-arrow {
					color: #e0e0e0;
				}
			}
			.icon-arrow {
				color: #b0b0b0;
				font-size: 10px;
			}
		}
	}
}
.recommend-wrap {
	width: 1226px;
	height: 310px;
	overflow: hidden;
}
.recommend-content {
	width: auto;
	height: 300px;
	transition: all 0.3s;
	.recomend-item {
		float: left;
		display: block;
		width: 234px;
		height: 300px;
		margin: 0 13px 14px 0;
		font-size: 14px;
		background: #fff;
		cursor: pointer;
		transition: all 0.3s;
		&:hover {
			transform: translateY(-2px);
		}
		&:nth-last-child(5n+1) {
			margin-right: 0;
		}
		.item-image {
			display: block;
			width: 140px;
			height: 140px;
			margin: 40px auto 15px;
		}
		.item-name {
			margin-bottom: 10px;
			font-weight: normal;
			font-size: 14px;
			text-align: center;
			color: #333;
		}
		.item-price {
			margin-bottom: 10px;
			font-size: 14px;
			text-align: center;
			color: #ff6700;
		}
		.item-favorable {
			font-size: 14px;
			text-align: center;
			color: #757575;
		}
	}
}

</style>
