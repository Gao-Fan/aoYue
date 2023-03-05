<template>
  <div class="home-box">
    <div class="header">
      <div class="left">
        <img src="../assets/images/logo.png" alt="">
        <p>节点精灵</p>
      </div>
      <div class="right">
        <div class="btn active">首页</div>
        <div class="btn" @click="handleGoto('http://www.nspirit.cn/product/make.html')">节点圈</div>
        <div class="btn" @click="handleGoto('https://dwz.hm.baidu.com/redirect/vh78IkkX?target=vh78IkkX&d_t=10')">节点VIP</div>
        <div class="btn" @click="handleGoto('http://www.nspirit.cn/api/')">开发文档</div>
        <div class="btn dever" @click="handleGoto('http://card.nspirit.cn/admin/auth/login')">开发者中心</div>
      </div>
    </div>

    <div class="module module-swiper">
      <!-- 这里是轮播图 -->
      <el-carousel height="540px" :autoplay="true" :interval="3000" :loop="true">
        <el-carousel-item>
          <div class="banner_first banner_item">
            <div class="cover-module">
              <div class="download-btn" @click="handleGoto('http://card.nspirit.cn/getApk')">下载安装</div>
              <div class="record-btn" @click="handleGoto('http://www.nspirit.cn/product/app.html')">历史版本》</div>
            </div>
          </div>
        </el-carousel-item>

        <el-carousel-item>
          <div class="banner_second banner_item"></div>
        </el-carousel-item>


      </el-carousel>
    </div>

    <div class="module why-node">
      <div class="title">为什么选择节点</div>
      <div class="tabs-box">
        <el-tabs v-model="data.tabName" class="demo-tabs" @tab-click="handleClick">
          <el-tab-pane class="tab-page" label="免root小程序" name="tabA">免root小程序</el-tab-pane>
          <el-tab-pane class="tab-page" label="图像控件检索" name="tabB">图像控件检索</el-tab-pane>
          <el-tab-pane class="tab-page" label="深度学习" name="tabC">深度学习</el-tab-pane>
          <el-tab-pane class="tab-page" label="文字识别" name="tabD">文字识别</el-tab-pane>
          <el-tab-pane class="tab-page" label="免部署云数据库" name="tabE">免部署云数据库</el-tab-pane>
          <el-tab-pane class="tab-page" label="app独立打包" name="tabF">app独立打包</el-tab-pane>
        </el-tabs>
      </div>
    </div>

    <div class="module module-developer">
      <div class="title">
        <span>节点精灵开发者</span>
        <p @click="data.dialogVisible = true">专属认证标准</p>
      </div>

      <div class="user-list">
        <div class="ranking-item ranking-A">
          <div class="grade">
            <img class="badge" src="../assets/images/gold_medal.png" alt="">
            <div class="label">节点精灵院士</div>
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
            <div class="label">节点精灵教授</div>
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
    </div>

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
              <div @click="handleGoto('http://www.nspirit.cn/product/app.html')" class="tool-link">节点精灵APP >></div>
              <div @click="handleGoto('https://mumu.163.com/mac/index.html')" class="tool-link">mumu模拟器 >></div>
              <div @click="handleGoto('https://code.visualstudio.com/')" class="tool-link">vsCode开发工具 >></div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="module module-footer">
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
    <div class="contact-qq">
      <el-tooltip
        effect="dark"
        content="939874706"
        placement="left-start"
      >
        <img src="../assets/images/qq.png" alt="">
      </el-tooltip>
    </div>
    <el-dialog
      v-model="data.dialogVisible"
      title="认证标准"
      width="45%"
    >
      <p>普通开发者：节点精灵开放平台成功注册账户</p>
      <p>铜牌开发者：精通lua语法，通过lua语法测评题</p>
      <p>银牌开发者：成为铜牌开发者，通过节点精灵api专属测试题</p>
      <p>金牌开发者：成为银牌开发者，通过应用场景测试专属测试题</p>
      <p>荣誉开发者：成为金牌开发者，在节点精灵平台成功发布开发者软件，并通过专属测试题</p>
      <p>节点精灵教授：成为荣誉开发者，在节点精灵平台成功发布论文，并通过专属测试题</p>
      <p>节点精灵院士：成为节点精灵教授，对节点有重精灵开放平台作出重大贡献</p>
    </el-dialog>
  </div>
</template>
<script setup lang="ts">
import { reactive } from 'vue';
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

</script>
<style scoped lang="scss">
@import './styles/home.scss';
</style>

