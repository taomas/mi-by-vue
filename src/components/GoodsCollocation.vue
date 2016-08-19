<template>
	<div class="around-container">
		<goods-top
			:top-title="topTitle"
			:subs="subs"></goods-top>
		<div class="goods-content clearfix">
			<goods-left
				:left-goods="leftGoods"
			></goods-left>
			<goods-right
				:hot-goods="hotGoods"
			></goods-right>
		</div>
	</div>
</template>

<script>
import GoodsTop from './common/GoodsTop'
import GoodsLeft from './common/GoodsLeft'
import GoodsRight from './common/GoodsRight'
export default {
	data () {
		return {
			topTitle: '搭配',
			subs: [
				{name: '热门', key: 'hot'},
				{name: '耳机音响', key: 'clothes'},
				{name: '电源', key: 'rabbit'},
				{name: '电池存储卡', key: 'around'}
			],
			leftGoods: [
				{imgUrl: 'http://i3.mifile.cn/a4/54581b2c-f88d-4415-9754-af83116346bd'},
				{imgUrl: 'http://i3.mifile.cn/a4/f7da6234-7159-414a-a2ea-8832af89b4f1'}
			],
			hotGoods: [
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1ycK_BjYv1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T12HJvByEv1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1WxYvB_xv1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1pZbvBTET1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/pms_1463579883.27084326.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1F5K_BjVv1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T15hZ_BsDv1RXrhCrK.jpg?width=80&height=80', 'title': '小米小钢炮', price: '79'}
			]
		}
	},
	components: {
		'goods-top': GoodsTop,
		'goods-left': GoodsLeft,
		'goods-right': GoodsRight
	}
}
</script>

<style>
.around-container {
	width: 1226px;
	height: auto;
	margin: 0 auto;
}
.goods-content {
	width: 1226px;
	height: auto;
	margin: 0 auto;
}
</style>
