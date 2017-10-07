---
title: new article
date: 2017-10-07 10:13:07
tags:
---
测试测试测试
===========

<!--more-->
``` bash
<template>
  <div class="kyg-button" :class="classes">
    <slot></slot>
  </div>
</template>
<script>
    export default {
        name: 'button',
        props:['type','disable'],
        computed:{
          classes(){
            return [this.type,this.disable?'disable':''];
          }
        }
    }
</script>
<style scoped rel="stylesheet/scss" lang="scss">
.kyg-button{
  color: white;
  text-align: center;

  &.primary{
    background-color: $color-button-normal;
  }

  &.disable{
    background-color: $color-button-disable;
    color: $color-font-3;
  }

  &:active{
    background-color: $color-button-click;
  }




}
</style>

```
