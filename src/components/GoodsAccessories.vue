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
			topTitle: '周边',
			subs: [
				{name: '热门', key: 'hot'},
				{name: '保护套', key: 'clothes'},
				{name: '贴膜', key: 'rabbit'},
				{name: '其它配件', key: 'around'}
			],
			leftGoods: [
				{imgUrl: 'http://i3.mifile.cn/a4/aa163c95-2890-4227-967c-a05ccec6c4a9'},
				{imgUrl: 'http://i3.mifile.cn/a4/363032e6-b043-4854-a8cc-8909df918f02'}
			],
			hotGoods: [
				{imgUrl: 'http://i2.mifile.cn/a1/T1COAjB7WT1RXrhCrK.jpg?width=150&height=150', 'title': '指环式防滑手机支架', price: '12.5元', oldPrice: '149', heat: '7869',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1_SDgB4KT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2万',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1l9WjBTbT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2万',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1zL_vByCT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2万',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1AmJgBsKT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2万',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/pms_1468287589.40786199.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2万',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1_8YvBKJT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2万',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1Zp__B5Ev1RXrhCrK.jpg?width=80&height=80', 'title': '小米小钢炮', price: '79'}
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
