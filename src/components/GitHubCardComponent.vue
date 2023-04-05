<template>
  <a href="https://github.com/">
    <div class="card">
      <img src="@/assets/github.svg" alt="">
      <p>{{ username }}</p>
    </div>
  </a>
</template>

<script>
import gsap from 'gsap';

export default {
  name: 'GitHubCardComponent',
  props: {
    username: {
      type: String,
      required: true,
    },
  },
  mounted() {
    const card = this.$el;
    card.href += this.username;
    card.target = '_blank';
    gsap.set('.card', { x: -window.innerWidth, opacity: 0 });
    window.addEventListener('keypress', (e) => {
      if (e.key === 'g') {
        gsap.to('.card', {
          x: 0,
          opacity: 1,
          duration: 2,
          ease: 'bounce.out',
          stagger: {
            amount: 0.5,
            from: 'end',
          },
        });
      }
    });
  },
};
</script>

<style scoped lang="scss">
a{
  text-decoration: none;
}
.card{
  padding: 0 15px;
  width: fit-content;
  box-sizing: border-box;
  background-color: black;
  border-radius: 20px;
  display: flex;
  align-items: center;
  gap: 15px;
  img{
    filter: invert(1);
  }
  p{
    color: white;
    font-weight: bold;
  }
}
</style>
