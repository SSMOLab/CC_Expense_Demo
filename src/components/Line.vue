 <template>
  <div>
    <div class="text-xs text-title px-4">2021/01 ~ 2021/05 消費分析</div>
    <apexchart
      width="380"
      height="120"
      type="line"
      :options="options"
      :series="series"
    ></apexchart>
  </div>
</template>

<script>
export default {
  props: {
    dataLabels: {
      default: false,
      type: Boolean
    },
    showYLabels: {
      default: true,
      type: Boolean
    }
  },
  data: function() {
    return {
      options: {
        grid: {
          padding: {
            top: 0,
            left: 20,
            right: 20
          }
        },
        stroke: {
          curve: "smooth"
        },
        chart: {
          id: "vuechart-example",
          toolbar: {
            show: false
          }
        },
        xaxis: {
          categories: ["1月", "2月", "3月", "4月", "5月", "6月"]
        },
        dataLabels: {
          enabled: this.dataLabels
        },
        yaxis: {
          show: this.showYLabels
        }
      },
      series: [
        {
          name: "series-1",
          data: [2000, 3000, 4505, 3500, 4900, 5844]
        }
      ]
    };
  },
  mounted() {
    this.series = [
      {
        name: "series-1",
        data: [2000, 3000, 4505, 3500, 4900, 5844]
      }
    ];
  }
};
</script>