<script lang="ts" setup>
  import { Icon } from '@iconify/vue';
  import {
    useDashboard,
    LoadingStatus,
    type ChainConfig,
  } from '@/stores/useDashboard';
  import ChainSummary from '@/components/ChainSummary.vue';
  import { computed, ref } from 'vue';
  import { useBlockchain } from '@/stores';
  
  const dashboard = useDashboard();
  
  const keywords = ref('');
  const chains = computed(() => {
    if (keywords.value) {
      return Object.values(dashboard.chains).filter(
        (x: ChainConfig) => x.chainName.indexOf(keywords.value) > -1
      );
    } else {
      return Object.values(dashboard.chains);
    }
  });
  const chainStore = useBlockchain()
  </script>
  <template>
    <div class="">
      <div class="flex md:!flex-row flex-col items-center justify-center mb-6 mt-14 gap-2">
        <div class="w-16 rounded-full">
<svg version="1.0" xmlns="http://www.w3.org/2000/svg"
 width="75.000000pt" height="75.000000pt" viewBox="0 0 75.000000 75.000000"
 preserveAspectRatio="xMidYMid meet">

<g transform="translate(0.000000,75.000000) scale(0.100000,-0.100000)"
fill="#000000" stroke="none">
<path d="M452 610 c0 -19 2 -27 5 -17 2 9 2 25 0 35 -3 9 -5 1 -5 -18z"/>
<path d="M522 605 c-6 -14 -8 -25 -3 -25 8 0 23 41 17 47 -1 2 -8 -8 -14 -22z"/>
<path d="M380 593 c0 -4 5 -15 10 -23 8 -13 10 -13 10 2 0 9 -4 20 -10 23 -5
3 -10 3 -10 -2z"/>
<path d="M576 574 c-4 -10 -1 -14 6 -12 15 5 23 28 10 28 -5 0 -13 -7 -16 -16z"/>
<path d="M335 540 c3 -5 13 -10 21 -10 8 0 12 5 9 10 -3 6 -13 10 -21 10 -8 0
-12 -4 -9 -10z"/>
<path d="M620 540 c-20 -12 -5 -24 16 -12 9 5 12 12 7 15 -5 3 -15 2 -23 -3z"/>
<path d="M134 483 c-15 -27 -28 -50 -30 -52 -2 -2 -23 13 -47 33 l-44 36 -7
-37 c-11 -70 -7 -123 9 -123 11 0 15 11 15 39 0 52 11 57 45 21 16 -17 32 -30
35 -30 4 0 15 18 25 40 10 23 22 43 26 46 5 3 18 -14 29 -37 19 -37 23 -40 37
-27 13 14 11 22 -17 72 -18 31 -36 58 -40 61 -4 3 -20 -16 -36 -42z"/>
<path d="M295 488 c-66 -38 -59 -121 13 -142 29 -9 62 1 62 20 0 9 -11 14 -33
14 -32 0 -57 14 -57 32 0 5 9 4 21 -2 27 -15 66 -5 79 20 9 16 6 25 -14 45
-28 28 -41 30 -71 13z m53 -40 c-6 -17 -40 -17 -45 0 -3 7 5 12 22 12 17 0 25
-5 23 -12z"/>
<path d="M437 470 c-32 -25 -41 -53 -27 -79 17 -33 47 -45 81 -30 50 20 66 80
31 112 -25 23 -54 21 -85 -3z m66 -34 c3 -8 -3 -22 -13 -31 -21 -19 -50 -14
-50 8 0 32 52 51 63 23z"/>
<path d="M710 454 l-12 -36 -28 33 -27 33 -13 -38 -12 -39 -20 31 c-12 19 -25
29 -34 25 -8 -3 -14 -7 -14 -9 0 -4 60 -107 66 -113 2 -3 12 14 21 37 l16 42
27 -31 26 -32 23 56 c21 52 22 77 1 77 -5 0 -14 -16 -20 -36z"/>
<path d="M737 281 c-4 -17 -16 -35 -29 -42 -13 -6 -33 -20 -44 -31 -19 -17
-27 -18 -60 -9 -21 6 -40 8 -42 6 -3 -3 13 -31 35 -62 22 -32 43 -68 47 -80 9
-30 53 -63 82 -63 21 0 24 5 24 34 0 30 -3 35 -27 38 -21 2 -29 9 -31 27 -4
28 21 53 44 44 11 -4 14 11 14 81 0 47 -2 86 -4 86 -2 0 -6 -13 -9 -29z m-109
-109 c7 -5 10 -16 6 -26 -6 -15 -7 -15 -20 1 -22 30 -15 43 14 25z"/>
<path d="M435 278 c-2 -7 -5 -26 -7 -43 -3 -26 -10 -32 -56 -48 -52 -18 -52
-18 -83 3 -16 12 -32 20 -34 18 -2 -2 2 -30 10 -63 7 -33 17 -78 22 -100 l8
-40 121 -3 c119 -3 122 -2 128 20 11 44 6 66 -39 156 -25 50 -45 95 -45 101 0
15 -20 14 -25 -1z m33 -67 c9 -26 8 -28 -9 -24 -13 4 -18 11 -15 20 3 8 6 19
6 24 0 18 8 9 18 -20z m-158 -60 c0 -12 -20 -36 -20 -24 0 6 -3 19 -6 27 -5
12 -2 15 10 10 9 -3 16 -9 16 -13z m160 -1 c22 -41 -14 -84 -45 -54 -19 20
-19 38 1 58 21 21 31 20 44 -4z m-90 -39 c20 -38 -16 -74 -45 -45 -18 19 -19
36 -3 52 18 18 36 15 48 -7z"/>
<path d="M431 147 c-14 -17 -4 -47 15 -47 22 0 29 29 12 46 -13 13 -16 13 -27
1z"/>
<path d="M340 105 c-14 -16 -5 -35 16 -35 15 0 20 35 5 44 -5 3 -14 -1 -21 -9z"/>
<path d="M703 114 c-3 -8 -1 -20 5 -26 16 -16 42 -2 42 22 0 24 -38 28 -47 4z"/>
</g>
</svg>
        </div>
        <h1 class="text-primary dark:invert text-3xl md:!text-6xl font-bold">
          {{ $t('pages.title') }}
        </h1>
        <div class="badge badge-primary badge-outline dark:invert mt-1 text-sm md:!mt-8">
          {{ $t('pages.tag') }}
        </div>
      </div>
      <div class="text-center text-base">
        <p class="mb-1">
          {{ $t('pages.slogan') }}
        </p>
        <h2 class="mb-6">{{ $t('pages.description') }}</h2>
      </div>
      <div
        v-if="dashboard.status !== LoadingStatus.Loaded"
        class="flex justify-center"
      >
        <progress class="progress progress-info w-80 h-1"></progress>
      </div>
  
      <div class="flex items-center rounded-lg bg-base-100  border border-gray-200 dark:border-gray-700 mt-10">
        <Icon icon="mdi:magnify" class="text-2xl text-gray-400 ml-3"/>
        <input :placeholder="$t('pages.search_placeholder')" class="px-4 h-10 bg-transparent flex-1 outline-none text-base" v-model="keywords" />
        <div class="px-4 text-base hidden md:!block">{{ chains.length }}/{{ dashboard.length }}</div>
      </div>
  
      <div
        class="grid grid-cols-1 gap-4 mt-6 md:!grid-cols-3 lg:!grid-cols-4 2xl:!grid-cols-5"
      >
        <ChainSummary
          v-for="(chain, index) in chains"
          :key="index"
          :name="chain.chainName"
        />
      </div>
    </div>
  </template>
  
  <style scoped>
   .logo path{
    fill: #131313;
  }
  </style>
  
