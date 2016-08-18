<template>
  <div class="boxs">
    <div class="boxs-top clearfix">
      <h3 class="top-title">智能硬件</h3>
      <span class="top-sub">
        查看全部
        <i class="sub-icon fa fa-fw fa-chevron-circle-right"></i>
      </span>
    </div>
    <div class="boxs-content">
      <div class="box-left">
        <img src="http://i3.mifile.cn/a4/57c2f4fb-6743-44c6-b447-6bd55aaeef89" alt="" />
      </div>
      <div class="box-right">
        <ul class="box-content">
          <li class="box" v-for="good in goods">
            <span></span>
            <img :src="good.imgUrl" alt="" />
            <h3 class="box-title">{{good.title}}</h3>
            <p class="box-desc">
              {{good.desc}}
            </p>
            <p class="price">
              {{good.price}}
            </p>
          </li>
        </ul>
      </div>
    </div>
	</div>
</template>

<script>
export default {
  data () {
    return {
      goods: [
        {imgUrl: 'http://i1.mifile.cn/a1/T1HcAQBgDT1RXrhCrK!220x220.jpg', title: '小米手环 光感版', desc: '实时监测心率，科学运动', price: '99元'},
        {imgUrl: 'http://i1.mifile.cn/a1/T1HcAQBgDT1RXrhCrK!220x220.jpg', title: '小米手环 光感版', desc: '实时监测心率，科学运动', price: '99元'},
        {imgUrl: 'http://i1.mifile.cn/a1/T1HcAQBgDT1RXrhCrK!220x220.jpg', title: '小米手环 光感版', desc: '实时监测心率，科学运动', price: '99元'},
        {imgUrl: 'http://i1.mifile.cn/a1/T1HcAQBgDT1RXrhCrK!220x220.jpg', title: '小米手环 光感版', desc: '实时监测心率，科学运动', price: '99元'},
        {imgUrl: 'http://i1.mifile.cn/a1/T1HcAQBgDT1RXrhCrK!220x220.jpg', title: '小米手环 光感版', desc: '实时监测心率，科学运动', price: '99元'},
        {imgUrl: 'http://i1.mifile.cn/a1/T1HcAQBgDT1RXrhCrK!220x220.jpg', title: '小米手环 光感版', desc: '实时监测心率，科学运动', price: '99元'},
        {imgUrl: 'http://i1.mifile.cn/a1/T1HcAQBgDT1RXrhCrK!220x220.jpg', title: '小米手环 光感版', desc: '实时监测心率，科学运动', price: '99元'},
        {imgUrl: 'http://i1.mifile.cn/a1/T1HcAQBgDT1RXrhCrK!220x220.jpg', title: '小米手环 光感版', desc: '实时监测心率，科学运动', price: '99元'}
      ]
    }
  }
}
</script>

<style scoped>
.boxs {
  position: relative;
  width: 1226px;
  height: auto;
  margin: 60px auto 0;
  background: #f5f5f5;
}

.boxs-top {
  width: 100%;
  height: 58px;
}

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
  display: block;
  font-size: 16px;
  line-height: 58px;
  color: #424242;
  cursor: pointer;
  .sub-icon {
    color: #b0b0b0;
    font-size: 20px;
  }
  &:hover {
    color: #ff6700;
    .sub-icon {
      color: #ff6700;
    }
  }
}

.box-left {
  float: left;
  width: 234px;
  height: 614px;
  cursor: pointer;
  transition: all 0.3s;
  &:hover {
    transform: translateY(-3px);
    box-shadow: 5px 5px 20px #ccc;
  }
}

.box-right {
  float: left;
  width: 978px;
  height: 628px;
  .box-content {
    display: flex;
    flex-flow: row wrap;
    justify-content: flex-start;
    width: 100%;
    height: 100%;
    background: #f5f5f5;
  }
  .box {
    padding: 0 0 14px 14px;
    background: #fff;
  }
}

</style>
