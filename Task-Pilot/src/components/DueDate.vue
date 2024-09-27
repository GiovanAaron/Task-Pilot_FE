// DueDate.vue
<template>
  <button type="button"  class="btn btn-primary" >{{ readableDate }}</button>
</template>

<script lang="ts">
import { computed } from 'vue';

export default {
  setup() {
    const isoDate = "2024-10-07T18:44:35.240Z";

    const date = new Date(isoDate);

    // Define abbreviated month names
    const monthNames = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sept", "Oct", "Nov", "Dec"];

    // Format it to a readable string
    const readableDate = computed(() => {
      return `${monthNames[date.getMonth()]} ${date.getDate()}, ${date.getFullYear()} ${date.toLocaleTimeString('en-US', { hour: '2-digit', minute: '2-digit', hour12: true })}`;
    });

    return { readableDate };
  }
}
</script>


<style>

    .btn-primary {
    background-color: #7e7a89; /* Default background color */
    border-color: #7e7a89; /* Default border color */
    }

    

</style>