<template>
  <div class="wrapper">
    <section class="section hero">
      <the-header></the-header>
      <main class="maincontent">
        <div class="directors">
          <ul class="people__list people__list2">
            <the-people
                :regactive="firstManagers"
                :isCardOpen="false"
            >
            </the-people>
          </ul>
        </div>
        <div class="container">
          <the-map
          :regs="steps"
          @currentReg="setActive"
          @click="currentStep"
          :class="currentStep ? 'grey' : '' "
          ></the-map>
        </div>
      </main>
    </section>
    <section class="section people" v-if="activeIndex != 0">
      <div class="container">
        <div class="people__list--card">
          <ul class="people__list people__list3">
            <the-people
                :regactive="currentManagers"
                :isCardOpen="true"
            >
            </the-people>
          </ul>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader";
import TheMap from "./components/TheMap";
import ThePeople from "./components/ThePeople";

export default {
  components: {
    TheHeader, TheMap, ThePeople
  },
  data() {
    return {
      activeIndex: 0, // то, что позволяет определить текущий активный шаг
      activeText: '',
      steps: [],
    }
  },
  created() {
    const data = require('./data/regions.json')
    this.steps = data

    this.addImagePath(this.firstManagers)
    // console.log(this.addImagePath(this.firstManagers))
  },
  updated() {
    this.addImagePath(this.currentManagers)
    console.log()
  },
  methods: {
    setActive(idx) {
      this.activeIndex = idx
    },
    addImagePath(people) {
      if(people) {
        return people.map(el => {
          let avatar = require(`./img/${el.avatar}`);
          el.avatar = avatar;
          console.log(el)
          return el
        })
      }
    },
  },
  computed: {
    currentStep() {
      console.log(this.activeIndex)
      return this.steps[this.activeIndex]
    },
    firstManagers() {
      return this.steps[0].managers
    },
    currentManagers() {
      if(!this.steps[this.activeIndex]) {
        console.log('tut', this.steps[this.activeIndex])
      } else {
        return this.steps[this.activeIndex].managers
      }
    }
  }
}
</script>

<style scoped>

.people {
  background: #DCDCDC;
}

.people__list3 {
  margin-top: 100px;
}


</style>
