<script setup>
defineProps({
  bg: {
    type: String,
    default: "bg-gray-100",
  },

});
</script>

<template>
    <!-- The wrapper component need the slot element to render the content inside -->
    <!-- the binding class is rendering inside the  string the bg property is dynamically coming  from the props  -->
    <div :class="`${bg} p-6 rounded-lg shadow-md`">
        <slot></slot>
    </div>

</template>