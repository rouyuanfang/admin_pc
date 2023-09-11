<script setup lang="ts">
import { reactive } from 'vue'
import { useI18n } from 'vue-i18n'

const { t } = useI18n()

const footerMenu = reactive(
  [
    {
      title: 'airbnb',
      menus: [
        {
          name: 'careers',
          link: '/careers'
        },
        {
          name: 'news',
          link: '/press/news'
        },
        {
          name: 'topic',
          link: '/help/topic/1578/法律条款'
        },
        {
          name: 'diversity',
          link: '/diversity'
        },
        {
          name: 'accessibility',
          link: '/accessibility'
        }
      ]
    },
    {
      title: 'discovery',
      menus: [
        {
          name: 'trustAndSafe',
          link: '/trust'
        },
        {
          name: 'invite',
          link: '/invite?r=6'
        },
        {
          name: 'evection',
          link: '/work?s=footer'
        },
        {
          name: 'magzine',
          link: ''
        },
        {
          name: 'airbnborg',
          link: ''
        }
      ]
    },
    {
      title: 'rent',
      menus: [
        {
          name: 'whyRent',
          link: '/host/homes?from_footer=1'
        },
        {
          name: 'hospitality',
          link: '/hospitality'
        },
        {
          name: 'responsibleHosting',
          link: '/help/responsible-hosting'
        },
        {
          name: 'experiences',
          link: '/host/experiences?from_footer=1'
        },
        {
          name: 'resources',
          link: '/resources?traffic_source=footer'
        }
      ]
    },
    {
      title: 'service',
      menus: [
        {
          name: 'help',
          link: '/help?from=footer'
        },
        {
          name: 'neighbors',
          link: '/neighbors'
        }
      ]
    }
  ])
</script>

<template>
  <div class="footer-common">
    <div class="inner-footer">
      <ul>
        <li v-for="(item, index) in footerMenu" :key="index">
          <h3>{{ t(`footer['${item.title}']`) }}</h3>
          <a
            target="_blank"
            :href="itemInner.link"
            v-for="(itemInner, indexInner) in item.menus"
            :key="indexInner"
          >{{ t(`footer['${itemInner.name}']`) }}</a>
        </li>
      </ul>
      <div class="copy-right">@ 2022 Harry, Inc . All rights reserved.</div>
    </div>
  </div>
</template>

<style lang="scss">
@import "@/assets/scss/layout/commonFooter.scss";
</style>
