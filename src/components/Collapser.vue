<template>
    <div class="collapser">
      <div
        class="top"
        @click="onCollapserClick">
        <div class="title">{{label}}</div>
        <div class="icon-wrapper">
          <Icon color="#3F4352" :source="opened ? 'expand_less' : 'expand_more'"></Icon>
        </div>
      </div>
      <div class="body" v-show="opened">
        <slot></slot>
      </div>
    </div>
</template>

<script>
    import Icon from './Icon';

    export default {
      components: { Icon },
      name: "Collapser",
      props: {
          label: String,
          opened: Boolean
      },
      methods: {
        onCollapserClick() {
          this.$emit('update:opened', !this.opened)
        }
      }
    }
</script>

<style lang="less" scoped>
  @import "../styles/vars";

    .collapser {
      display: flex;
      width: 100%;
      flex-direction: column;
      box-shadow: @card-shadow;
      margin-bottom: @collapser-margin-bottom;

      .top {
        display: flex;
        width: 100%;
        height: 40px;
        align-items: center;

        background-color: white;
        .font-components-button-normal-alt-dark();

        & > div {
          display: flex;
          justify-content: center;
        }

        .title {
          flex: 1;
        }

        .icon-wrapper {
          width: 50px;
        }
      }

      .body {
        padding: @collapser-body-padding;
        background-color: white;
      }
    }
</style>
