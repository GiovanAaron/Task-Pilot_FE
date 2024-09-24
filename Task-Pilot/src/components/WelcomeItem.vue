<template>
  <div class="d-flex align-items-start my-4 position-relative">
    <i class="d-flex justify-content-center align-items-center bg-light border border-secondary rounded-circle" style="width: 50px; height: 50px;">
      <slot name="icon"></slot>
    </i>
    <div class="flex-grow-1 ms-3">
      <h3 class="h5 fw-medium mb-2 text-primary">
        <slot name="heading"></slot>
      </h3>
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
@media (min-width: 1024px) {
  .position-relative::before, .position-relative::after {
    content: ' ';
    position: absolute;
    border-left: 1px solid var(--bs-secondary-border-color); /* Adjust for Bootstrap variable */
    left: 0;
  }

  .position-relative::before {
    bottom: calc(50% + 25px);
    height: calc(50% - 25px);
  }

  .position-relative::after {
    top: calc(50% + 25px);
    height: calc(50% - 25px);
  }

  .position-relative:first-of-type::before {
    display: none;
  }

  .position-relative:last-of-type::after {
    display: none;
  }
}
</style>
