<template>
  <a
    class="btn"
    :class="{
      full: props.full,
      primary: props.primary,
      secondary: props.secondary,
      outline: props.outline,
      color: props.color,
    }"
  >
    <div :style="{ 'background-color': props.background, color: props.color }">
      <span v-if="props.label">{{ props.label }}</span>
      <span
        v-if="props.icon"
        :class="{ 'btn-icon': props.icon && !props.outline }"
        class="material-symbols-outlined"
      >
        {{ props.icon }}
      </span>
    </div>
  </a>
</template>
<script setup>
const props = defineProps([
  'label',
  'icon',
  'full',
  'primary',
  'secondary',
  'outline',
  'background',
  'color',
]);
</script>
<style scoped>
.btn {
  display: flex;
  justify-content: center;
}
.btn > div {
  border-radius: 5px;
  padding: 10px !important;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 0.5rem;
  width: 100%;
  font-weight: 700;
}
.btn > div > span {
  text-transform: uppercase;
  font-size: 0.8rem;
  font-weight: 500;
}
.btn.full {
  flex: 1;
}

.btn.primary > div {
  background-color: #5762d5;
  color: white;
}

.btn.secondary > div {
  background-color: rgba(255, 255, 255, 0.05);
  color: white;
}
.btn.outline > div {
  border: 1px solid #5762d5;
}
.btn.green > div {
  background-color: #7ce5bb;
  color: black;
}

.btn-icon {
  font-variation-settings: 'FILL' 1;
}

.btn > div > .btn-icon {
  font-size: 18px;
  padding: 4px;
  /* background-color: #454da8; */
  border-radius: 4px;
}
</style>
