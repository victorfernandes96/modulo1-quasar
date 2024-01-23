<template>
  <q-page class="container flex flex-center justify-around">
    <q-img
      src="https://play-lh.googleusercontent.com/q2RJGwjMz5VUFHhwhyYFs2toYEzX9t6JVn-94Hi7hXxN6Hw3RQgfmbzVtHA9ww-oZb0r"
      spinner-color="white"
      style="height: auto; max-width: 230px"
    />

    <h4 class="title q-ma-sm text-center">{{ phrases[index] }}</h4>

    <q-btn
      @click="randonPosition"
      class="button"
      rounded
      label="Gerar Frases"
    />
  </q-page>
</template>

<script>
export default {
  name: "PhraseOfDay",
  data() {
    return {
      phrases: [
        "Se você aprendeu a ter medo, então poderá aprender a ter coragem.",
        "A timidez faz com que um homem negue ao mundo a sua existência.",
        "A dor faz parte, o sofrimento é uma opção e o sucesso a consequência.",
        "O pior não, é aquele que você dá a si mesmo",
        "Os diamantes são valiosos não por serem brilhantes, mas por serem raros",
      ],

      index: 0,
    };
  },

  methods: {
    randonPosition() {
      let index = parseInt(Math.random() * 5 + 0);
      console.log(index);
      this.index = index;
    },
  },

  beforeMount() {
    this.randonPosition();
  },
};
</script>

<style lang="stylus" scoped>
.container {
   background-color: #f95179;
  }

  .title {
    color: #fff
  };

  .button{

    color: #fff;
    height: 60px;
    background-color: #262525;
  }
</style>
