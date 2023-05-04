<template>
    <div class="video-background">
    <video autoplay loop muted class="video-background">
      <source src="../video/bg-video.mp4" type="video/mp4">
    </video>
    <div class="gradient-overlay"></div>
    </div>
  </template>

<style scoped>
.video-background {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -1;
}
.gradient-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: radial-gradient(ellipse at top, #1b0b0b9d, transparent), radial-gradient(ellipse at bottom, #141d0da1, transparent);
  z-index: 1;
}
</style>
