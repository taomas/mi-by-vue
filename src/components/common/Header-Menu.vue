<template>
	<div class="header-menu">
		<ul class="menus">
			<li class="product" v-for="item in xiaomi">
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
			tid: '',
			xiaomi: [
				{name: '小米Max', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/nav/maxdingbu!160x110.jpg', price: '1299元起'},
				{name: '小米手机5', imgUrl: 'http://c1.mifile.cn/f/i/16/goods/nav/mi5!160x110.jpg', price: '1499元起'},
				{name: '小米手机4c', imgUrl: 'http://c1.mifile.cn/f/i/15/goods/nav/mi4c!160x110.jpg', price: '1099元'}
			]
		}
	},
	watch: {
		headerStatus: function (newVal, oldVal) {
			let $menu = $('.header-menu')
			if (newVal) {
				this.tid = setTimeout(function () {
					$menu.show()
					$menu.animate({
						height: '230px',
						opacity: '1'
					}, 300)
				}, 300)
			} else {
				clearTimeout(this.tid)
				$menu.animate({
					height: '0',
					opacity: '0'
				}, 300, function () {
					$menu.hide()
				})
			}
		}
	},
	props: {
		headerStatus: {
			type: Boolean
		}
	},
	methods: {
		evtEnter () {

		}
	}
}
</script>

<style>
.header-menu {
	display: none;
	width: 100%;
	height: 230px;
	background: #fff;
	box-shadow: 0 1px 5px #ccc;
	.menus {
		list-style: none;
		margin: 0;
		padding: 30px 0 0 150px;
		.product {
			float: left;
			width: 160px;
			.product-img {
				width: 100%;
				height: 110px;
			}
			.product-name {
				width: 100%;
				height: 16px;
				margin-top: 16px;
				font-size: 12px;
				text-align: center;
			}
			.product-price {
				width: 100%;
				height: 14px;
				margin-top: 10px;
				font-size: 10px;
				text-align: center;
				color: #ff6700;
			}
		}
	}
}
</style>
