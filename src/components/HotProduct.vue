<template>
	<div class="hot-container">
		<goods-header :title="title"></goods-header>
		<div class="hot-wrap">
			<ul class="hot-content clearfix">
				<li class="hot-item"
					v-for="item in hots">
					<img class="item-image" :src="item.imageUrl" alt="" />
					<div class="item-evaluation">
						<p class="review-txt">{{item.review}}</p>
						<p class="author">来自{{item.author}}的评价</p>
					</div>
					<div class="item-desc">
						<span class="item-name">{{item.name}}</span>
						<span class="sep">|</span>
						<span class="item-price">{{item.price}}</span>
					</div>
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
			title: '热评产品',
			hots: [
				{imageUrl: 'http://i3.mifile.cn/a4/bae79ac6-60d5-478d-90e7-ff1222764bd1', review: '东西很小，做工挺精致，电池待机也比想象中好。值得买。', author: '同路者', name: '小米随身蓝牙音箱', price: '299元', favorable: '1.1万'},
				{imageUrl: 'http://i3.mifile.cn/a4/62d44838-f464-4c11-887c-9168645ae797', review: '东西很小，做工挺精致，电池待机也比想象中好。值得买。', author: '同路者', name: '小米随身蓝牙音箱', price: '299元', favorable: '1.1万'},
				{imageUrl: 'http://i3.mifile.cn/a4/1e737b55-91bd-4f5b-b085-405fa722142f', review: '东西很小，做工挺精致，电池待机也比想象中好。值得买。', author: '同路者', name: '小米随身蓝牙音箱', price: '299元', favorable: '1.1万'},
				{imageUrl: 'http://i3.mifile.cn/a4/a14bd55a-2a7f-4e5f-9d8d-79e3e1bdb467', review: '东西很小，做工挺精致，电池待机也比想象中好。值得买。', author: '同路者', name: '小米随身蓝牙音箱', price: '299元', favorable: '1.1万'}
			]
		}
	},
	components: {
		'goods-header': GoodsHeader
	}
}
</script>

<style>
.hot-container {
	width: 1226px;
	height: auto;
	margin: 0 auto;
}

.hot-header {
	position: relative;
	.title {
		margin: 0;
		font-size: 22px;
		font-weight: 200;
		line-height: 58px;
		color: #333;
	}
}

.hot-content {
	.hot-item {
		float: left;
		width: 296px;
		height: 415px;
		padding: 0 0 14px 14px;
		cursor: pointer;
		transition: all 0.3s;
		&:nth-child(1) {
			padding-left: 0;
		}
		&:hover {
			transform: translateY(-3px);
			box-shadow: 5px 5px 20px #ccc;
		}
		.item-image {
			width: 296px;
			height: 220px;
		}
		.review-txt {
			height: 72px;
			margin: 22px 28px;
			font-size: 14px;
			line-height: 24px;
			font-weight: 400;
			overflow: hidden;
		}
		.author {
			position: relative;
			height: 18px;
			margin: 0 28px 8px;
			padding: 0 10px 0 0;
			font-size: 12px;
			color: #b0b0b0;
		}
	}
}

.item-desc {
	padding-left: 30px;
	.item-name {
		font-size: 14px;
		color: #333;
	}
	.sep {
		margin: 0 4px;
		color: #e0e0e0;
	}
	.item-price {
		font-size: 14px;
		color: #ff6700;
	}
}
</style>
