<template>
  <div class="home">
    <home-content msg="Show me some doxygen content!" />
  </div>
</template>

<script>
// @ is an alias to /src
import HomeContent from '@/components/HomeContent'

export default {
  name: 'Home',
  components: {
    HomeContent
  }
}
</script>
