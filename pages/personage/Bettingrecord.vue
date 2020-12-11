<template>
  <view class="Zhangchangerecord">
    <view  class="game-header normal">
      <view class="go-back" @click="goblick()" style="position: absolute;">
      </view>
      <view class="header-center">
        <p class="header-title">
          <span>投注记录</span>
        </p>
      </view>
      <view class="additional">
        <view class="uni-form-item uni-column">
          <picker @change="bindPickerChange" :range="array">
            <label class="shabx">{{array[index]}}</label>
          </picker>
        </view>
      </view>
    </view>
    <view class="hsatst">
      <view> << </view>
      <view class="adte">2020/11/27</view>
      <view> >> </view>
    </view>
    <view class="tbale">
      <view class="warp">
        <view class="box" style="background-color: rgba(0,0,0,.8);">
          <t-table :is-check="false" @change="change">
            <t-tr font-size="14" color="#fff" background-color: rgba(0,36,93,.5); align="center">
              <t-th align="center">期号</t-th>
              <t-th align="center">投注内容</t-th>
              <t-th align="center">状态</t-th>
              <t-th align="center">盈亏</t-th>
            </t-tr>
          </t-table>
        </view>
      </view>
    </view>
  </view>
</template>

<script>
import tTable from '@/components/t-table/t-table.vue';
import tTh from '@/components/t-table/t-th.vue';
import tTr from '@/components/t-table/t-tr.vue';
import tTd from '@/components/t-table/t-td.vue';
export default {
  data() {
    return {
      index: 0,
      array: [
        '澳洲5',
        '澳洲10',
        '极速时时彩',
        '极速赛车',
        '168飞艇',
        '英国赛车',
        '英国时时彩',
        '英国极速赛车',
        '英国极速时时彩'
      ],
      yx: ''
    };
  },
  components: {
    tTable,
    tTh,
    tTr,
    tTd
  },
  methods: {
    //下拉框
    bindPickerChange(e) {
      this.index = e.target.value
      this.yx = this.array[this.index]
    },
    change(e) {
      console.log(e.detail);
    },
    edit(item) {
      uni.showToast({
        title: item.name,
        icon: 'none'
      });
    },
    goblick() {
      uni.switchTab({
        url: '/pages/personage/index'
      });
    },
  }
}
</script>

<style lang="scss" scoped>
.Zhangchangerecord{
  width: 100%;
  position: fixed;
  height: 100vh;
  background-color: #f2f2f2;
  .game-header {
    position: relative;
    -ms-flex-negative: 0;
    flex-shrink: 0;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    height: 100rpx;
    background-size: 100% 100%;
    .additional {
      display: -webkit-box;
      display: -ms-flexbox;
      display: flex;
      -webkit-box-align: center;
      -ms-flex-align: center;
      align-items: center;
      position: absolute;
      top: 0;
      right: 0;
      height: 100%;
      z-index: 199;
      .uni-form-item{
        color: #ffffff;
        .shabx{
          margin-right: 30rpx;
        }
      }
    }
    .save-icon{
      width: 162rpx;
      height: 64rpx;
      background-image: url("../../static/img/userbc.png");
      background-size: 100% 100%;
      background-repeat: no-repeat;
    }
  }
  .normal{
    background-image: url("../../static/img/userheader.png");
  }
  .go-back{
    position: absolute;
    top:0;
    left: 0;
    width: 134rpx;
    height: 100rpx;
    background-image: url("../../static/img/userback.png");
    background-repeat: no-repeat;
    background-size: 100% 100%;
  }
  .header-center {
    -webkit-box-flex: 1;
    -ms-flex-positive: 1;
    flex-grow: 1;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    -ms-flex-direction: column;
    flex-direction: column;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    justify-content: center;
    .header-title {
      -webkit-box-flex: 1;
      -ms-flex-positive: 1;
      flex-grow: 1;
      text-align: center;
      font-size: 26rpx;
      color: #fff;
      text-shadow: 0 4rpx 0 0 rgba(0,0,0,.75);
      .add-info {
        font-size: 26rpx;
      }
    }
  }
  .hsatst{
    display: flex;
    width: 100%;
    height: 90rpx;
    justify-content: space-around;
    align-items: center;
    background-image: url("./../../static/img/headers2a.png");
    background-repeat: no-repeat;
    background-size: 100% 100%;
    color: #ffffff;
    .adte{
      color: #ffffff;
      font-size: 20rpx;
    }
  }
}

</style>
