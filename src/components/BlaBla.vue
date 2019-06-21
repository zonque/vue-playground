<template>
        <div>
                <h1>{{ data.one }}</h1>
                <h1>{{ data.two }}</h1>
                <p>Year: {{ year }}</p>
        </div>
</template>

<script>
export default {
  name: 'BlaBla',
  props: {
    data: Object,
    year: Number
  },
  watch: {
          data: function(val) {
                  this.makePlot();
          },
          year: function(val) {
                  this.makePlot();
          }
  },
  mounted() {
  },
  methods: {
     makePlot() {
          console.log("MAKE PLOT for year", this.year, this.data);
     }
  }
}
</script>

<style scoped>
</style>
