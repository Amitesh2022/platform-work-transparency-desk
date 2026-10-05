<script setup lang="ts">
import { onMounted } from 'vue'
import { storeToRefs } from 'pinia'
import { RouterLink, RouterView } from 'vue-router'
import { useDeliveryStore } from './store'
const store = useDeliveryStore()
const { approvedShare, offers, urgent } = storeToRefs(store)
onMounted(store.load)
</script>

<template><div class="shell"><aside><div class="brand">PlatformFairEU<span>ALGORITHMIC TRANSPARENCY</span></div><nav><RouterLink to="/">Transparency reviews</RouterLink><RouterLink to="/insights">Worker guidance</RouterLink></nav><div class="health"><i /> Java platform work service connected</div></aside><main><header><div><span class="eyebrow">Build a diverse workforce for Europe’s digital labour platforms</span><h1>Platform Work Transparency Desk</h1></div><button @click="store.addOffer">Add transparency review</button></header><section class="summary"><article><small>Plans ready</small><strong>{{ approvedShare }}%</strong><div class="bar"><span :style="{ width: `${approvedShare}%` }" /></div></article><article><small>Plans tracked</small><strong>{{ offers.length }}</strong><p>Shared workforce view</p></article><article><small>High-priority blockers</small><strong>{{ urgent }}</strong><p>Needs attention</p></article></section><RouterView /></main></div></template>
