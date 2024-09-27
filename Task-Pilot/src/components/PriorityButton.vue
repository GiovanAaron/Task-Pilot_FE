<template>
    <div class="dropdown">
      <button
        page="2334"
        id="dropdownMenuButton"
        type="button"
        :class="['dropdown-toggle',buttonClass ]"
        @click="toggleDropdown"
        :aria-expanded="isExpanded.toString()"
      >
        {{ selectedStatus }}
      </button>
      <ul v-if="isExpanded" class="dropdown-menu show">
        <li><a class="dropdown-item" href="#" @click.prevent="selectStatus('Optional', $event)">Optional</a></li>
        <li><a class="dropdown-item" href="#" @click.prevent="selectStatus('Low', $event)">Low</a></li>
        <li><a class="dropdown-item" href="#" @click.prevent="selectStatus('Medium', $event)">Medium</a></li>
        <li><a class="dropdown-item" href="#" @click.prevent="selectStatus('High', $event)">High</a></li>
        <li><a class="dropdown-item" href="#" @click.prevent="selectStatus('Critical', $event)">Critical</a></li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isExpanded: false,
        selectedStatus: 'Low'
      };
    },
    computed: {
      buttonClass() {
        return {
          'btn btn-optional': this.selectedStatus === 'Optional',
          'btn btn-low': this.selectedStatus === 'Low',
          'btn btn-medium': this.selectedStatus === 'Medium',
          'btn btn-high': this.selectedStatus === 'High',
          'btn btn-critical': this.selectedStatus === 'Critical'
        };
      }
    },
    methods: {
      toggleDropdown() {
        this.isExpanded = !this.isExpanded;
      },

      selectStatus(status, event) {
        const page = event.target.closest('div').querySelector('button').getAttribute('page')
        console.log(page)
        this.selectedStatus = status;
        this.isExpanded = false;
      }
    }
  };
  </script>
  
  <style>
 .btn-optional {
  background-color: #e0e0e0; /* Backlog background color */
  border-color: #bdbdbd; /* Darker border color */
}

.btn-optional:hover {
  background-color: #bdbdbd; /* Darker hover background color */
  border-color: #9e9e9e; /* Even darker border color on hover */
}

/* low Button */
.btn-low {
  background-color: #d5b383; /* low background color */
  border-color: #c39a5b; /* Darker border color */
}

.btn-low:hover {
  background-color: #c39a5b; /* Darker hover background color */
  border-color: #a6784a; /* Even darker border color on hover */
}

/* medium Button */
.btn-medium {
  background-color: #b0c4cb; /* medium background color */
  border-color: #97a8af; /* Darker border color */
  color:white
}

.btn-medium:hover {
  background-color: #97a8af; /* Darker hover background color */
  border-color: #7f8f96; /* Even darker border color on hover */
}

/* high Button */
.btn-high {
  background-color: #FDD150; /* high background color */
  border-color: #f1c84e; /* Darker border color */
}

.btn-high:hover {
  background-color: #ebc44f; /* Darker hover background color */
  border-color: #ad8f34; /* Even darker border color on hover */
}

/* critical Button */
.btn-critical {
  background-color: #FA474A; /* critical background color */
  border-color: #e43d3f; /* Darker border color */
  color:#FFFFFF
}

.btn-critical:hover {
  background-color: #e93e41; /* Darker hover background color */
  border-color: #e13a3d; /* Even darker border color on hover */
  
}
  </style>
  