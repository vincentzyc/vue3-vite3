<template>
  <van-popup v-model:show="show" class="agreement-popup" style="max-width: 576px" teleport="body" @closed="close">
    <div class="agreement-wrap">
      <iframe :src="text" frameborder="0" style="width: 100%; height: 100%"></iframe>
    </div>
    <div class="agreement-confirm" @click="close()">ζη₯ιδΊ</div>
  </van-popup>
</template>

<script setup lang="ts">
defineProps<{
  show: boolean;
  text: string;
}>();
const emit = defineEmits<{
  (e: "update:show", bool: boolean): void;
}>();
function close() {
  emit("update:show", false);
}
</script>
