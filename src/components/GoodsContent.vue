<template>
	<div class="product-container">
		<goods-header :title="title"></goods-header>
		<div class="box-bd">
			<ul class="content-list clearfix">
				<li>
					<template v-for="content in contents">
						<good-content-slide :content="content"></good-content-slide>
					</template>
				</li>
			</ul>
		</div>
	</div>
</template>

<script>
import GoodsHeader from './common/GoodsHeader'
import GoodsContentSlide from './common/GoodsContentSlide'
export default {
	data () {
		return {
			currPage: 0,
			title: '内容',
			contents: [
				{
					title: '图书',
					type: 'book',
					list: [
						{title: '哈利·波特与魔法石', desc: '哈利波特来了', imgUrl: '//i3.mifile.cn/a4/8e3584b6-3169-41c6-9356-939ec79aac2b', type: 0},
						{title: '特价专区', desc: '精选畅销好书，特价促销，天天更新，天天特价！', price: '限时优惠', imgUrl: '//i3.mifile.cn/a4/T1dlVgBbbT1RXrhCrK.jpg', type: 1},
						{title: '杂志专区', desc: '纸媒杂志＋互联网杂志，你想看的这都有！', price: '同步新刊上线', imgUrl: '//i3.mifile.cn/a4/T1R3WgBjKT1RXrhCrK.jpg', type: 1},
						{desc1: '海量好书，享受精品阅读时光', desc2: '漂亮的中文排版，千万读者选择！', btnTxt: '前往多看阅读', price: '限时优惠', imgUrl: '//s01.mifile.cn/i/index/more-duokan.jpg', type: 2}
					]
				},
				{
					title: '图书',
					type: 'book',
					list: [
						{title: '哈利·波特与魔法石', desc: '哈利波特来了', imgUrl: '//i3.mifile.cn/a4/8e3584b6-3169-41c6-9356-939ec79aac2b', type: 0},
						{title: '特价专区', desc: '精选畅销好书，特价促销，天天更新，天天特价！', price: '限时优惠', imgUrl: '//i3.mifile.cn/a4/T1dlVgBbbT1RXrhCrK.jpg', type: 1},
						{title: '杂志专区', desc: '纸媒杂志＋互联网杂志，你想看的这都有！', price: '同步新刊上线', imgUrl: '//i3.mifile.cn/a4/T1R3WgBjKT1RXrhCrK.jpg', type: 1},
						{desc1: '海量好书，享受精品阅读时光', desc2: '漂亮的中文排版，千万读者选择！', btnTxt: '前往多看阅读', price: '限时优惠', imgUrl: '//s01.mifile.cn/i/index/more-duokan.jpg', type: 2}
					]
				},
				{
					title: '图书',
					type: 'book',
					list: [
						{title: '哈利·波特与魔法石', desc: '哈利波特来了', imgUrl: '//i3.mifile.cn/a4/8e3584b6-3169-41c6-9356-939ec79aac2b', type: 0},
						{title: '特价专区', desc: '精选畅销好书，特价促销，天天更新，天天特价！', price: '限时优惠', imgUrl: '//i3.mifile.cn/a4/T1dlVgBbbT1RXrhCrK.jpg', type: 1},
						{title: '杂志专区', desc: '纸媒杂志＋互联网杂志，你想看的这都有！', price: '同步新刊上线', imgUrl: '//i3.mifile.cn/a4/T1R3WgBjKT1RXrhCrK.jpg', type: 1},
						{desc1: '海量好书，享受精品阅读时光', desc2: '漂亮的中文排版，千万读者选择！', btnTxt: '前往多看阅读', price: '限时优惠', imgUrl: '//s01.mifile.cn/i/index/more-duokan.jpg', type: 2}
					]
				},
				{
					title: '图书',
					type: 'book',
					list: [
						{title: '哈利·波特与魔法石', desc: '哈利波特来了', imgUrl: '//i3.mifile.cn/a4/8e3584b6-3169-41c6-9356-939ec79aac2b', type: 0},
						{title: '特价专区', desc: '精选畅销好书，特价促销，天天更新，天天特价！', price: '限时优惠', imgUrl: '//i3.mifile.cn/a4/T1dlVgBbbT1RXrhCrK.jpg', type: 1},
						{title: '杂志专区', desc: '纸媒杂志＋互联网杂志，你想看的这都有！', price: '同步新刊上线', imgUrl: '//i3.mifile.cn/a4/T1R3WgBjKT1RXrhCrK.jpg', type: 1},
						{desc1: '海量好书，享受精品阅读时光', desc2: '漂亮的中文排版，千万读者选择！', btnTxt: '前往多看阅读', price: '限时优惠', imgUrl: '//s01.mifile.cn/i/index/more-duokan.jpg', type: 2}
					]
				}]
		}
	},
	components: {
		'goods-header': GoodsHeader,
		'good-content-slide': GoodsContentSlide
	}
}
</script>

<style>
.product-container {
	width: 1226px;
	height: auto;
	margin: 0 auto;
}

.content-list {
	.content {
		position: relative;
		float: left;
		width: 296px;
		height: auto;
		margin: 0 0 14px 14px;
		padding-top: 45px;
		background: #fff;
		transition: all 0.3s;
		&:hover {
			transform: translateY(-3px);
			box-shadow: 5px 5px 20px #ccc;
		}
		&:nth-child(1) {
			margin-left: 0;
		}
	}
	.book {
		.title {
			color: #ffac13;
		}
	}
}

/*.content-list {
	.content {
		position: relative;
		float: left;
		width: 296px;
		height: auto;
		margin: 0 0 14px 14px;
		padding-top: 45px;
		background: #fff;
		transition: all 0.3s;
		&:hover {
			transform: translateY(-3px);
			box-shadow: 5px 5px 20px #ccc;
		}
		&:nth-child(1) {
			margin-left: 0;
		}
		.title {
			margin: 0 10px 18px;
			font-size: 16px;
			font-weight: 400;
			text-align: center;
		}
	}
	.book {
		.title {
			color: #ffac13;
		}
	}
}*/
</style>
