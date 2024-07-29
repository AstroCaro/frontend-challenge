<script setup>
const props = defineProps(['placeholder', 'icon', 'color', 'option', 'src']);
</script>

<template>
  <div class="selector">
    <div v-if="icon" class="icon" :style="{ color: props.color }">
      <span class="material-symbols-outlined"> {{ props.icon }} </span>
    </div>
    <div v-else class="img">
      <img :src="props.src" alt="" />
    </div>
    <div class="select-placeholder">
      <div class="placeholder" :class="{ option: option }">
        {{ props.placeholder }}
      </div>
      <div v-if="props.option" class="option">{{ props.option }}</div>
    </div>
    <span class="material-symbols-outlined"> arrow_drop_down </span>
  </div>
</template>

<style scoped>
.selector {
  width: 100%;
  flex: 1;
  display: flex;
  align-items: center;
  gap: 16px;
  background-color: var(--color-background-form);
  padding: 12px 16px;
  border-radius: 4px;
  min-height: 54px;
  color: var(--color-text);
  border: none;
  font-size: 18px;
}

.img {
  height: 20px;
  margin-left: 12px;
  width: 14px;
}
.icon {
  display: flex;
}
.icon .material-symbols-outlined {
  font-size: 30px;
  font-weight: 200;
}
.material-symbols-outlined {
  margin: auto 0;
}
.select-placeholder {
  flex: 1;
}
.placeholder.option {
  font-size: 11px;
  font-weight: 200;
}
.option {
  font-size: 14px;
  font-weight: 400;
}
</style>
