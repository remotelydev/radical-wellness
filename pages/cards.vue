<template>
  <main
    :class="inverted ? `bg-${categoryColor} text-white` : ''"
    class="min-h-screen flex flex-col justify-between items-center p-4"
  >
    <Logo
      :class="inverted ? 'text-white' : `text-${categoryColor}`"
      class="h-24"
    />
    <div class="card flex flex-col max-w-md">
      <h1>
        {{ card ? card.question : 'Draw a question' }}
      </h1>
      <span class="self-end flex items-center"
        ><span
          v-if="card"
          :class="inverted ? '' : `text-${categoryColor}`"
          class="text-4xl"
          >&bull;</span
        >{{ card && card.category }}
      </span>
    </div>
    <button
      :class="
        inverted
          ? `bg-white text-${categoryColor}`
          : `bg-${categoryColor} text-white`
      "
      class="px-4 py-2 rounded"
      @click="getRandomQuestion"
    >
      Draw
    </button>
  </main>
</template>

<script>
import Logo from '~/components/Logo'

export default {
  components: {
    Logo
  },
  data() {
    return {
      card: undefined,
      deck: [
        {
          question:
            "What is one thing that you truly value about your life that you didn't realize before the quarantine?",
          category: 'Light & Shadow',
          level: 1
        },
        {
          question:
            'What is one lesson that humanity can learn from this time of quarantine?',
          category: 'Light & Shadow',
          level: 2
        },
        {
          question:
            "Imagine you'd have to spend a year in quarantine.... How would you design your daily life?",
          category: 'Light & Shadow',
          level: 2
        },
        {
          question:
            'Who are three people with whom you would most like to be quarantined?',
          category: 'Light & Shadow',
          level: 2
        },
        {
          question:
            'What would be your ideal location to spend in quarantine? Why?',
          category: 'Light & Shadow',
          level: 1
        },
        {
          question:
            'How important is it to you to feel part of a community right now? Why?',
          category: 'Light & Shadow',
          level: 2
        },
        {
          question:
            'What has the current lockdown taught you about yourself? What changes do you plan to make, if any?',
          category: 'Light & Shadow',
          level: 1
        },
        {
          question:
            'What has the current lockdown taught you about your current profession? What chainges do you plan to make, if any?',
          category: 'Light & Shadow',
          level: 1
        },
        {
          question:
            'Would you sacrifice your life if it meant protecting all people on this planet from the virus?',
          category: 'Light & Shadow',
          level: 2
        },
        {
          question:
            'What is the most important choice you have made in your life?',
          category: 'Past & Future',
          level: 2
        },
        {
          question:
            'Who are the three people who have influenced who you are today the most?',
          category: 'Past & Future',
          level: 1
        },
        {
          question: 'Describe your first big love.',
          category: 'Past & Future',
          level: 1
        },
        {
          question: 'How would you want to be described at your funeral?',
          category: 'Past & Future',
          level: 2
        },
        {
          question:
            'If you could change anything about the way you were raised, what would it be?',
          category: 'Past & Future',
          level: 2
        },
        {
          question:
            'If you died tonight, what would you most regret not having told someone?',
          category: 'Past & Future',
          level: 2
        },
        {
          question:
            'Take four minutes and tell us your life story in as much detail as possible.',
          category: 'Past & Future',
          level: 1
        },
        {
          question:
            'If you could travel back in time and visit your younger self, what advice would you give yourself?',
          category: 'Past & Future',
          level: 1
        },
        {
          question: 'What is your happiest memory?',
          category: 'Past & Future',
          level: 1
        },
        {
          question:
            'Who is the one person whose death would most affect you? Why?',
          category: 'Reflect & Share',
          level: 2
        },
        {
          question:
            'Who do you think is the one person that would be most affected by your death?',
          category: 'Reflect & Share',
          level: 2
        },
        {
          question: 'Do you believe in life after death, and why?',
          category: 'Reflect & Share',
          level: 2
        },
        {
          question: 'For what in your life do you feel most grateful?',
          category: 'Reflect & Share',
          level: 1
        },
        {
          question: 'What does forgiveness mean to you?',
          category: 'Reflect & Share',
          level: 2
        },
        {
          question: 'What accomplishment in your life are you most proud of?',
          category: 'Reflect & Share',
          level: 1
        },
        {
          question: 'How do you like to receive love? And to give love?',
          category: 'Reflect & Share',
          level: 2
        },
        {
          question: 'What does inner freedom mean to you?',
          category: 'Reflect & Share',
          level: 2
        },
        {
          question: 'Where do you feel safest and why?',
          category: 'Reflect & Share',
          level: 2
        },
        {
          question:
            'If you were to be remembered forever, what would you want to be remembered for?',
          category: 'Dream & Desire',
          level: 2
        },
        {
          question:
            'If you had enough money to not have to work, how would you spend your days?',
          category: 'Dream & Desire',
          level: 1
        },
        {
          question: 'What did you dream of becoming when you were young?',
          category: 'Dream & Desire',
          level: 1
        },
        {
          question:
            'If you could choose to have one superpower, what would it be?',
          category: 'Dream & Desire',
          level: 1
        },
        {
          question: 'Describe where you want to be five years from now.',
          category: 'Dream & Desire',
          level: 1
        },
        {
          question:
            "Is there something that you’ve dreamt of doing for a long time? What's stopping you?",
          category: 'Dream & Desire',
          level: 2
        },
        {
          question: 'Describe the one habit you would most like to develop.',
          category: 'Dream & Desire',
          level: 1
        },
        {
          question: 'Describe your ideal date, in detail.',
          category: 'Dream & Desire',
          level: 1
        },
        {
          question:
            'If you could make one rule that everyone in the world had to follow, what would it be and why?',
          category: 'Dream & Desire',
          level: 1
        },
        {
          question: 'When was the last time you cried in front of someone?',
          category: 'Open & Tell',
          level: 2
        },
        {
          question: 'What is the most child-like thing you still do?',
          category: 'Open & Tell',
          level: 1
        },
        {
          question:
            'Describe a situation in which you felt from the start it was going to fail, but you still pursued it. What happened?',
          category: 'Open & Tell',
          level: 2
        },
        {
          question: 'When in your life did you experience heartbreak?',
          category: 'Open & Tell',
          level: 2
        },
        {
          question: 'When was the last time you feared for your life?',
          category: 'Open & Tell',
          level: 2
        },
        {
          question:
            'What is the most romantic thing you have ever done for someone?',
          category: 'Open & Tell',
          level: 1
        },
        {
          question:
            'If you could forgive yourself or someone else for one thing, what would it be?',
          category: 'Open & Tell',
          level: 2
        },
        {
          question:
            'In what ways are you most like one or both of your parents?',
          category: 'Open & Tell',
          level: 2
        },
        {
          question: 'Describe your most recent romantic encounter in detail.',
          category: 'Open & Tell',
          level: 1
        },
        {
          question:
            'What are the three things that can make your quarantine easier? What three things can even make it fun?',
          category: 'Re-think & Re-frame',
          level: 1
        },
        {
          question:
            'What positive societal changes do you expect the current crisis to bring?',
          category: 'Re-think & Re-frame',
          level: 2
        },
        {
          question:
            'What is the first thing you will do once you get out of quarantine?',
          category: 'Re-think & Re-frame',
          level: 1
        },
        {
          question:
            'Name three ways to keep physically fit during quarantine, and three ways to keep mentally fit.',
          category: 'Re-think & Re-frame',
          level: 1
        },
        {
          question:
            'If you had to live on only a few food items for the next few months, what would they be?',
          category: 'Re-think & Re-frame',
          level: 1
        },
        {
          question:
            'When I wake up or go to bed, in order to release worries and tension, I...',
          category: 'Re-think & Re-frame',
          level: 2
        },
        {
          question:
            'What altered behaviour do you see around you that makes you laugh?',
          category: 'Re-think & Re-frame',
          level: 1
        },
        {
          question: 'How are you showing your loved ones that you love them?',
          category: 'Re-think & Re-frame',
          level: 2
        },
        {
          question:
            'How do you manage to keep your heart open and free from fear?',
          category: 'Re-think & Re-frame',
          level: 2
        },
        {
          question:
            'How do you cope with the overflow of news and information during the quarantine?',
          category: 'Re-think & Re-frame',
          level: 1
        },
        {
          question: 'What would be your soundtrack for the current lockdown?',
          category: 'Re-think & Re-frame',
          level: 1
        },
        {
          question:
            "What is one thing that you truly value about your life that you didn't realize before the quarantine?",
          category: 'Re-think & Re-frame',
          level: 2
        },
        {
          question:
            'What is one lesson that humanity can learn from this time of quarantine?',
          category: 'Re-think & Re-frame',
          level: 2
        },
        {
          question:
            "Imagine you'd have to spend a year in quarantine.... How would you design your daily life?",
          category: 'Re-think & Re-frame',
          level: 2
        },
        {
          question:
            'Who are three people with whom you would most like to be quarantined?',
          category: 'Re-think & Re-frame',
          level: 1
        },
        {
          question:
            'What would be your ideal location to spend in quarantine? Why?',
          category: 'Re-think & Re-frame',
          level: 1
        },
        {
          question:
            'How important is it to you to feel part of a community right now? Why?',
          category: 'Re-think & Re-frame',
          level: 1
        },
        {
          question:
            'What has the current lockdown taught you about yourself? What changes do you plan to make, if any?',
          category: 'Re-think & Re-frame',
          level: 2
        },
        {
          question:
            'What has the current lockdown taught you about your current profession? What changes do you plan to make, if any?',
          category: 'Re-think & Re-frame',
          level: 2
        },
        {
          question:
            'Would you sacrifice your life if it meant protecting all people on this planet from the virus?',
          category: 'Re-think & Re-frame',
          level: 2
        }
      ]
    }
  },
  computed: {
    categoryColor() {
      let color = 'black'
      if (!this.card) return color
      switch (this.card.category) {
        case 'Light & Shadow':
          color = 'black'
          break
        case 'Past & Future':
          color = 'rad-red'
          break
        case 'Reflect & Share':
          color = 'rad-pink'
          break
        case 'Dream & Desire':
          color = 'rad-beige'
          break
        case 'Open & Tell':
          color = 'rad-green'
          break
        case 'Re-think & Re-frame':
          color = 'rad-yellow'
          break
      }
      return color
    },
    inverted() {
      return this.card?.level === 2
    }
  },
  methods: {
    getRandomQuestion() {
      const randomIndex = Math.floor(Math.random() * this.deck.length)
      this.card = this.deck[randomIndex]
      this.deck.splice(randomIndex, 1)
    }
  }
}
</script>
