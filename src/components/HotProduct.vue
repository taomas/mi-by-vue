<template>
	<div class="hot-container">
		<div class="hot-header">
			<h2 class="title">热评产品</h2>
		</div>
		<div class="recommend-wrap">
			<ul class="recommend-content">
				<li class="recomend-item"
					v-for="item in recomends">
					<img class="item-image" :src="item.imageUrl" alt="" />
					<h3 class="item-name">{{item.name}}</h3>
					<div class="item-evaluation">
						<p>{{item.evaluation}}</p>
						<p class="author">来自{{item.author}}的评价</p>
					</div>
					<div class="item-desc">
						<span class="item-name"></span>|
						<span class="item-price"></span>
					</div>
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
.hot-container {
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
}

</style>
