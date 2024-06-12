 <template>
    <div class="card shadow mb-4">
      <div class="card-header py-3">
        <h6 class="m-0 font-weight-bold text-primary">카테고리별 소비</h6>
      </div>
      <div class="card-body">
        <div class="row">
          <div class="col-lg-8">
            <div class="chart-pie pt-4">
              <canvas id="myPieChart"></canvas>
            </div>
          </div>
          <div class="col-lg-4">
            <div id="pieChartLegend" class="mt-4"></div>
            <div id="totalAmount" class="mt-4">총 지출액: {{ totalAmount }}원</div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import Chart from 'chart.js/auto';
  import { useBudgetStore } from '@/stores/budgetStore';
  
  export default {
    data() {
      return {
        chartData: [],
        totalAmount: 0,
        myPieChart: null,
      };
    },
    mounted() {
      this.fetchData();
    },
    methods: {
      async fetchData() {
        const budgetStore = useBudgetStore();
        try {
          await budgetStore.getTransactions();
          const outcomeData = budgetStore.transactions.filter(item => item.type === '출금');
          const categories = outcomeData.map(item => item.category);
          const amounts = outcomeData.map(item => parseFloat(item.amount));
          this.chartData = { categories, amounts };
          this.totalAmount = amounts.reduce((acc, curr) => acc + curr, 0);
          this.updatePieChart();
        } catch (err) {
          console.error('Error fetching data:', err);
        }
      },
      updatePieChart() {
        if (this.myPieChart) {
          this.myPieChart.destroy();
        }
        var ctxPie = document.getElementById("myPieChart");
        this.myPieChart = new Chart(ctxPie, {
          type: 'doughnut',
          data: {
            labels: this.chartData.categories,
            datasets: [{
              data: this.chartData.amounts,
              backgroundColor: ['#f6c23e', '#36b9cc', '#4e73df', '#1cc88a', '#6610f2', '#e74a3b'],
              hoverBackgroundColor: ['#f0c24e', '#2a96ad', '#375abd', '#17a673', '#5a1de1', '#d73a28'],
              hoverBorderColor: "rgba(234, 236, 244, 1)",
            }],
          },
          options: {
            maintainAspectRatio: false,
            tooltips: {
              enabled: false
            },
            legend: {
              display: false
            },
            cutoutPercentage: 80,
          },
        });
  
        var pieChartLegend = document.getElementById("pieChartLegend");
        pieChartLegend.innerHTML = ''; // Clear previous legend items
        this.chartData.categories.forEach((category, index) => {
          const legendItem = document.createElement("div");
          const percentage = ((this.chartData.amounts[index] / this.totalAmount) * 100).toFixed(1);
          legendItem.innerHTML = `<span>${category}: ${this.chartData.amounts[index]} 원 (${percentage}%)</span>`;
          pieChartLegend.appendChild(legendItem);
        });
      }
    }
  }
  </script> 