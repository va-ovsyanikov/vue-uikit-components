<template>
  <div :class="addClass">
      <slot></slot>
  </div>
</template>
<script setup>
import {computed} from 'vue';
const props = defineProps({
  icon: {
    type: String,
    default: "",
  },
  disabled: {
    type: Boolean,
    default: false,
  },
});

//class
const addClass = computed(()=>{
	return{
		'list':true,
		'disabled': props.disabled
	}
})
</script>
<style lang="less" scoped>
.list {
  border: 1px solid var(--border);
  width: 541px;
  background-color: var(--white);
  border-radius: 4px;
  &__item {
    &:last-child {
      border-bottom: none;
    }
  }
  &__body {
    padding: 0 20px;
  }
}
.disabled {
  &.list {
    border: 1px solid var(--hints);
  }
}
</style>
