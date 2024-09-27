<template>
  <div class="dropdown" @clickoutside="collapseDropdown">
    <button
      page="2334"
      id="dropdownMenuButton"
      type="button"
      :class="['dropdown-toggle', buttonClass]"
      @click="toggleDropdown"
      :aria-expanded="isExpanded.toString()"
    >
      {{ selectedStatus }}
    </button>
    <ul v-if="isExpanded" class="dropdown-menu show">
      <li>
        <a class="dropdown-item" href="#" @click.prevent="selectStatus('Backlog', $event)"
          >Backlog</a
        >
      </li>
      <li>
        <a class="dropdown-item" href="#" @click.prevent="selectStatus('Launch Pad', $event)"
          >Launch Pad</a
        >
      </li>
      <li>
        <a class="dropdown-item" href="#" @click.prevent="selectStatus('In Progress', $event)"
          >In Progress</a
        >
      </li>
      <li>
        <a class="dropdown-item" href="#" @click.prevent="selectStatus('Complete', $event)"
          >Complete</a
        >
      </li>
      <li>
        <a class="dropdown-item" href="#" @click.prevent="selectStatus('Archive', $event)"
          >Archive</a
        >
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isExpanded: false,
      selectedStatus: 'Launch Pad'
    }
  },
  computed: {
    buttonClass() {
      return {
        'btn btn-backlog': this.selectedStatus === 'Backlog',
        'btn btn-launchpad': this.selectedStatus === 'Launch Pad',
        'btn btn-inprogress': this.selectedStatus === 'In Progress',
        'btn btn-complete': this.selectedStatus === 'Complete',
        'btn btn-archive': this.selectedStatus === 'Archive'
      }
    }
  },
  methods: {
    toggleDropdown() {
      this.isExpanded = !this.isExpanded
    },

    selectStatus(status, event) {
      const page = event.target.closest('div').querySelector('button').getAttribute('page')
      console.log(page)
      this.selectedStatus = status
      this.isExpanded = false
    },

    collapseDropdown() {
      console.log('activated')
      this.isExpanded = false
    }
  }

  
}
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
