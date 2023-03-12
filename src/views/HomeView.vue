<template>
  <div class="contact-qq">
      <el-popover placement="right" :width="200" trigger="hover">
        <template #reference>
          <img src="../assets/images/we_chart_logo.png" alt="">
        </template>
        <div>
          <img src="../assets/images/we_chart.png" alt="">
        </div>
      </el-popover>
    </div>
  <div class="home-box" id="homeBox" ref="fullPageBox">
    <div class="header">
      <div class="left">
        <img src="../assets/images/logo.png" alt="">
        <p>AirScript</p>
      </div>
      <div class="right">
        <div class="btn active">首页</div>
        <div class="btn" @click="handleGoto('http://www.nspirit.cn/product/make.html')">AirScript圈</div>
        <div class="btn" @click="handleGoto('https://dwz.hm.baidu.com/redirect/vh78IkkX?target=vh78IkkX&d_t=10')">AirScriptVIP</div>
        <div class="btn" @click="handleGoto('http://www.nspirit.cn/api/')">开发文档</div>
        <div class="btn dever" @click="handleGoto('http://card.nspirit.cn/admin/auth/login')">开发者中心</div>
      </div>
    </div>

    <div class="fullPageContainer" ref="fullPageContainer" @mousewheel="mouseWheelHandle">
      <div class="module module-swiper">
        <!-- 这里是轮播图 -->
        <el-carousel height="100vh" :autoplay="true" :interval="3000" :loop="true">
          <el-carousel-item>
            <div class="banner_first banner_item">
              <div class="iphone-img">
                <img src="../assets/images/banner_iphone.png" alt="">
              </div>
              <div class="cover-module">
                <div class="introduce">
                  <div class="tip">免ROOT，安卓平台运行，自动化工具</div>
                  <div class="items">lua语言开发｜零门槛学习｜前沿的AI技术｜任意脚本均可运行</div>
                </div>
                <div class="link-box">
                  <div class="qr-code">
                    <img src="../assets/images/banner_qr_code.png" alt="" />
                    <p>扫码下载</p>
                  </div>
                  <div class="btns">
                    <div class="download-btn" @click="handleGoto('http://card.nspirit.cn/getApk')">下载安装</div>
                    <div class="record-btn" @click="handleGoto('http://www.nspirit.cn/product/app.html')">历史版本》</div>
                  </div>
                </div>
              </div>
            </div>
          </el-carousel-item>

          <!-- <el-carousel-item>
            <div class="banner_second banner_item"></div>
          </el-carousel-item> -->


        </el-carousel>
      </div>

      <div class="module why-node">
        <div class="title">为什么选择AirScript</div>
        <div class="tabs-box">
          <el-tabs v-model="data.tabName" class="demo-tabs" @tab-click="handleClick">
            <el-tab-pane class="tab-page" label="免root小程序" name="tabA">
              <div class="video-box">
                <video src="../assets/images/80_1678367293.mp4" controls></video>
              </div>
            </el-tab-pane>
            <el-tab-pane class="tab-page" label="图像控件检索" name="tabB">
              <div class="video-box">
                <video src="../assets/images/80_1678367293.mp4" controls></video>
              </div>
            </el-tab-pane>
            <el-tab-pane class="tab-page" label="深度学习" name="tabC">
              <div class="video-box">
                <video src="../assets/images/80_1678367293.mp4" controls></video>
              </div>
            </el-tab-pane>
            <el-tab-pane class="tab-page" label="文字识别" name="tabD">
              <div class="video-box">
                <video src="../assets/images/80_1678367293.mp4" controls></video>
              </div>
            </el-tab-pane>
            <el-tab-pane class="tab-page" label="免部署云数据库" name="tabE">
              <div class="video-box">
                <video src="../assets/images/80_1678367293.mp4" controls></video>
              </div>
            </el-tab-pane>
            <el-tab-pane class="tab-page" label="app独立打包" name="tabF">
              <div class="video-box">
                <video src="../assets/images/80_1678367293.mp4" controls></video>
              </div>
            </el-tab-pane>
          </el-tabs>
        </div>
      </div>

      <!-- <div class="module module-developer">
        <div class="title">
          <span>AirScript开发者</span>
          <p @click="data.dialogVisible = true">专属认证标准</p>
        </div>

        <div class="user-list">
          <div class="ranking-item ranking-A">
            <div class="grade">
              <img class="badge" src="../assets/images/gold_medal.png" alt="">
              <div class="label">AirScript院士</div>
            </div>
            <div class="users">
              <div class="user-item" v-for="(userItem, index) in data.ranking['A']" :key="index">
                <div class="avatar">
                  <img :src="userItem.userAvatar" alt="">
                </div>
                <span class="user-name">{{ userItem.userName }}</span>
              </div>
            </div>
          </div>

          <div class="ranking-item ranking-B">
            <div class="grade">
              <img class="badge" src="../assets/images/silver_medal.png" alt="">
              <div class="label">AirScript教授</div>
            </div>
            <div class="users">
              <div class="user-item" v-for="(userItem, index) in data.ranking['B']" :key="index">
                <div class="avatar">
                  <img :src="userItem.userAvatar" alt="">
                </div>
                <span class="user-name">{{ userItem.userName }}</span>
              </div>
            </div>
          </div>

          <div class="ranking-item ranking-C">
            <div class="grade">
              <img class="badge" src="../assets/images/bronze_medal.png" alt="">
              <div class="label">荣誉开发者</div>
            </div>
            <div class="users">
              <div class="user-item" v-for="(userItem, index) in data.ranking['C']" :key="index">
                <div class="avatar">
                  <img :src="userItem.userAvatar" alt="">
                </div>
                <span class="user-name">{{ userItem.userName }}</span>
              </div>
            </div>
          </div>

          <div class="ranking-item ranking-D">
            <div class="grade">
              <div class="badge">4</div>
              <div class="label">金牌开发者</div>
            </div>
            <div class="users">
              <div class="user-item" v-for="(userItem, index) in data.ranking['D']" :key="index">
                <div class="avatar">
                  <img :src="userItem.userAvatar" alt="">
                </div>
                <span class="user-name">{{ userItem.userName }}</span>
              </div>
            </div>
          </div>

          <div class="ranking-item ranking-E">
            <div class="grade">
              <div class="badge">5</div>
              <div class="label">银牌开发者</div>
            </div>
            <div class="users">
              <div class="user-item" v-for="(userItem, index) in data.ranking['E']" :key="index">
                <div class="avatar">
                  <img :src="userItem.userAvatar" alt="">
                </div>
                <span class="user-name">{{ userItem.userName }}</span>
              </div>
            </div>
          </div>

          <div class="ranking-item ranking-F">
            <div class="grade">
              <div class="badge">6</div>
              <div class="label">铜牌开发者</div>
            </div>
            <div class="users">
              <div class="user-item" v-for="(userItem, index) in data.ranking['F']" :key="index">
                <div class="avatar">
                  <img :src="userItem.userAvatar" alt="">
                </div>
                <span class="user-name">{{ userItem.userName }}</span>
              </div>
            </div>
          </div>

          <div class="develop-income">
            <div class="gradient-line"></div>
            <div class="develop-income-item user-count">共有<span class="number">7069</span>名开发者</div>
            <div class="develop-income-item income">累计收益：<span class="number">1982791.00</span>元</div>
          </div>
        </div>

        <div class="developer-square">
          <div class="btn" @click="handleGoto('http://card.nspirit.cn/admin/auth/login')">开发者中心</div>
        </div>
      </div> -->

      <div class="module module-guide">
        <div class="title">新手入门</div>
        <div class="guide-content">
          <div class="guide-video-box shadow-box">
            <div class="video-content">
              <img src="../assets/images/play_btn.png" alt="">
            </div>
            <div class="video-label">Lua语言零基础学习，轻松掌握api使用技巧，快速获得实战能力</div>
          </div>
          <div class="guide-tool shadow-box">
            <div class="tool-item">
              <div class="icon">
                <img src="../assets/images/guide_tool_A.png" alt="">
              </div>
              <div class="tool-list">
                <div class="tool-title">文档说明</div>
                <div class="tool-link">定制脚本文档 >></div>
                <div @click="handleGoto('http://www.nspirit.cn/about/web/mzsm.html')" class="tool-link">免责声明 >></div>
                <div class="tool-link">隐私条款 >></div>
              </div>
            </div>
            <div class="tool-item">
              <div class="icon">
                <img src="../assets/images/guide_tool_B.png" alt="">
              </div>
              <div class="tool-list">
                <div class="tool-title">开发指南</div>
                <div class="tool-link">lua基本语法学习指南 >></div>
                <div @click="handleGoto('http://www.nspirit.cn/api/cloud.html')" class="tool-link">云控对接操作指南 >></div>
                <div @click="handleGoto('http://www.nspirit.cn/api/db.html')" class="tool-link">数据库对接操作指南 >></div>
                <div @click="handleGoto('http://www.nspirit.cn/api/plugsread.html')" class="tool-link">插件库 >></div>
              </div>
            </div>
            <div class="tool-item">
              <div class="icon">
                <img src="../assets/images/guide_tool_C.png" alt="">
              </div>
              <div class="tool-list">
                <div class="tool-title">插件库</div>
                <div @click="handleGoto('http://www.nspirit.cn/product/app.html')" class="tool-link">AirScriptAPP >></div>
                <div @click="handleGoto('https://mumu.163.com/mac/index.html')" class="tool-link">mumu模拟器 >></div>
                <div @click="handleGoto('https://code.visualstudio.com/')" class="tool-link">vsCode开发工具 >></div>
              </div>
            </div>
          </div>
        </div>

        <div class="module-footer">
          <div class="record-no">
            @2019-2022 aoyue tec 京ICP备2020040944号-2
          </div>
          <div class="footer-link">
            <span>联系我们</span> ｜
            <span @click="handleGoto('http://www.nspirit.cn/about/web/mzsm.html')">免责声明</span> ｜
            <span @click="handleGoto('http://www.nspirit.cn/about/web/yhxy.html')">用户协议</span> ｜
            <span @click="handleGoto('http://www.nspirit.cn/about/web/kfzxy.html')">开发者协议</span> ｜
            <span>隐私协议</span>
          </div>
        </div>
      </div>


      <!-- <div class="contact-qq">
        <el-popover placement="right" :width="200" trigger="hover">
          <template #reference>
            <img src="../assets/images/we_chart_logo.png" alt="">
          </template>
          <div>
            <img src="../assets/images/we_chart.png" alt="">
          </div>
        </el-popover>
      </div> -->

      <el-dialog
        v-model="data.dialogVisible"
        title="认证标准"
        width="45%"
      >
        <p>普通开发者：AirScript开放平台成功注册账户</p>
        <p>铜牌开发者：精通lua语法，通过lua语法测评题</p>
        <p>银牌开发者：成为铜牌开发者，通过AirScriptapi专属测试题</p>
        <p>金牌开发者：成为银牌开发者，通过应用场景测试专属测试题</p>
        <p>荣誉开发者：成为金牌开发者，在AirScript平台成功发布开发者软件，并通过专属测试题</p>
        <p>AirScript教授：成为荣誉开发者，在AirScript平台成功发布论文，并通过专属测试题</p>
        <p>AirScript院士：成为AirScript教授，对AirScript开放平台作出重大贡献</p>
      </el-dialog>
    </div>
  </div>
</template>
<script setup lang="ts">
import Loadsh from 'lodash'
import { reactive, ref } from 'vue';
import type { TabsPaneContext } from 'element-plus'

const data = reactive({
  dialogVisible: false,
  tabName: 'tabA',
  test: 'hello world',
  ranking: {
    A: [
      { userName: '王雪', userAvatar: 'https://img.js.design/assets/img/63992c0a668ab75c39105bb0.png' }
    ],
   
    B: [
      { userName: '王菲', userAvatar: 'https://img.js.design/assets/img/63992c0a80dec50614d35a9d.png' },
      { userName: '利好', userAvatar: 'https://img.js.design/assets/img/63992c0a080d94a295270790.png' }
    ],
    C: [
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a80dec50614d35a9d.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0ae1aa7f47d07c3a8f.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a080d94a295270790.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a97161508069ae34d.png' }
    ],
    D: [
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a80dec50614d35a9d.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0ae1aa7f47d07c3a8f.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a080d94a295270790.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a97161508069ae34d.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a080d94a295270790.png' }
    ],
    E: [
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a80dec50614d35a9d.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a080d94a295270790.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a080d94a295270790.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0ae1aa7f47d07c3a8f.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a80dec50614d35a9d.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a080d94a295270790.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a080d94a295270790.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a080d94a295270790.png' }
    ],
    F: [
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a80dec50614d35a9d.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a080d94a295270790.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a080d94a295270790.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a97161508069ae34d.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a80dec50614d35a9d.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a080d94a295270790.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0a97161508069ae34d.png' },
      { userName: '哥布林', userAvatar: 'https://img.js.design/assets/img/63992c0ae1aa7f47d07c3a8f.png' }
    ],
  }
})

const handleClick = (tab: TabsPaneContext, event: Event) => {
  console.log(tab, event)
}
const handleGoto = (url: string) => {
  window.open(url)
}


// 滚动事件
const move = (index: number) => {
  fullpage.isScrolling = true; // 为了防止滚动多页，需要通过一个变量来控制是否滚动
  console.log('滚动', fullpage.isScrolling)
  directToMove(index); //执行滚动
  setTimeout(() => {  //这里的动画是1s执行完，使用setTimeout延迟1s后解锁
    fullpage.isScrolling = false
  }, 1410)
}
const fullpage = reactive({
  current: 1, // 当前的页面编号
  isScrolling: false, // 是否在滚动,是为了防止滚动多页，需要通过一个变量来控制是否滚动
  deltaY: 0 // 返回鼠标滚轮的垂直滚动量，保存的鼠标滚动事件的deleteY,用来判断是往下还是往上滚
})

const fullPageBox = ref(null);
const fullPageContainer = ref(null);
// 执行滚动
const directToMove = (index: number) => {
  let height = fullPageBox.value.clientHeight; //获取屏幕的高度
  let scrollPage = fullPageContainer // 获取执行tarnsform的元素
  let scrollHeight; // 计算滚动的告诉，是往上滚还往下滚
  scrollHeight = -(index - 1) * height + 'px'
  scrollPage.value.style.transform = `translateY(${scrollHeight})`  
  fullpage.current = index;
}

const next = () => {
  let len = 3; // 页面的个数
  if (fullpage.current + 1 <= len) { // 如果当前页面编号+1 小于总个数，则可以执行向下滑动
    fullpage.current += 1; // 页面+1
    move(fullpage.current); // 执行切换
  }
}
// 往上切换
const pre = () => {
  if (fullpage.current - 1 > 0) { // 如果当前页面编号-1 大于0，则可以执行向下滑动
    fullpage.current -= 1;// 页面+1
    move(fullpage.current);// 执行切换
  }
}

const mouseWheelHandle = (event: any) => {
  let evt = event || window.event;
  // evt.stopPropagation();
  if (evt.stopPropagation) {
    evt.stopPropagation();
  } else {
    evt.returnValue = false;
  }

  if (fullpage.isScrolling) {
    return false
  }
  Loadsh.throttle(() => { console.log('校验', fullpage.isScrolling) }, 400)
  
  let e = event.originalEvent || event;
  fullpage.deltaY = e.deltaY || e.detail; // Firefox使用detail
  // fullpage.isScrolling = true
  if (fullpage.deltaY > 0) {
    console.log('AA')
    next()
  } else if (fullpage.deltaY < 0) {
    pre()
  }
}

</script>
<style scoped lang="scss">
@import './styles/home.scss';
</style>

