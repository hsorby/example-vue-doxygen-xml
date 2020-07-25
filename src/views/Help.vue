<template>
  <div class="help">
    <template v-if="isRoot">
      <ul>
        <li>
          <router-link
            :to="{
              name: 'Help',
              params: { version: 'v0.1.0' }
            }"
            >v0.1.0</router-link
          >
        </li>
        <li>
          <router-link
            :to="{
              name: 'Help',
              params: { version: 'v0.2.0' }
            }"
            >v0.2.0</router-link
          >
        </li>
      </ul>
    </template>
    <template v-else>
      <v-select
        :options="['v0.1.0', 'v0.2.0']"
        :clearable="false"
        :closeOnSelect="true"
        :value="version"
        @input="setSelected"
      ></v-select>
      <doxygen-xml :baseURL="`/doxygen/${this.version}`" />
    </template>
  </div>
</template>

<script>
import vSelect from 'vue-select'
import 'vue-select/dist/vue-select.css'

import { DoxygenXml } from 'vue-doxygen-xml'

export default {
  name: 'Help',
  components: {
    DoxygenXml,
    vSelect
  },
  data() {
    return {
      version: ''
    }
  },
  watch: {
    $route(to) {
      if (to.params.version !== this.version) {
        this.version = to.params.version
      }
    }
  },
  created() {
    this.version = this.$route.params.version
  },
  computed: {
    isRoot() {
      return this.$route.name === 'HelpRoot'
    }
  },
  methods: {
    setSelected(value) {
      if (value) {
        this.version = value
        if (this.$route.params.version !== value) {
          this.$router.push({
            name: 'Help',
            params: { version: value, pageName: this.$route.params.pageName }
          })
        }
      }
    }
  }
}
</script>
