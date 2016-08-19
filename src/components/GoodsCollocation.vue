<template>
	<div class="collocation-container">
		<div class="goods-top clearfix">
			<h3 class="top-title">搭配</h3>
			<ul class="top-sub">
				<li
					:class="{'active': topSubStatus === 'hot'}"
					@mouseenter="topSubEnter('hot')">热门</li>
				<li
					:class="{'active': topSubStatus === 'headset'}"
					@mouseenter="topSubEnter('headset')">耳机音响</li>
				<li
					:class="{'active': topSubStatus === 'power'}"
					@mouseenter="topSubEnter('power')">电源</li>
				<li
					:class="{'active': topSubStatus === 'battery'}"
					@mouseenter="topSubEnter('battery')">电池存储卡</li>
			</ul>
		</div>
		<div class="goods-content clearfix">
			<ul class="goods-left">
				<li class="goods-item item-top">
					<img src="http://i3.mifile.cn/a4/54581b2c-f88d-4415-9754-af83116346bd" alt="" />
				</li>
				<li class="goods-item item-bottom">
					<img src="http://i3.mifile.cn/a4/f7da6234-7159-414a-a2ea-8832af89b4f1" alt="" />
				</li>
			</ul>
			<ul class="goods-right">
				<li class="goods-rihgt-item"
					v-for="good in hotGoods">
					<img :src="good.imgUrl" alt="" />
					<h3 class="box-title">{{good.title}}</h3>
					<p class="box-price">
						{{good.price}}
					</p>
					<p class="box-heat">
						{{good.heat}}
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
			topSubStatus: 'hot',
			hotGoods: [
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2万'},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2万'},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2万'},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2万'},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2万'},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2万'},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2万'},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2万'}
			]
		}
	},
	methods: {
		topSubEnter (subStatus) {
			this.topSubStatus = subStatus
		}
	}
}
</script>

<style>
.collocation-container {
	width: 1226px;
	height: auto;
	margin: 0 auto;
}

.goods-top {
	width: 100%;
	height: 58px;
	.top-title {
		float: left;
		margin: 0;
		font-size: 22px;
		font-weight: 200;
		line-height: 58px;
		color: #333;
	}
	.top-sub {
		float: right;
		display: flex;
		flex-flow: row nowrap;
		justify-content: flex-start;
		align-items: center;
		font-size: 16px;
		line-height: 58px;
		color: #424242;
		li {
			margin-left: 30px;
			cursor: pointer;
			border-bottom: 2px solid #f5f5f5;
			&.active {
				color: #ff6700;
				border-bottom: 2px solid #ff6700;
			}
		}
	}
}

.goods-content {
	width: 1226px;
	height: auto;
	margin: 0 auto;
}

.goods-left {
	float: left;
  width: 234px;
  height: auto;
	.goods-item {
		width: 234px;
		height: 300px;
		cursor: pointer;
		transition: all 0.3s;
		&:hover {
			transform: translateY(-2px);
			box-shadow: 5px 5px 20px #ccc;
		}
		img {
			width: 234px;
			height: 300px;
		}
	}
	.item-bottom {
		margin-top: 14px;
	}
}
</style>
