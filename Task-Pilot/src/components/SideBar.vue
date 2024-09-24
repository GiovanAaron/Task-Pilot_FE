<!-- image = "src/assets/profile_pic.webp" -->
<style>
  .side-bar_elements {
    display: flex;
    flex-direction: column;
    gap: 1.4rem;
    margin-top: 2rem;
  }
</style>



<template>
  <div
    class="container position-fixed left-0"
    style="background-color: #7e7a89; color: white; max-width: 14rem; height: 100vh"
  >
    <h3 style="padding-top: 1rem;">Task Pilot</h3>
    <div style="margin-top: 2rem">
      <img
        src="../assets/profile_pic.webp"
        alt="Description of the image"
        style="width: 50%; height: 50%; object-fit: contain; border: 2px solid white"
      />
    </div>
    <div class="side-bar_elements ">
      <h4><a href="">Notifications</a></h4>
      <h4><a href="">Today</a></h4>
      <h4><a href="">Kanban</a></h4>
      <h4><a href="">Calendar View</a></h4>
      <h4><a href="">Overview</a></h4>
    </div>

    <div class="side-bar_elements" 
    style="height: 50vh; padding-bottom: 7rem;
    justify-content: flex-end; " >
      <h4><a href="">My Profile</a></h4>
      <h4><a href="">Settings</a></h4>
      
    </div>
  </div>
</template>
