<template>
  <div class="top-container">
		<div class="top-bar clearfix">
			<div class="topbar-nav">
				<ul class="nav-wrap">
					<li v-for="item in navs" class="nav clearfix">
						<a href="#" class="nav-name">{{item['name']}}</a>
						<span class="nav-separate" v-show="$index !== 8">|</span>
					</li>
				</ul>
			</div>
			<div class="topbar-info">
				<a href="#">登陆</a>
				<span class="nav-separate" v-show="$index !== 8">|</span>
				<a href="#">注册</a>
			</div>
			<div class="topbar-cart"
        @mouseenter="evtCartEnter"
        @mouseleave="evtCartOut">
				<div class="cart"
          :class="{'active': cartStatus}">
					<i class="icon-cart"></i>
					<a href="#">
						购物车(
						<span>0<span>
							)
					</a>
				</div>
				<div class="cart-list">
					购物车中还没有商品，赶快选购吧！
				</div>
			</div>

		</div>
  </div>
</template>

<script>
export default {
	data () {
		return {
			navs: [
				{'name': '小米商城'},
				{'name': 'MIUI'},
				{'name': '米聊'},
				{'name': '游戏'},
				{'name': '多看阅读'},
				{'name': '云服务'},
				{'name': '小米网移动版'},
				{'name': '问题反馈'},
				{'name': 'Select Region'}
			],
			timer: '',
			cartStatus: false
		}
	},
  ready () {
    console.log($(window).width())
  },
	methods: {
		evtCartEnter: function () {
      $('.cart-list').show()
      $('.cart-list').animate({
        'height': '96px',
        'opacity': '1'
      }, 300)
      clearInterval(this.timer)
		},
    evtCartOut: function () {
      this.timer = setTimeout(function () {
        $('.cart-list').animate({
          'height': '0',
          'opacity': '0'
        }, 300, function () {
          $('.cart-list').hide() // 动画执行完后隐藏该元素
        })
      }, 300)
    }
	},
	components: {
	}
}
</script>

<style scoped>

.top-container {
	width: 100%;
	height: 40px;
	background: #333;
}

.top-bar {
	position: relative;
	width: 1226px;
	margin: 0 auto;
	font-size: 12px;
}

.topbar-nav {
	float: left;
	display: inline-block;
	height: 40px;
	line-height: 40px;
	overflow: hidden;
}

.nav-wrap {
	display: inline-block;
	margin: 0;
	padding: 0;
	list-style: none;
	.nav {
		display: inline-block;
		text-decoration: none;
		height: 40px;
		line-height: 40px;
		padding-left: 5px;
		& :hover {
			color: #fff;
		}
		.nav-name {
			display: inline-block;
			font-size: 12px;
			color: #b0b0b0;
			text-decoration: none;
		}
		.nav-separate {
			display: inline-block;
			color: #b0b0b0;
			margin-left: 5px;
		}
	}
}

.topbar-info {
	position: absolute;
	top: 0;
	right: 140px;
	height: 40px;
	line-height: 40px;
	a {
		color: #b0b0b0;
		text-decoration: none;
    &:hover {
      color: #fff;
    }
	}
	span {
		color: #b0b0b0;
	}
}

.topbar-cart {
	position: relative;
	float: right;
	width: 120px;
	background: #424242;
	height: 40px;
	line-height: 40px;
	cursor: pointer;
	.active {
		background: #fff;
    a {
      color: #ff6700;
    }
    span {
      color: #ff6700;
    }
	}
	a {
		display: block;
		margin-left: 50px;
		color: #b0b0b0;
		text-decoration: none;
	}
	span {
		color: #b0b0b0;
	}
}

.cart-list {
  display: none;
	position: absolute;
	right: 0;
	top: 40px;
  width: 316px;
  height: 0;
  line-height: 96px;
	text-align: center;
	color: #b0b0b0;
	background: #fff;
	box-shadow: 0 0 5px #ccc;
  z-index: 10;
}
</style>
