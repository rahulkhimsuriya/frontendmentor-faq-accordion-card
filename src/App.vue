<template>
  <div id="app">
    <div class="container">
      <div class="card">
        <div class="card__images">
          <img
            src="./assets/images/illustration-box-desktop.svg"
            alt="box"
            class="card__image--box"
          />
          <div class="card__wraper">
            <img
              src="./assets/images/illustration-woman-online-desktop.svg"
              alt="woman-online"
              class="card__image--women"
            />
          </div>
        </div>
        <div class="card__body">
          <h2 class="card__body--header">FAQ</h2>

          <accordion :items="items" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Accordion from './components/Accordion.vue';

export default {
  name: 'App',

  components: {
    Accordion
  },

  data() {
    return {
      items: [
        {
          title: 'How many team members can I invite?',
          body:
            'You can invite up to 2 additional users on the Free plan. There is no limit on team members for the Premium plan.'
        },

        {
          title: 'What is the maximum file upload size?',
          body:
            'No more than 2GB. All files in your account must fit your allotted storage space.'
        },

        {
          title: 'How do I reset my password?',
          body:
            'Click “Forgot password” from the login page or “Change password” from your profile page. A reset link will be emailed to you.'
        },

        {
          title: 'Can I cancel my subscription?',
          body:
            'Yes! Send us a message and we’ll process your request no questions asked.'
        },

        {
          title: 'Do you provide additional support?',
          body:
            'Chat and email support is available 24/7. Phone lines are open during normal business hours.'
        }
      ]
    };
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Kumbh+Sans:wght@400;700&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: 'Kumbh Sans', sans-serif;
  font-size: 12px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  min-height: 100vh;
  background-image: linear-gradient(
    to bottom right,
    hsl(273, 75%, 66%),
    hsl(240, 73%, 65%)
  );
  display: flex;
  align-items: center;
  justify-content: center;
}

.container {
  width: 90%;
  max-width: 1024px;
  margin: 0 auto;
  padding: 0 1rem;
}

.card {
  display: flex;
  align-items: center;
  background-color: #fff;
  border-radius: 1rem;
  position: relative;
  background-image: url('./assets/images/bg-pattern-desktop.svg');
  background-position: -65% 67%;
  background-repeat: no-repeat;
  background-size: 600px, 48px;
}

.card > * {
  flex: 1;
  grid-gap: 1rem;
}

.card__images {
  position: relative;
}

.card__wraper {
  overflow: hidden;
}

.card__image--women {
  max-height: 285px;
  margin-left: -4rem;
}

.card__image--box {
  position: absolute;
  height: 120px;
  left: -14%;
  top: 42%;
}

.card__body {
  padding: 4rem;
}

.card__body--header {
  font-size: 2rem;
  padding-bottom: 2rem;
}
</style>
