<template>
	<div class="goods-container">
		<goods-top-box></goods-top-box>
		<goods-collocation></goods-collocation>
		<goods-accessories></goods-accessories>
		<goods-around></goods-around>
		<recommend></recommend>
		<hot-product></hot-product>
		<goods-content></goods-content>
	</div>
</template>

<script>
import GoodsTopBox from './GoodsTopBox'
import GoodsCollocation from './GoodsCollocation'
import GoodsAccessories from './GoodsAccessories'
import GoodsAround from './GoodsAround'
import Recommend from './Recommend'
import HotProduct from './HotProduct'
import GoodsContent from './GoodsContent'

export default {
	components: {
		'goods-top-box': GoodsTopBox,
		'goods-collocation': GoodsCollocation,
		'goods-accessories': GoodsAccessories,
		'goods-around': GoodsAround,
		'recommend': Recommend,
		'hot-product': HotProduct,
		'goods-content': GoodsContent
	}
}
</script>

<style>
.goods-container {
	width: 100%;
	height: auto;
	background: #f5f5f5;
}
</style>
