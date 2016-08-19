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
			<div class="goods-right">
				<ul class="goods-right-content">
					<template
						v-for="item in hotGoods"
						v-if="$index < hotGoods.length - 1">
						<li class="goods-right-item">
								<img :src="item.imgUrl" alt="" />
								<h3 class="goods-title">{{item.title}}</h3>
								<p class="goods-price">
									{{item.price}}元
									<span class="old-price">
										{{item.oldPrice}}元
									</span>
								</p>
								<p class="goods-rank">
									{{item.heat}}万人评价
								</p>
								<div
									v-show="item.reviewStatus"
									class="review">
									<span class="review-content">{{item.reviewDesc}}</span>
									<span class="review-author">来自于{{item.reviewAuthor}}的评价</span>
								</div>
						</li>
					</template>
					<ul class="goods-right-small">
						<li class="item-small">
							<div class="desc">
								<h3 class="title">
									{{hotGoods[hotGoods.length - 1].title}}
								</h3>
								<span class="price">
									{{hotGoods[hotGoods.length - 1].price}}元
								</span>
							</div>
							<img
								class="small-img"
								:src="hotGoods[hotGoods.length - 1].imgUrl" alt="" />
						</li>
						<li class="item-small read-more">
							<div class="desc">
								<h3 class="title">
									浏览更多
								</h3>
								<span class="price hot">
									热门
								</span>
							</div>
							<i class="fa fa-arrow-circle-right fa-4x icon-arrow"></i>
						</li>
					</ul>
				</ul>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data () {
		return {
			topSubStatus: 'hot',
			hotGoods: [
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米移动电源10000mAh 高配版', price: '129', oldPrice: '149', heat: '2',
				reviewDesc: '比我以前买的小米充电宝砖头好太多了！放在包里不占位置...', reviewAuthor: '龚毅祥', reviewStatus: true},
				{imgUrl: 'http://i2.mifile.cn/a1/T1eSZgBjVT1RXrhCrK.jpg?width=150&height=150', 'title': '小米小钢炮', price: '79'}
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
		margin-top: 16px;
		color: #424242;
		li {
			width: auto;
			height: 24px;
			line-height: 24px;
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

.goods-right {
	float: left;
	width: 992px;
	height: 628px;
	.goods-right-content {
		display: flex;
		flex-flow: row wrap;
		justify-content: flex-start;
		width: 100%;
		height: 100%;
	}
  .goods-right-item {
  	position: relative;
    margin: 0 0 14px 14px;
    padding: 20px 0;
    width: 234px;
    height: 260px;
    background: #fff;
    cursor: pointer;
    transition: all 0.3s;
    &:hover {
      transform: translateY(-1px);
      box-shadow: 5px 5px 20px #ccc;
			.review {
				height: 76px;
				opacity: 1;
			}
    }
    img {
      display: block;
      width: 160px;
      height: 160px;
      margin: 0 auto;
    }
    .goods-title {
      font-size: 14px;
      text-align: center;
      color: #333;
      font-weight:normal;
			text-overflow: ellipsis;
			white-space: nowrap;
			overflow: hidden;
    }
    .box-desc {
      margin: 0 10px 10px;
      height: 18px;
      font-size: 12px;
      text-align: center;
      text-overflow: ellipsis;
      white-space: nowrap;
      overflow: hidden;
      color: #b0b0b0;
    }
    .goods-price {
      color: #ff6700;
      font-size: 14px;
      text-align: center;
			.old-price {
				color: #b0b0b0;
				text-decoration: line-through;
			}
    }
		.goods-rank {
			margin: 0 10px;
			font-size: 12px;
			text-align: center;
			text-overflow: ellipsis;
			white-space: nowrap;
			overflow: hidden;
			color: #b0b0b0;
		}
  }

	.goods-right-small {
		width: 234px;
    height: 260px;
		.item-small {
			width: 234px;
			height: 143px;
			margin: 0 0 14px 14px;
			padding: 30px 0 0 30px;
			background: #fff;
	    cursor: pointer;
	    transition: all 0.3s;
			box-sizing: border-box;
	    &:hover {
	      transform: translateY(-1px);
	      box-shadow: 5px 5px 20px #ccc;
	    }
			.desc {
				float: left;
				width: 120px;
				height: 100%;
				.title {
					font-size: 14px;
					text-align: center;
					color: #333;
					font-weight: normal;
					text-overflow: ellipsis;
					white-space: nowrap;
					overflow: hidden;
				}
				.price {
					display: block;
					width: 100%;
					color: #ff6700;
			    font-size: 14px;
			    text-align: center;
				}
			}
			.small-img {
				float: left;
				width: 80px;
				height: 80px;
			}
		}
		.icon-arrow {
			margin-top: 5px;
			color: #ff6700;
		}
	}
}

.review {
	position: absolute;
	left: 0;
	bottom: 0;
	width: 234px;
	font-size: 12px;
	height: 0;
	line-height: 18px;
	overflow: hidden;
	box-sizing: border-box;
	color: #fff;
	background: #ff6700;
	opacity: 0;
	transition: all 0.3s;
	.review-content {
		display: block;
		text-align: center;
		margin: 8px 30px;
	}
	.review-author {
		display: block;
		text-align: center;
		margin-bottom: 8px;
	}
}
</style>
