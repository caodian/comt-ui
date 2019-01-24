<template>
    <header class="zx-header" :style="{background: `${background}`, height: `${height}px`, color: `${fontColor}`}">
        <div class="zx-header-left">
            <slot name="overwriteLeft"></slot>
        </div>
        <h1 class="zx-header-title"
            :style="{ height: `${height}px`, lineHeight: `${height}px`, marginLeft: `${marginLeft}px`, marginRight: `${marginRight}px` }"
        >
            <slot>
                <span v-if="title">{{title}}</span>
            </slot>
        </h1>
        <div class="zx-header-right">
            <slot name="overwriteRight"></slot>
        </div>
    </header>
</template>

<script>
export default {
  name: 'md-header',
  props: {
    /**
     * 标题（默认为空）
     */
    title: {
      type: String,
      default: ''
    },
    /**
     * 头部高度
     */
    height: {
      type: Number,
      default: 88
    },
    /**
     * 标题左边距
     */
    marginLeft: {
      type: Number,
      default: 88
    },
    /**
     * 标题右边距
     */
    marginRight: {
      type: Number,
      default: 88
    },
    /**
     * 头部背景色
     */
    background: {
      type: String,
      default: '#e8302e'
    },
    /**
     * 头部字体颜色
     */
    fontColor: {
      type: String,
      default: '#fff'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .zx-header {
        position: relative;
        width: 100%;
        box-sizing: border-box;
    }
    .zx-header .zx-header-left {
        position: absolute;
        left: 18px;
        top: 28px;
    }
    .zx-header .zx-header-title {
        font-size: 30px;
        width: auto;
    }
    .zx-header .zx-header-title>span{
        display: inline-block;
        width: 100%;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
        text-align: center;
    }
    .zx-header .zx-header-right {
        position: absolute;
        right: 18px;
        top: 14px;
        font-size: 26px;
        line-height: 60px;
    }
</style>
