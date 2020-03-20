<template>
  <main>
    <h1>
      {{ currentQuestion ? currentQuestion : 'Draw a question' }}
    </h1>
    <button @click="getRandomQuestion">Shuffle</button>
  </main>
</template>

<script>
export default {
  data() {
    return {
      currentQuestion: undefined,
      deck: ['To be or not to be?', 'What is love?', 'Does this work?']
    }
  },
  methods: {
    getRandomQuestion() {
      const randomIndex = Math.floor(Math.random() * this.deck.length)
      this.currentQuestion = this.deck[randomIndex]
      this.deck.splice(randomIndex, 1)
    }
  }
}
</script>
