<template>
  <a-layout-header style="background: #fff; padding: 0">
    <menu-unfold-outlined
      v-if="collapsed"
      class="trigger"
      @click="toggleCollapse"
    />
    <menu-fold-outlined v-else class="trigger" @click="toggleCollapse" />
  </a-layout-header>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { MenuUnfoldOutlined, MenuFoldOutlined } from "@ant-design/icons-vue";

export default defineComponent({
  props: ["collapsed"],
  components: {
    MenuUnfoldOutlined,
    MenuFoldOutlined,
  },
  setup(props, { emit }) {
    const toggleCollapse = () => {
      emit("update:collapsed", !props.collapsed);
    };
    return { toggleCollapse };
  },
});
</script>

<style>
#components-layout-demo-custom-trigger .trigger {
  font-size: 18px;
  line-height: 64px;
  padding: 0 24px;
  cursor: pointer;
  transition: color 0.3s;
}

#components-layout-demo-custom-trigger .trigger:hover {
  color: #1890ff;
}

#components-layout-demo-custom-trigger .logo {
  height: 32px;
  background: rgba(255, 255, 255, 0.3);
  margin: 16px;
}

.site-layout .site-layout-background {
  background: #fff;
}
</style>
