<template>
  <div class="home">
    <v-row class="introduction">
      <v-col xs-12>
        <v-card color="#121212" dark>
          <div class="d-flex flex-no-wrap">
            <v-avatar
              class="ma-3"
              size="125"
              tile
            >
              <v-img src="@/assets/skills/css.png"></v-img>
            </v-avatar>
            <div>
              <v-card-title>李怡情</v-card-title>
              <v-card-subtitle class="pa-0 pl-4">全端工程師</v-card-subtitle>
              <span class="address"><v-icon>mdi-map-marker</v-icon>台灣・高雄</span>
            </div>
          </div>
        </v-card>
      </v-col>
      <v-col></v-col>
    </v-row>

    <h4 class="mb-1">技能</h4>
    <v-row class="skills mb-4">
      <div class="skill" v-for="skill in skills">
        <div>
          <v-img :src="skill.image"></v-img>
        </div>
        <span>{{skill.title}}</span>
      </div>
    </v-row>

    <h4 class="mb-1">經歷</h4>
    <v-row class="experience">
      <v-timeline dense>
        <v-slide-x-reverse-transition
          group
          hide-on-leave
        >
          <v-timeline-item
            v-for="(year, i) in years"
            :key="i"
            :color="year.color"
            small
          >
            <div class="py-4">
              <div
                :class="`font-weight-bold ${year.color}--text`"
                v-text="year.year"
              ></div>
              <div :class="` mb-4 ${year.color}--text`">{{year.company}}</div>
              <div>
                Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.
              </div>
            </div>
          </v-timeline-item>
        </v-slide-x-reverse-transition>
      </v-timeline>
    </v-row>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  data: () => ({
    skills: [{
      title: 'CSS',
      image: require('@/assets/skills/css.png')
    }, {
      title: 'HTML',
      image: require('@/assets/skills/html.png')
    }, {
      title: 'javascript',
      image: require('@/assets/skills/javascript.png')
    }, {
      title: 'node.js',
      image: require('@/assets/skills/node.png')
    }, {
      title: 'vue.js',
      image: require('@/assets/skills/vue.png')
    }, {
      title: 'git',
      image: require('@/assets/skills/git.png')
    }, {
      title: 'Bootstrap',
      image: require('@/assets/skills/bootstrap.png')
    }],
    years: [
      {
        color: 'cyan',
        year: '2017 - 現在',
        company: '百星科技'
      },
      {
        color: 'green',
        year: '2012 - 2016',
        company: '國立台東大學 - 資訊工程學系'
      }
    ]
  }),
}
</script>
<style lang="scss">
.introduction {
  .address {
    font-size: 10px;
    padding-left: 16px;
    color: rgba(255, 255, 255, 0.7);

    .v-icon {
      font-size: 20px;
      color: rgba(255, 255, 255, 0.7);
    }
  }
}
.skill{

  > div {
    height: 60px;
    width: 60px;
    background: #ffffff;
    border-radius: 8px;
    padding: 4px;
    margin: 0 10px;
    display: flex;
    margin-bottom: 2px;
  }

 > span {
    font-size: 12px;
    display: flex;
    justify-content: center;
  }
}

</style>
