<script setup lang="ts">
import {computed, ref} from "vue";

function useSomething() {
  const testRef = ref('test')
  const testComputed = computed(() => {
    if(testRef !== 'test') {
      return true
    } else {
      return false
    }
  })
  return {
    testComputed,
    testRef,
  }
}

const isTestComputedOk = computed(() => {
  const { testComputed } = useSomething()
  if (testComputed) {
    return 'yes'
  } else {
    return 'no'
  }
})

</script>

<template>
  <h1>
    Not important
  </h1>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
