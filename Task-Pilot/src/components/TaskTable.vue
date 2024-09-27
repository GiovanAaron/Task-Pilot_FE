<script setup lang="ts">

import StatusButton from "@/components/StatusButton.vue"
import PriorityButton from "@/components/PriorityButton.vue"
import DifficultyToggle from "./DifficultyToggle.vue";
import DueDate from "./DueDate.vue";

</script>

<template>
  <table class="table">
    <thead>
      <tr>
        <th scope="col">#</th>
        <th scope="col" style="width: 16rem">Title</th>
        <th scope="col">Status</th>
        <th scope="col">Priority</th>
        <th scope="col">Difficulty</th>
        <th scope="col">Due</th>
        <th scope="col">-</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th scope="row">1</th>
        <td>Write introduction to the thesis la alalslald</td>
        <td>
          <StatusButton/>
        </td>
        <td><PriorityButton/></td>
        <td><DifficultyToggle/></td>
        <td><DueDate/></td>
      </tr>
      <tr>
        <th scope="row">2</th>
        <td>Jacob</td>
        <td>Thornton</td>
        <td>@fat</td>
      </tr>
      <tr>
        <th scope="row">3</th>
        <td>Larry</td>
        <td>the Bird</td>
        <td>@twitter</td>
      </tr>
    </tbody>
  </table>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'DropdownComponent',
  setup() {
    const selectedStatus = ref<string>('Launch Pad') // Default dropdown button text
    let statusColor = <string>'#FFFFFF' // Default dropdown button color
    // Function to update the dropdown button's text
    const selectStatus = (status: string) => {
      selectedStatus.value = status
    }

    const selectColor = (status: string) => {
      console.log('hi', status)

      switch (status) {
        case 'Backlog':
          statusColor = 'btn-backlog'
          break
        case 'Launch Pad':
          statusColor = 'btn-launchpad'
          break
        case 'In Progress':
          statusColor = 'btn-inprogress'
          break
        case 'Complete':
          statusColor = 'btn-complete'
          break
        case 'Archive':
          statusColor = 'btn-archive'
          break
      }
    }

    return { selectedStatus, selectStatus, selectColor, statusColor }
  }
})
</script>

<style>
.btn-backlog {
  background-color: #e0e0e0; /* Backlog background color */
  border-color: #bdbdbd; /* Darker border color */
}

.btn-backlog:hover {
  background-color: #bdbdbd; /* Darker hover background color */
  border-color: #9e9e9e; /* Even darker border color on hover */
}

/* LaunchPad Button */
.btn-launchpad {
  background-color: #d5b383; /* LaunchPad background color */
  border-color: #c39a5b; /* Darker border color */
}

.btn-launchpad:hover {
  background-color: #c39a5b; /* Darker hover background color */
  border-color: #a6784a; /* Even darker border color on hover */
}

/* In Progress Button */
.btn-inprogress {
  background-color: #b0c4cb; /* In Progress background color */
  border-color: #97a8af; /* Darker border color */
}

.btn-inprogress:hover {
  background-color: #97a8af; /* Darker hover background color */
  border-color: #7f8f96; /* Even darker border color on hover */
}

/* Complete Button */
.btn-complete {
  background-color: #a5dd91; /* Complete background color */
  border-color: #85be72; /* Darker border color */
}

.btn-complete:hover {
  background-color: #85be72; /* Darker hover background color */
  border-color: #6a9a5a; /* Even darker border color on hover */
}

/* Archive Button */
.btn-archive {
  background-color: #f3cfcf; /* Archive background color */
  border-color: #d9b1b1; /* Darker border color */
}

.btn-archive:hover {
  background-color: #d9b1b1; /* Darker hover background color */
  border-color: #b69393; /* Even darker border color on hover */
}
</style>
