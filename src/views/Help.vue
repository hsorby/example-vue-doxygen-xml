<template>
  <div class="help">
    <doxygen-xml baseURL="/files" />
  </div>
</template>

<script>
// @ is an alias to /src
import { DoxygenXml } from 'vue-doxygen-xml'

export default {
  name: 'Home',
  components: {
    DoxygenXml
  }
}
</script>
