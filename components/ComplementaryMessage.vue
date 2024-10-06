<template>
  <div
    v-click
    :class="[
      'flex justify-center items-center gap-4 mt-4',
      textColor,
      {
        'p-4 border rounded-md': bordered,
        [borderColor]: bordered,
      },
    ]"
  >
    <light-icon :icon="icon" />
    <span class="text-center text-sm"><slot /></span>
  </div>
</template>

<script setup>
import { computed } from "vue";

const props = defineProps({
  bordered: {
    type: Boolean,
    default: false,
  },
  type: {
    type: String,
    default: "info",
  },
});

const icon = computed(() => {
  switch (props.type) {
    case "info":
      return "info-circle";
    case "alert":
      return "alert-triangle";
    case "success":
      return "circle-check";
    case "danger":
      return "circle-x";
  }
});

const textColor = computed(() => {
  switch (props.type) {
    case "info":
      return "text-sky-700 dark:text-sky-300";
    case "alert":
      return "text-amber-600 dark:text-amber-400";
    case "success":
      return "text-green-700 dark:text-green-400";
    case "danger":
      return "text-rose-700 dark:text-rose-400";
  }
});

const borderColor = computed(() => {
  switch (props.type) {
    case "info":
      return "border-sky-700 dark:border-sky-300";
    case "alert":
      return "border-amber-600 dark:border-amber-400";
    case "success":
      return "border-green-700 dark:border-green-400";
    case "danger":
      return "border-rose-700 dark:border-rose-400";
  }
});
</script>
