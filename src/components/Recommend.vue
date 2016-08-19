<template>
	<div class="recommend-container">
		<div class="recommend-header">
			<h2 class="title">为你推荐</h2>
			<div class="control-part">
				<span class="control control-left">
					<i class="fa fa-chevron-left icon-arrow"></i>
				</span>
				<span class="control control-right">
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
			recomends: [
				{imageUrl: '//i1.mifile.cn/a1/T1CDbjBgAT1RXrhCrK.jpg?width=140&height=140', name: ' 90分旅行箱 24寸', price: '299元', favorable: '1.1万'},
				{imageUrl: '//i1.mifile.cn/a1/T1CDbjBgAT1RXrhCrK.jpg?width=140&height=140', name: ' 90分旅行箱 24寸', price: '299元', favorable: '1.1万'},
				{imageUrl: '//i1.mifile.cn/a1/T1CDbjBgAT1RXrhCrK.jpg?width=140&height=140', name: ' 90分旅行箱 24寸', price: '299元', favorable: '1.1万'},
				{imageUrl: '//i1.mifile.cn/a1/T1CDbjBgAT1RXrhCrK.jpg?width=140&height=140', name: ' 90分旅行箱 24寸', price: '299元', favorable: '1.1万'},
				{imageUrl: '//i1.mifile.cn/a1/T1CDbjBgAT1RXrhCrK.jpg?width=140&height=140', name: ' 90分旅行箱 24寸', price: '299元', favorable: '1.1万'}
			]
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
			.icon-arrow {
				color: #b0b0b0;
				font-size: 10px;
			}
		}
	}
}
.recommend-content {
	display: flex;
	flex-flow: row nowrap;
	justify-content: flex-start;
	.recomend-item {
		width: 234px;
		height: 300px;
		margin: 0 14px 14px 0;
		font-size: 14px;
		background: #fff;
		cursor: pointer;
		transition: all 0.3s;
		&:hover {
			transform: translateY(-1px);
		}
		&:nth-last-child(1) {
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
