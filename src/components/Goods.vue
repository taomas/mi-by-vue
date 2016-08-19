<template>
	<div class="goods-container">
		<goods-top-box></goods-top-box>
		<goods-collocation></goods-collocation>
	</div>
</template>

<script>
import GoodsTopBox from './GoodsTopBox'
import GoodsCollocation from './GoodsCollocation'

export default {
	components: {
		'goods-top-box': GoodsTopBox,
		'goods-collocation': GoodsCollocation
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
