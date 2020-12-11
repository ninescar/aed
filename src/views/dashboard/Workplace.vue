<template>
  <page-header-wrapper>
<!--    <template v-slot:content>-->
<!--      <div class="page-header-content">-->
<!--        <div class="avatar">-->
<!--          <a-avatar size="large" :src="currentUser.avatar"/>-->
<!--        </div>-->
<!--        <div class="content">-->
<!--          <div class="content-title">-->
<!--            {{ timeFix }}，{{ user.name }}<span class="welcome-text">，{{ welcome }}</span>-->
<!--          </div>-->
<!--          <div>前端工程师 | 蚂蚁金服 - 某某某事业群 - VUE平台</div>-->
<!--        </div>-->
<!--      </div>-->
<!--    </template>-->
<!--    <template v-slot:extraContent>-->
<!--      <div class="extra-content">-->
<!--        <div class="stat-item">-->
<!--          <a-statistic title="项目数" :value="56" />-->
<!--        </div>-->
<!--        <div class="stat-item">-->
<!--          <a-statistic title="团队内排名" :value="8" suffix="/ 24" />-->
<!--        </div>-->
<!--        <div class="stat-item">-->
<!--          <a-statistic title="项目访问" :value="2223" />-->
<!--        </div>-->
<!--      </div>-->
<!--    </template>-->

<!--    <div>-->
<!--      <a-row :gutter="24">-->
<!--        <a-col :xl="16" :lg="24" :md="24" :sm="24" :xs="24">-->
<!--          <a-card-->
<!--            class="project-list"-->
<!--            :loading="loading"-->
<!--            style="margin-bottom: 24px;"-->
<!--            :bordered="false"-->
<!--            title="进行中的项目"-->
<!--            :body-style="{ padding: 0 }">-->
<!--            <a slot="extra">全部项目</a>-->
<!--            <div>-->
<!--              <a-card-grid class="project-card-grid" :key="i" v-for="(item, i) in projects">-->
<!--                <a-card :bordered="false" :body-style="{ padding: 0 }">-->
<!--                  <a-card-meta>-->
<!--                    <div slot="title" class="card-title">-->
<!--                      <a-avatar size="small" :src="item.cover"/>-->
<!--                      <a>{{ item.title }}</a>-->
<!--                    </div>-->
<!--                    <div slot="description" class="card-description">-->
<!--                      {{ item.description }}-->
<!--                    </div>-->
<!--                  </a-card-meta>-->
<!--                  <div class="project-item">-->
<!--                    <a href="/#/">科学搬砖组</a>-->
<!--                    <span class="datetime">9小时前</span>-->
<!--                  </div>-->
<!--                </a-card>-->
<!--              </a-card-grid>-->
<!--            </div>-->
<!--          </a-card>-->

<!--          <a-card :loading="loading" title="动态" :bordered="false">-->
<!--            <a-list>-->
<!--              <a-list-item :key="index" v-for="(item, index) in activities">-->
<!--                <a-list-item-meta>-->
<!--                  <a-avatar slot="avatar" :src="item.user.avatar"/>-->
<!--                  <div slot="title">-->
<!--                    <span>{{ item.user.nickname }}</span>&nbsp;-->
<!--                    在&nbsp;<a href="#">{{ item.project.name }}</a>&nbsp;-->
<!--                    <span>{{ item.project.action }}</span>&nbsp;-->
<!--                    <a href="#">{{ item.project.event }}</a>-->
<!--                  </div>-->
<!--                  <div slot="description">{{ item.time }}</div>-->
<!--                </a-list-item-meta>-->
<!--              </a-list-item>-->
<!--            </a-list>-->
<!--          </a-card>-->
<!--        </a-col>-->
<!--        <a-col-->
<!--          style="padding: 0 12px"-->
<!--          :xl="8"-->
<!--          :lg="24"-->
<!--          :md="24"-->
<!--          :sm="24"-->
<!--          :xs="24">-->
<!--          <a-card title="快速开始 / 便捷导航" style="margin-bottom: 24px" :bordered="false" :body-style="{padding: 0}">-->
<!--            <div class="item-group">-->
<!--              <a>操作一</a>-->
<!--              <a>操作二</a>-->
<!--              <a>操作三</a>-->
<!--              <a>操作四</a>-->
<!--              <a>操作五</a>-->
<!--              <a>操作六</a>-->
<!--              <a-button size="small" type="primary" ghost icon="plus">添加</a-button>-->
<!--            </div>-->
<!--          </a-card>-->
<!--          <a-card-->
<!--            title="XX 指数"-->
<!--            style="margin-bottom: 24px"-->
<!--            :loading="radarLoading"-->
<!--            :bordered="false"-->
<!--            :body-style="{ padding: 0 }">-->
<!--            <div style="min-height: 400px;">-->
<!--              &lt;!&ndash; :scale="scale" :axis1Opts="axis1Opts" :axis2Opts="axis2Opts"  &ndash;&gt;-->
<!--              <radar :data="radarData"/>-->
<!--            </div>-->
<!--          </a-card>-->
<!--          <a-card :loading="loading" title="团队" :bordered="false">-->
<!--            <div class="members">-->
<!--              <a-row>-->
<!--                <a-col :span="12" v-for="(item, index) in teams" :key="index">-->
<!--                  <a>-->
<!--                    <a-avatar size="small" :src="item.avatar"/>-->
<!--                    <span class="member">{{ item.name }}</span>-->
<!--                  </a>-->
<!--                </a-col>-->
<!--              </a-row>-->
<!--            </div>-->
<!--          </a-card>-->
<!--        </a-col>-->
<!--      </a-row>-->
<!--    </div>-->
    <div id="aedMap">
      <div id="container" style="max-width:1500px;height:600px;position: relative">
        <a-button id="locBtn" icon="environment" @click="loc" style="position: fixed;bottom: 80px;right: 60px;z-index: 999"/>
      </div>
    </div>
  </page-header-wrapper>
</template>

<script>
// import { timeFix } from '@/utils/util'
// import { mapState } from 'vuex'
import { PageHeaderWrapper } from '@ant-design-vue/pro-layout'
import { Radar } from '@/components'

// import { getRoleList, getServiceList } from '@/api/manage'
//
// const DataSet = require('@antv/data-set')

export default {
  name: 'Workplace',
  components: {
    PageHeaderWrapper,
    Radar
  },
  data () {
    return {
      // timeFix: timeFix(),
      // avatar: '',
      // user: {},
      //
      // projects: [],
      // loading: true,
      // radarLoading: true,
      // activities: [],
      // teams: [],
      //
      // // data
      // axis1Opts: {
      //   dataKey: 'item',
      //   line: null,
      //   tickLine: null,
      //   grid: {
      //     lineStyle: {
      //       lineDash: null
      //     },
      //     hideFirstLine: false
      //   }
      // },
      // axis2Opts: {
      //   dataKey: 'score',
      //   line: null,
      //   tickLine: null,
      //   grid: {
      //     type: 'polygon',
      //     lineStyle: {
      //       lineDash: null
      //     }
      //   }
      // },
      // scale: [{
      //   dataKey: 'score',
      //   min: 0,
      //   max: 80
      // }],
      // axisData: [
      //   { item: '引用', a: 70, b: 30, c: 40 },
      //   { item: '口碑', a: 60, b: 70, c: 40 },
      //   { item: '产量', a: 50, b: 60, c: 40 },
      //   { item: '贡献', a: 40, b: 50, c: 40 },
      //   { item: '热度', a: 60, b: 70, c: 40 },
      //   { item: '引用', a: 70, b: 50, c: 40 }
      // ],
      // radarData: []
      location: '',
      aedMap: '',
      marker: '',
      locMarker: '//a.amap.com/jsapi_demos/static/demo-center/icons/poi-marker-default.png',
      locWindow: '',
      loccc: '123',
      allLoc: {
        lat: '',
        lng: '',
        formattedAddress: ''
      }
    }
  },
  computed: {
    // ...mapState({
    //   nickname: (state) => state.user.nickname,
    //   welcome: (state) => state.user.welcome
    // }),
    // currentUser () {
    //   return {
    //     name: 'Serati Ma',
    //     avatar: 'https://gw.alipayobjects.com/zos/antfincdn/XAosXuNZyF/BiazfanxmamNRoxxVxka.png'
    //   }
    // },
    // userInfo () {
    //   return this.$store.getters.userInfo
    // }
  },
  created () {
    // this.user = this.userInfo
    // this.avatar = this.userInfo.avatar
    //
    // getRoleList().then(res => {
    //   // console.log('workplace -> call getRoleList()', res)
    // })
    //
    // getServiceList().then(res => {
    //   // console.log('workplace -> call getServiceList()', res)
    // })
  },
  mounted () {
    // this.getProjects()
    // this.getActivity()
    // this.getTeams()
    // this.initRadar()
    this.init()
  },
  methods: {
    // getProjects () {
    //   this.$http.get('/list/search/projects')
    //     .then(res => {
    //       this.projects = res.result && res.result.data
    //       this.loading = false
    //     })
    // },
    // getActivity () {
    //   this.$http.get('/workplace/activity')
    //     .then(res => {
    //       this.activities = res.result
    //     })
    // },
    // getTeams () {
    //   this.$http.get('/workplace/teams')
    //     .then(res => {
    //       this.teams = res.result
    //     })
    // },
    // initRadar () {
    //   this.radarLoading = true
    //
    //   this.$http.get('/workplace/radar')
    //     .then(res => {
    //       const dv = new DataSet.View().source(res.result)
    //       dv.transform({
    //         type: 'fold',
    //         fields: ['个人', '团队', '部门'],
    //         key: 'user',
    //         value: 'score'
    //       })
    //
    //       this.radarData = dv.rows
    //       this.radarLoading = false
    //     })
    // }
    init () {
      const that = this
      // 步骤：定义map变量 调用 AMap.Map() 构造函数   获取地图显示容器
      that.aedMap = new window.AMap.Map(document.getElementById('container'), {
        resizeEnable: true,
        zoom: 13
      })
      // 定位
      // window.AMap.plugin('AMap.Geolocation', function () {
      //   that.location = new window.AMap.Geolocation({
      //     // 是否使用高精度定位，默认：true
      //     enableHighAccuracy: true,
      //     // 设置定位超时时间，默认：无穷大
      //     timeout: 10000,
      //     // 定位按钮的停靠位置的偏移量，默认：Pixel(10, 20)
      //     buttonOffset: new window.AMap.Pixel(10, 20),
      //     //  定位成功后调整地图视野范围使定位位置及精度范围视野内可见，默认：false
      //     zoomToAccuracy: true,
      //     //  定位按钮的排放位置,  RB表示右下
      //     buttonPosition: 'RB',
      //     // 自定义定位点样式
      //     markerOptions: {
      //       offset: new window.AMap.Pixel(-18, -36),
      //       content: '<img src="https://a.amap.com/jsapi_demos/static/resource/img/user.png" style="width:36px;height:36px"/>'
      //     }
      //   })
      //   that.aedMap.addControl(that.location)
      //   // 定位结果
      //   that.location.getCurrentPosition(function (status, result) {
      //     if (status === 'complete') {
      //       console.log(result)
      //       console.log(result.formattedAddress) // 地址（中文）
      //       console.log(result.position.lng) // 经度
      //       console.log(result.position.lat) // 纬度
      //     } else {
      //       console.log('定位失败')
      //     }
      //   })
      // })
    },
    loc () {
      const that = this
      // 定位
      window.AMap.plugin('AMap.Geolocation', function () {
        that.location = new window.AMap.Geolocation({
          // 是否展示按钮
          showButton: false,
          // 是否使用高精度定位，默认：true
          enableHighAccuracy: true,
          // 设置定位超时时间，默认：无穷大
          timeout: 10000,
          // 定位按钮的停靠位置的偏移量，默认：Pixel(10, 20)
          // buttonOffset: new window.AMap.Pixel(10, 20),
          //  定位成功后调整地图视野范围使定位位置及精度范围视野内可见，默认：false
          zoomToAccuracy: true,
          //  定位按钮的排放位置,  RB表示右下
          buttonPosition: 'RB',
          // 是否展示定位点
          showMarker: true,
          // 自定义定位点样式
          markerOptions: {
            offset: new window.AMap.Pixel(-13, -34),
            content: '<div id = "locMarker">' +
              '<img src="//a.amap.com/jsapi_demos/static/demo-center/icons/poi-marker-default.png" style="width:26px;height:34px"/>' +
              '</div>'
          }
        })
        that.aedMap.addControl(that.location)
        // 定位结果
        that.location.getCurrentPosition(function (status, result) {
          if (status === 'complete') {
            console.log(result)
            that.allLoc.formattedAddress = result.formattedAddress
            console.log(result.formattedAddress) // 地址（中文）
            that.allLoc.lng = result.position.lng
            console.log(that.allLoc.lng) // 经度
            that.allLoc.lat = result.position.lat
            console.log(that.allLoc.lat) // 纬度
          } else {
            console.log('定位失败')
          }
        })
      })
      // 定位点
      // that.marker = new window.AMap.Marker({
      //   position: [that.lng, that.lat],
      //   offset: new window.AMap.Pixel(-18, -36),
      //   icon: that.locMarker,
      //   imageSize: new window.AMap.Size(25, 34)
      // })
      // that.marker.setMap(that.aedMap)
      // let Mc = Vue.extend({
      //   template: '<a>qiuqiunile</a>'
      // })
      setTimeout(function () {
        console.log(that.allLoc.lng + '??')
      }, 4000)
      // const mm = new Info().$mount()
      // 创建消息窗口
      that.locWindow = new window.AMap.AdvancedInfoWindow({
        map: that.aedMap,
        position: [113.53467, 22.35002],
        anchor: 'bottom-center',
        offset: new window.AMap.Pixel(-1, -40),
        placeSearch: false,
        asDestination: false,
        driving: false,
        transit: false,
        content: that.$refs.infowindow.$el
      })
      that.locWindow.open(that.aedMap)
      // this.content = '<infoWindow/>'
      // this.locWindow.open()
      // this.locWindow.setPosition(this.aedMap.getCenter()) // 设置信息窗口的坐标
      // this.locWindow.setContent() // 设置信息窗口的内容
      // $('#aaa').append(mm.$el)
      // window.document.getElementById('submit').addEventListener('click', function () {
      //   setTimeout(function () {
      //     alert('jh')
      //   }, 400)
      // })
    }
  }
}
</script>

<style lang="less" scoped>
  @import "./Workplace.less";

  .project-list {

    .card-title {
      font-size: 0;

      a {
        color: rgba(0, 0, 0, 0.85);
        margin-left: 12px;
        line-height: 24px;
        height: 24px;
        display: inline-block;
        vertical-align: top;
        font-size: 14px;

        &:hover {
          color: #1890ff;
        }
      }
    }

    .card-description {
      color: rgba(0, 0, 0, 0.45);
      height: 44px;
      line-height: 22px;
      overflow: hidden;
    }

    .project-item {
      display: flex;
      margin-top: 8px;
      overflow: hidden;
      font-size: 12px;
      height: 20px;
      line-height: 20px;

      a {
        color: rgba(0, 0, 0, 0.45);
        display: inline-block;
        flex: 1 1 0;

        &:hover {
          color: #1890ff;
        }
      }

      .datetime {
        color: rgba(0, 0, 0, 0.25);
        flex: 0 0 auto;
        float: right;
      }
    }

    .ant-card-meta-description {
      color: rgba(0, 0, 0, 0.45);
      height: 44px;
      line-height: 22px;
      overflow: hidden;
    }
  }

  .item-group {
    padding: 20px 0 8px 24px;
    font-size: 0;

    a {
      color: rgba(0, 0, 0, 0.65);
      display: inline-block;
      font-size: 14px;
      margin-bottom: 13px;
      width: 25%;
    }
  }

  .members {
    a {
      display: block;
      margin: 12px 0;
      line-height: 24px;
      height: 24px;

      .member {
        font-size: 14px;
        color: rgba(0, 0, 0, .65);
        line-height: 24px;
        max-width: 100px;
        vertical-align: top;
        margin-left: 12px;
        transition: all 0.3s;
        display: inline-block;
      }

      &:hover {
        span {
          color: #1890ff;
        }
      }
    }
  }

  .mobile {

    .project-list {

      .project-card-grid {
        width: 100%;
      }
    }

    .more-info {
      border: 0;
      padding-top: 16px;
      margin: 16px 0 16px;
    }

    .headerContent .title .welcome-text {
      display: none;
    }
  }

</style>
