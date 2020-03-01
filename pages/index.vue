<template>
  <ul class="condiments-list">
    <li
      v-for="(condiment, index) in condiments"
      :key="index"
      class="condiments-list__item"
    >
      <h4 class="condiments-list__title">
        {{ condiment.title }}
      </h4>
      <div class="condiments-list__content">
        <condiment-checkbox
          v-for="(values, i) in condiment.items"
          :key="values.id + i"
          :condiment="values"
        />
      </div>
    </li>
  </ul>
</template>
<script lang="ts">
import Vue from 'vue'
import CondimentCheckbox from '~/components/CondimentCheckbox.vue'

export default Vue.extend({
  name: 'CondimentsList',
  components: {
    CondimentCheckbox
  },
  data() {
    return {
      condiments: [
        {
          title: 'あ行',
          items: [
            {
              id: 'oil',
              name: '油',
              styles: {
                '--background-image': require('~/assets/images/oil.png'),
                '--background-size': '25%',
                '--border-color--hover': 'rgba(243, 241, 214, 0.1)',
                '--background-color--hover': 'rgba(243, 241, 214, 0.25)',
                '--background-color--checked': 'rgba(243, 241, 214, 0.2)'
              }
            },
            {
              id: 'olive-oil',
              name: 'オリーブオイル',
              styles: {
                '--background-image': require('~/assets/images/olive-oil.png'),
                '--background-size': '20%',
                '--border-color--hover': 'rgba(214, 178, 0, 0.1)',
                '--background-color--hover': 'rgba(214, 178, 0, 0.25)',
                '--background-color--checked': 'rgba(214, 178, 0, 0.2)'
              }
            }
          ]
        },
        {
          title: 'か行',
          items: [
            {
              id: 'milk',
              name: '牛乳',
              styles: {
                '--background-image': require('~/assets/images/milk.png'),
                '--background-size': '40%',
                '--border-color--hover': 'rgba(0, 144, 214, 0.1)',
                '--background-color--hover': 'rgba(0, 144, 214, 0.25)',
                '--background-color--checked': 'rgba(0, 144, 214, 0.2)'
              }
            },
            {
              id: 'ketchup',
              name: 'ケチャップ',
              styles: {
                '--background-image': require('~/assets/images/ketchup.png'),
                '--border-color--hover': 'rgba(230, 49, 46, 0.1)',
                '--background-color--hover': 'rgba(230, 49, 46, 0.25)',
                '--background-color--checked': 'rgba(230, 49, 46, 0.2)'
              }
            },
            {
              id: 'pepper',
              name: 'こしょう',
              styles: {
                '--background-image': require('~/assets/images/pepper.png'),
                '--border-color--hover': 'rgba(198, 186, 167, 0.1)',
                '--background-color--hover': 'rgba(198, 186, 167, 0.25)',
                '--background-color--checked': 'rgba(198, 186, 167, 0.2)'
              }
            }
          ]
        },
        {
          title: 'さ行',
          items: [
            {
              id: 'sugar',
              name: '砂糖',
              styles: {
                '--background-image': require('~/assets/images/sugar.png'),
                '--border-color--hover': 'rgba(211, 220, 235, 0.1)',
                '--background-color--hover': 'rgba(211, 220, 235, 0.25)',
                '--background-color--checked': 'rgba(211, 220, 235, 0.2)'
              }
            },
            {
              id: 'salt',
              name: '塩',
              styles: {
                '--background-image': require('~/assets/images/salt.png'),
                '--border-color--hover': 'rgba(211, 220, 235, 0.1)',
                '--background-color--hover': 'rgba(211, 220, 235, 0.25)',
                '--background-color--checked': 'rgba(211, 220, 235, 0.2)'
              }
            },
            {
              id: 'soy-source',
              name: 'しょうゆ',
              styles: {
                '--background-image': require('~/assets/images/soy-source.png'),
                '--background-size': '20%',
                '--border-color--hover': 'rgba(83, 12, 9, 0.1)',
                '--background-color--hover': 'rgba(83, 12, 9, 0.25)',
                '--background-color--checked': 'rgba(83, 12, 9, 0.2)'
              }
            },
            {
              id: 'su',
              name: '酢',
              styles: {
                '--background-image': require('~/assets/images/su.png'),
                '--background-size': '20%',
                '--border-color--hover': 'rgba(253, 244, 214, 0.1)',
                '--background-color--hover': 'rgba(253, 244, 214, 0.25)',
                '--background-color--checked': 'rgba(253, 244, 214, 0.2)'
              }
            },
            {
              id: 'source',
              name: 'ソース',
              styles: {
                '--background-image': require('~/assets/images/source.png'),
                '--border-color--hover': 'rgba(108, 38, 15, 0.1)',
                '--background-color--hover': 'rgba(108, 38, 15, 0.25)',
                '--background-color--checked': 'rgba(108, 38, 15, 0.2)'
              }
            }
          ]
        },
        {
          title: 'な行',
          items: [
            {
              id: 'fresh-cream',
              name: '生クリーム',
              styles: {
                '--background-image': require('~/assets/images/fresh-cream.png'),
                '--background-size': '40%',
                '--border-color--hover': 'rgba(248, 193, 78, 0.1)',
                '--background-color--hover': 'rgba(248, 193, 78, 0.25)',
                '--background-color--checked': 'rgba(248, 193, 78, 0.2)'
              }
            }
          ]
        },
        {
          title: 'は行',
          items: [
            {
              id: 'butter',
              name: 'バター',
              styles: {
                '--background-image': require('~/assets/images/butter.png'),
                '--background-size': '40%',
                '--border-color--hover': 'rgba(254, 229, 93, 0.1)',
                '--background-color--hover': 'rgba(254, 229, 93, 0.25)',
                '--background-color--checked': 'rgba(254, 229, 93, 0.2)'
              }
            }
          ]
        },
        {
          title: 'ま行',
          items: [
            {
              id: 'mayo',
              name: 'マヨネーズ',
              styles: {
                '--background-image': require('~/assets/images/mayo.png'),
                '--border-color--hover': 'rgba(255, 240, 172, 0.1)',
                '--background-color--hover': 'rgba(255, 240, 172, 0.25)',
                '--background-color--checked': 'rgba(255, 240, 172, 0.2)'
              }
            },
            {
              id: 'miso',
              name: 'みそ',
              styles: {
                '--background-image': require('~/assets/images/miso.png'),
                '--background-size': '50%',
                '--border-color--hover': 'rgba(190, 120, 60, 0.1)',
                '--background-color--hover': 'rgba(190, 120, 60, 0.25)',
                '--background-color--checked': 'rgba(190, 120, 60, 0.2)'
              }
            },
            {
              id: 'mirin',
              name: 'みりん',
              styles: {
                '--background-image': require('~/assets/images/mirin.png'),
                '--background-size': '20%',
                '--border-color--hover': 'rgba(252, 211, 92, 0.1)',
                '--background-color--hover': 'rgba(252, 211, 92, 0.25)',
                '--background-color--checked': 'rgba(252, 211, 92, 0.2)'
              }
            }
          ]
        },
        {
          title: 'ら行',
          items: [
            {
              id: 'sake',
              name: '料理酒',
              styles: {
                '--background-image': require('~/assets/images/sake.png'),
                '--background-size': '20%',
                '--border-color--hover': 'rgba(253, 244, 214, 0.1)',
                '--background-color--hover': 'rgba(253, 244, 214, 0.25)',
                '--background-color--checked': 'rgba(253, 244, 214, 0.2)'
              }
            }
          ]
        }
      ]
    }
  }
})
</script>
<style lang="scss">
.condiments-list {
  padding: 10px;
  list-style: none;

  &__item {
    margin-bottom: 20px;
  }
  &__title {
    display: inline-block;
    font-size: 14px;
    background: linear-gradient(transparent 80%, #ffc0cb 90%);
    margin-bottom: 20px;
  }
  &__content {
    display: flex;
    flex-wrap: wrap;
  }
}
</style>
