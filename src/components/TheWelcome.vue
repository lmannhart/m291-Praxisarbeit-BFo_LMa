<script setup>

</script>

<template>
  <table>
    <thead>
      <tr>
        <th></th>
        <th>Begegnung</th>
        <th>Wettbewerb</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="match in matches">
        <td class="thumbnail"><a :href="match.matchviewUrl" target="_blank"><img :src="match.thumbnail"></a> </td>
        <td>{{ match.title }}</td>
        <td>{{ match.competition }}</td>
      </tr>

    </tbody>
  </table>
</template>

<script>
export default {
  name: "MatchList",
  data() {
    return {
      matches: []
    }
  },
  created() {
    this.getMatches();
  },

  methods: {
    async getMatches() {
      const url =`https://www.scorebat.com/video-api/v3/feed/?token=[OTIyMjNfMTY4NjgyMDc2Nl9hNjdkN2UwYWRlZmU3YmUwOTBkOTk3OGEyY2RiODYxNTZkM2Q4ZjA2]`
      const response = await fetch(url);
      const data =  await response.json();
      this.matches = data.response.filter(item => item.videos[0].title === 'Live Stream');
    }
  }
};
</script>

<style>
.thumbnail a img {
  width: 200px;
}
</style>