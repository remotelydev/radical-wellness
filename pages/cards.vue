<template>
  <main class="min-h-screen flex flex-column justify-center items-center p-4">
    <h1>
      {{ currentQuestion ? currentQuestion : 'Draw a question' }}
    </h1>
    <button
      class="fixed bottom-0 m-2 px-4 py-2 bg-red-500 text-white rounded"
      @click="getRandomQuestion"
    >
      Draw
    </button>
  </main>
</template>

<script>
export default {
  data() {
    return {
      currentQuestion: undefined,
      deck: [
        `What is something that people don't know about you?`,
        'Describe the lowest point in your life, in detail.',
        `Describe a situation in which you treated someone mean, who didn't deserve it. What happened?`,
        'What do you most regret in your life?',
        'Describe the highest point in your life, in detail.',
        'When was the last time you told someone a lie, and got away with it.',
        'When you are in pain, how do you usually react?',
        'Describe the last time you were kind to a stranger.',
        'Describe one habit you would like to get rid of.',
        'What is the most important choice you have made in your life?',
        'Who are the three people who have influenced who you are today the most?',
        'Describe your first big love.',
        'How would you want to be described at your funeral?',
        'If you could change anything about the way you were raised, what would it be?',
        'If you died tonight, what would you most regret not having told someone?',
        'Describe your parents’ values. How do they influence you today?',
        'Take four minutes and tell us your life story in as much detail as possible.',
        'If you could travel back in time and visit your younger self, what advice would you give yourself?',
        'What is your happiest memory?',
        'Who is the one person whose death would most affect you? Why?',
        'Who do you think is the one person that would be most affected by your death?',
        'Do you believe in life after death, and why?',
        'For what in your life do you feel most grateful?',
        'What does forgiveness mean to you?',
        'What accomplishment in your life are you most proud of?',
        'How do you like to receive love? And to give love?',
        'What does inner freedom mean to you?',
        'Where do you feel safest and why?',
        'If you were to be remembered forever, what would you want to be remembered for?',
        'If you had enough money to not have to work, how would you spend your days?',
        'What did you dream of becoming when you were young?',
        'If you could choose to have one superpower, what would it be?',
        'Describe where you want to be five years from now.',
        `Is there something that you’ve dreamt of doing for a long time? What's stopping you?`,
        'Describe the one habit you would most like to develop.',
        'Describe your ideal date, in detail.',
        'If you could make one rule that everyone in the world had to follow, what would it be and why?',
        'Who would be your favourite dinner guests?',
        'When was the last time you cried in front of someone?',
        'What is the most child-like thing you still do?',
        'On a scale from 1 to 10, how would you rate your current stress-level, and why?',
        'Describe a situation in which you felt from the start it was going to fail, but you still pursued it. What happened?',
        'When in your life did you experience heartbreak?',
        'When was the last time you feared for your life?',
        'What is the most romantic thing you have ever done for someone?',
        'If you could forgive yourself or someone else for one thing, what would it be?',
        'In what ways are you most like one or both of your parents?',
        'Describe your most recent romantic encounter in detail.',
        'Who would be your favourite dinner guests?',
        'Tell someone what you like about them.',
        'If you were stuck on a deserted island and could bring three food items, what would they be?',
        'Name three things you seem to have in common with the person next to you.',
        'When was the last time you sang to yourself? To someone?',
        'What is the best compliment you have ever received?',
        'What would be the soundtrack of your life?',
        'My favourite sound or smell is…',
        'What would be the title of your autobiography?',
        'I get mad when…'
      ]
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
