<template>
  <div class="boxs-container">
    <div class="boxs">
      <div class="boxs-top clearfix">
        <h3 class="top-title">智能硬件</h3>
        <span class="top-sub">
          查看全部
          <i class="sub-icon fa fa-fw fa-chevron-circle-right"></i>
        </span>
      </div>
      <div class="boxs-content clearfix">
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
              <p class="box-price">
                {{good.price}}
              </p>
            </li>
          </ul>
        </div>
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
        {imgUrl: 'http://i3.mifile.cn/a4/T1rQAgB7Av1RXrhCrK.jpg', title: '小米路由器3', desc: '四天线设计，更安全更稳定', price: '149元'},
        {imgUrl: 'http://i1.mifile.cn/a1/pms_1464615180.86261317!220x220.jpg', title: '米兔智能故事机', desc: '实时监测心率，科学运动', price: '99元'},
        {imgUrl: 'http://i1.mifile.cn/a1/T1PXhgBbdT1RXrhCrK!220x220.jpg', title: '小米手环 光感版', desc: '实时监测心率，科学运动', price: '99元'},
        {imgUrl: 'http://i1.mifile.cn/a1/T17FCQByWv1RXrhCrK!220x220.jpg', title: '小米手环 光感版', desc: '实时监测心率，科学运动', price: '99元'},
        {imgUrl: 'http://i1.mifile.cn/a1/T1gRW_BjVv1RXrhCrK!220x220.jpg', title: '小米手环 光感版', desc: '实时监测心率，科学运动', price: '99元'},
        {imgUrl: 'http://i1.mifile.cn/a1/pms_1470730028.12443689!220x220.jpg', title: '小米手环 光感版', desc: '实时监测心率，科学运动', price: '99元'},
        {imgUrl: 'http://i1.mifile.cn/a1/T1GxCvBghT1RXrhCrK!220x220.jpg', title: '小米手环 光感版', desc: '实时监测心率，科学运动', price: '99元'}
      ]
    }
  }
}
</script>

<style scoped>

.boxs-container {
  width: 100%;
  height: auto;
  padding-top: 60px;
  margin-bottom: 26px;
  background: #f5f5f5;
}

.boxs {
  position: relative;
  width: 1226px;
  height: auto;
  margin: 0 auto;
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
    transform: translateY(-1px);
    box-shadow: 5px 5px 20px #ccc;
  }
}

.box-right {
  float: left;
  width: 992px;
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
    }
    img {
      display: block;
      width: 160px;
      height: 160px;
      margin: 0 auto;
    }
    .box-title {
      font-size: 14px;
      text-align: center;
      color: #333;
      font-weight:normal;
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
    .box-price {
      color: #ff6700;
      font-size: 14px;
      text-align: center;
    }
  }
}

</style>
