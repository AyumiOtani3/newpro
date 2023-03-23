<template>
  <div id='mytable' ref="table"/>
</template>

<script>
export default {
  name: 'MyTable',
  props: {
    msg: String
  },
  mounted() {
    this.initTable();
  },

  methods: {
    initTable() {
      jspreadsheet(this.$refs.table, {
        data: [
          ['2023/03/01', 'youTube', 1000, 30000],
          ['2023/03/01', 'instagram', 1200, 5000],
          ['2023/03/01', 'Facebook', 800, 500],
          ['2023/03/01', 'Tiktok', 750, 2000],
          ['2023/03/01', 'Twitter', 900, 4000],
        ],
        columns: [
          { type: 'calendar', title: 'date', width: 120, options: { format: 'YYYY/MM/DD' } },
          { type: 'text', title: 'SNS', width: 300 },
          { type: 'numeric', title: 'subscribe', width: 200, mask:'#,##' },
          { type: 'numeric', title: 'like', width: 200, mask:'#,##' },
          { type: "checkbox", title: "Stock", width: "80px" },
          {
            type: "dropdown",
            title: "Make",
            width: "250px",
            source: ["video", "photo", "text",]
          },
        ],
        // toolbar:true,
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
