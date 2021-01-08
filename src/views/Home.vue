<template>
  <div class="home">
    <!-- Game page -->
    <div ref="gameBoard"></div>
  </div>
</template>

<script>
// @ is an alias to /src

import * as THREE from "three";

export default {
  name: "Home",
  data() {
    return {
      // game state
    };
  },
  methods: {
    // functions that run on every re-render
    renderGame() {
      const scene = new THREE.Scene();
      const camera = new THREE.PerspectiveCamera(
        75,
        window.innerWidth / window.innerHeight,
        0.1,
        1000
      );

      const renderer = new THREE.WebGLRenderer();
      renderer.setSize(window.innerWidth, window.innerHeight);
      const testEl = this.$refs.gameBoard;
      testEl.appendChild(renderer.domElement)
      

      const geometry = new THREE.BoxGeometry();
      const material = new THREE.MeshBasicMaterial({ color: 0x00ff00 });
      const cube = new THREE.Mesh(geometry, material);
      scene.add(cube);

      camera.position.z = 5;

      const animate = function() {
        requestAnimationFrame(animate);

        cube.rotation.x += 0.01;
        cube.rotation.y += 0.01;

        renderer.render(scene, camera);
      };

      animate();
    }
  },
  computed: {
    // functions that run only when state change is is detected. (data changes)
  },
  watch: {
    // functons that run only under specified conditions (side effects)
  },
  components: {},
  mounted() {
    this.renderGame();
  }
};
</script>
