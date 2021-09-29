<template>
  <div class="dnd">Let's fetch some DnD!</div>
  <div class="spell">Your spell for today is: <em>{{res.results[0].name}}</em></div>
</template>

<script>
import axios from 'axios'

export default {
  async setup () {
    const fetchDndData = async () => {
      const result = await axios.get('https://www.dnd5eapi.co/api/spells/?name=Acid+Arrow')
      return result.data
    }

    const res = await fetchDndData()
    return { res }
  }
}
</script>

<style>
  .dnd {
    font-size: 24px;
    margin-bottom: 15px;
  }
  .spell {
    margin-bottom: 15px;
  }
</style>
