<template>
  <table class="table">
    <thead>
      <tr>
        <th scope="col">#</th>
        <th scope="col" style="width: 16rem;">Title</th>
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
          <div class="dropdown">
            <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton" data-bs-toggle="dropdown" aria-expanded="false">
              {{ selectedStatus }}
            </button>
            <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton">
              <li><a class="dropdown-item" href="#" @click.prevent="selectStatus('Backlog')">Backlog</a></li>
              <li><a class="dropdown-item" href="#" @click.prevent="selectStatus('LaunchPad')">LaunchPad</a></li>
              <li><a class="dropdown-item" href="#" @click.prevent="selectStatus('In Progress')">In Progress</a></li>
              <li><a class="dropdown-item" href="#" @click.prevent="selectStatus('Complete')">Complete</a></li>
              <li><a class="dropdown-item" href="#" @click.prevent="selectStatus('Archive')">Archive</a></li>
            </ul>
          </div>
        </td>
        <td>@mdo</td>
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
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'DropdownComponent',
  setup() {
    const selectedStatus = ref<string>('Launch Pad'); // Default dropdown button text

    // Function to update the dropdown button's text
    const selectStatus = (status: string) => {
      selectedStatus.value = status;
    };

    return { selectedStatus, selectStatus };
  },
});
</script>

<style scoped>
@import 'bootstrap/dist/css/bootstrap.css';
</style>
