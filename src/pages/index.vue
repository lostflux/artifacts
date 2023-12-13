<script setup lang='ts'>
import { useTitle } from '@vueuse/core'
import { works } from '../works'
import { stringify } from '../utils/stringify'

const avaliable_works = works.filter(i => !i.draft)

useTitle('artifacts')
</script>

<template lang='pug'>
.paper
  .centered.index-page
    h1.font-mono.mb-2.text-lg.font-bold.mb-4 100 days
    pre.grid.gap-x-4.gap-y-1(class="grid-cols-1 sm:grid-cols-2 lg:grid-cols-3")
      router-link.link.block.mr-4(v-for='work of avaliable_works' :key='work.no' :to='`/${work.no}`')
        span.mr-2.opacity-50 {{ work.no }}
        b {{ work.name }}
    h1.font-mono.mb-2.mt-8
      a.link(href='https://amittai.studio' target='_blank') @siavava
      br
      span.text-gray-300 from 2022/12
</template>
