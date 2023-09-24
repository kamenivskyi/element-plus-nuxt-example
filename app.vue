<template>
  <div>
    <!-- BUTTONS COLOR CUSTOMISED USING SCSS -->
    <el-button @click="ElMessage('hello')">button</el-button>
    <ElButton :icon="ElIconEditPen" type="primary">button</ElButton>
    <LazyElButton type="warning">lazy button</LazyElButton>
  </div>

  <!-- DIALOG -->
  <ClientOnly>
    <el-button text @click="dialogVisible = true">
      Click to open Dialog
    </el-button>

    <el-dialog v-model="dialogVisible" title="Tips" width="30%" draggable :center="true">
      <span>It's a draggable Dialog</span>
      <template #footer>
        <span class="dialog-footer">
          <el-button @click="dialogVisible = false">Cancel</el-button>
          <el-button type="primary" @click="dialogVisible = false">
            Confirm
          </el-button>
        </span>
      </template>
    </el-dialog>
  </ClientOnly>
  
  <!-- TOOLTIP CUSTOMIZED -->
  <el-tooltip content="Bottom center" effect="customized">
    <el-button>Customized theme</el-button>
  </el-tooltip>
</template>

<script setup>
const dialogVisible = ref(false)
</script>

<style lang="scss">

.el-popper.is-customized {
  /* Set padding to ensure the height is 32px */
  padding: 6px 12px;
  background: linear-gradient(90deg, rgb(159, 229, 151), rgb(204, 229, 129));
}

.el-popper.is-customized .el-popper__arrow::before {
  background: linear-gradient(45deg, #b2e68d, #bce689);
  right: 0;
}
</style>