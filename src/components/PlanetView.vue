<template>
  <border-box>
    <template slot="header">
      <h2 class="card-header-title">
        Planet
      </h2>
      <button
        class="card-header-icon no-border dark"
        title="Edit planets stats for a colonised planet"
        @click="$emit('editClicked')"
      >
        <lead-pencil-icon />
      </button>
    </template>

    <table>
      <thead>
        <tr>
          <th />
          <th>Stored</th>
          <th>Abundance</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>
            <img
              :src="`${imgDG}/units/small/metal.gif`"
              title="Metal"
              class="image-header"
            > Metal
          </td>
          <td class="resource-metal">
            {{ planet.stored.metal }}
          </td>
          <td class="resource-metal">
            {{ planet.abundances.metal }}%
          </td>
        </tr>
        <tr>
          <td>
            <img
              :src="`${imgDG}/units/small/mineral.gif`"
              title="Mineral"
              class="image-header"
            > Mineral
          </td>
          <td class="resource-mineral">
            {{ planet.stored.mineral }}
          </td>
          <td class="resource-mineral">
            {{ planet.abundances.mineral }}%
          </td>
        </tr>
        <tr>
          <td>
            <img
              :src="`${imgDG}/units/small/energy.gif`"
              title="Energy"
              class="image-header"
            > Energy
          </td>
          <td class="resource-energy">
            {{ planet.stored.energy }}
          </td>
          <td class="resource-energy">
            {{ planet.abundances.energy }}%
          </td>
        </tr>
        <tr>
          <td>
            <img
              :src="`${imgDG}/units/small/worker.gif`"
              title="Workers"
              class="image-header"
            > Workers
          </td>
          <td class="workers">
            {{ planet.stored.pop }}
          </td>
          <td />
        </tr>
      </tbody>
    </table>
  </border-box>
</template>

<script>
import BorderBox from '../components/BorderBox'
import LeadPencilIcon from 'mdi-vue/LeadPencil.vue'

export default {
  components: {
    BorderBox,
    LeadPencilIcon
  },
  props: {
    planet: {
      type: Object,
      required: true
    }
  },
  data () {
    return {
      /**
       * Link to the website of Dark Galaxy to get images
       */
      imgDG: 'https://beta.darkgalaxy.com/images'
    }
  }
}
</script>

<style scoped>
.no-border {
  border: none;
}

.dark {
  color: whitesmoke;
  background-color: #1a1a1a;
}
</style>
