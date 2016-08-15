<template>
	<div class="header-menu">
		<ul class="menus" v-for="item in xiaomi">
			<li class="product">
				<img :src="item.imgUrl" alt="" class="product-img"/>
				<div class="product-name">{{item.name}}</div>
				<div class="product-price">
					{{item.price}}
				</div>
			</li>
		</ul>
	</div>
</template>

<script>
export default {
	data () {
		return {
			xiaomi: [
				{name: '小米手机Max', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/nav/maxdingbu!160x110.jpg', price: '1299元起'},
				{name: '小米手机5', imgUrl: 'http://c1.mifile.cn/f/i/16/goods/nav/mi5!160x110.jpg', price: '1499元起'},
				{name: '小米手机4c', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/nav/mi4c!160x110.jpg', price: '1099元'}
			]
		}
	}
}
</script>

<style>
.header-menu {
	width: 100%;
	height: 230px;
	background: #fff;
	.menus {
		list-style: none;
		margin: 0;
		padding: 0;
		padding-left: 150px;
		.product {
			float: left;
			width: 160px;
			.product-img {
				width: 160px;
				height: 110px;
			}
			.product-name {
				width: 160px;
				margin-top: 16px;
				font-size: 16px;
				text-align: center;
			}
		}
	}
}
</style>
