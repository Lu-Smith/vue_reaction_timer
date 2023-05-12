<template>
    <p class="footer-note">
    This project was coded by
    <a href="https://www.lunasmithart.com/" target="_blank" class="cool-link"
      >Luna Smith</a
    >
    and is open-source on
    <a
      href="https://github.com/Lu-Smith/vue_reaction_timer"
      target="_blank"
      class="cool-link"
      >GitHub</a
    >.
  </p>
</template>

<style>
.footer-note {
  position: fixed;
  bottom: 0;
  width: 100vw;
  padding: 20px 0;
  font-weight: 500;
  background-color: rgb(52, 15, 58);
  color: #f1f5f3;
}

.cool-link {
  position: relative;
  text-decoration: none;
  color: #fcd6d6;
  transition: all 0.3s ease;
  letter-spacing: 1px;
}

.cool-link:before {
  content: "";
  position: absolute;
  width: 100%;
  height: 3px;
  bottom: -5px;
  left: 0;
  background-color: #f87e0d;
  visibility: hidden;
  transform: scaleX(0);
  transition: all 0.3s ease-in-out 0s;
}

.cool-link:hover:before {
  visibility: visible;
  transform: scaleX(1);
}

.cool-link:hover {
  color: #f87e0d;
}
</style>