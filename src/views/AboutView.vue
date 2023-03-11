<template>
  <div class="fullPage" ref="fullPage">
    <div
        class="fullPageContainer"
        ref="fullPageContainer"
        @mousewheel="mouseWheelHandle"
        @DOMMouseScroll="mouseWheelHandle"
    >
      <div class="section section1">1</div>
      <div class="section section2">2</div>
      <div class="section section3">3</div>
      <div class="section section4">4</div>
    </div>
  </div>
</template>
<script setup lang="ts">
import { ref } from 'vue';

const fullpage = {
  current: 1, // 当前的页面编号
        isScrolling: false, // 是否在滚动,是为了防止滚动多页，需要通过一个变量来控制是否滚动
        deltaY: 0 // 返回鼠标滚轮的垂直滚动量，保存的鼠标滚动事件的deleteY,用来判断是往下还是往上滚
}

let startTime = undefined // 记录触摸开始的时间
let startX = undefined // 记录触摸开始的X坐标，本次主要实现的是上下滑动，所以当前坐标不做强制要求
let startY = undefined // 记录触摸开始的Y坐标

// 滚动事件
const move = (index) => {
      fullpage.isScrolling = true; // 为了防止滚动多页，需要通过一个变量来控制是否滚动
      directToMove(index); //执行滚动
      setTimeout(() => {  //这里的动画是1s执行完，使用setTimeout延迟1s后解锁
        fullpage.isScrolling = false;
      }, 1010)
    }

    const fullPage = ref(null);
    const fullPageContainer = ref(null);
	// 执行滚动
    const directToMove = (index) => {
      let height = fullPage.value.clientHeight; //获取屏幕的宽度
      let scrollPage = fullPageContainer // 获取执行tarnsform的元素
      let scrollHeight; // 计算滚动的告诉，是往上滚还往下滚
      scrollHeight = -(index - 1) * height + "px";
      scrollPage.value.style.transform = `translateY(${scrollHeight})`;
      fullpage.current = index;
    }

    const next = () => {
      let len = 4; // 页面的个数
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
  // 添加冒泡阻止
  let evt = event || window.event;
  if (evt.stopPropagation) {
    evt.stopPropagation();
  } else {
    evt.returnValue = false;
  }
  console.log('71', fullpage.isScrolling)
  
  if (fullpage.isScrolling) { // 判断是否可以滚动
    return false;
  }
  let e = event.originalEvent || event;
  fullpage.deltaY = e.deltaY || e.detail; // Firefox使用detail
  if (fullpage.deltaY > 0) {
    next()
  } else if (fullpage.deltaY < 0) {
    pre()
  }
}

</script>
<style scoped lang="scss">
.fullPage {
  height: 100vh; //一定要设置，保证占满
  overflow: hidden; //一定要设置，多余的先隐藏
  background-color: rgb(189, 211, 186);
}

.fullPageContainer {
  width: 100%;
  height: 100vh;
  transition: all linear 0.5s;
}

.section {
  width: 100%;
  height: 100vh;
  background-position: center center;
  background-repeat: no-repeat;
}

//下面的只是为了区分每个页面的背景颜色
.section1 {
  background-color: rgb(189, 211, 186);
}

.section2 {
  background-color: rgb(44, 48, 43);
}

.section3 {
  background-color: rgb(116, 104, 109);
}

.section4 {
  background-color: rgb(201, 202, 157);
}
</style>
