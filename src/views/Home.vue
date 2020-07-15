<template>
  <div class="home">
    <v-row class="introduction mb-8">
      <v-flex md4 sm5 xs12>
        <v-card color="#121212" dark>
          <div class="d-flex flex-no-wrap">
            <v-avatar
              class="ma-3 elevation-4 rounded-4"
              size="100"
              tile
            >
              <v-img src="@/assets/myself.jpg"></v-img>
            </v-avatar>
            <div>
              <v-card-title>李怡情</v-card-title>
              <v-card-subtitle class="pa-0 pl-4">全端工程師</v-card-subtitle>
              <span class="address"><v-icon>mdi-map-marker</v-icon>台灣・高雄</span>
            </div>
          </div>
        </v-card>
      </v-flex>
      <v-flex class="content" md8 sm7 xs12>
        目前在公司擔任全端工程師
      </v-flex>
    </v-row>

    <h4 class="mb-4">技能</h4>
    <v-row class="skills mb-8">
      <div class="skill" v-for="skill in skills">
        <div>
          <v-img :src="skill.image"></v-img>
        </div>
        <span>{{skill.title}}</span>
      </div>
    </v-row>

    <h4 class="mb-4">經歷</h4>
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
              <div class="skills mb-2">
                <div v-for="(skill) in year.skills" >
                  <v-img :src="skill.image"></v-img>
                </div>
              </div>
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
        skills: [{
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
        company: '百星科技'
      },
      {
        color: 'green',
        year: '2012 - 2016',
        skills: [{
          title: 'CSS',
          image: require('@/assets/skills/css.png')
        }, {
          title: 'HTML',
          image: require('@/assets/skills/html.png')
        }],
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
  .v-image {
    border-radius: 4px!important;
    box-shadow: 0 3px 5px -1px rgba(0,0,0,.2),0 5px 8px 0 rgba(0,0,0,.14),0 1px 14px 0 rgba(0,0,0,.12)!important;
  }
  .content {
    display: flex;
    align-items: center;
    color: rgba(255, 255, 255, 0.7);
    font-size: 14px;
  }
}
.skills {
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
}
.experience {
  .skills {
    display: inline-flex;
    background: #adadad;
    height: 40px;
    padding: 4px;
    border-radius: 4px;
    align-items: center;
    > div {
      margin: 0 4px;
      height: 30px;
      width: 30px;
    }
  }
}

</style>
