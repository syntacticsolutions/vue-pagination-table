<template>
  <div id="app">
    <Table v-if="tableData" :theData="tableData" :config="config" :style="{height: '600px'}"/>
  </div>
</template>

<script>
import Table from './components/Table'

export default {
  components: {
    Table
  },
  data: () => ({
    tableData: undefined,
    config: [
      {
        key: 'avatar',
        title: 'Avatar',
        type: 'image'
      },
      {
        key: 'name',
        title: 'Name',
        type: 'text'
      },
      {
        key: 'city',
        title: 'City',
        type: 'text'
      },
      {
        key: 'companyName',
        title: 'Company',
        type: 'text'
      },
      {
        key: 'createdAt',
        title: 'Signup Date',
        type: 'date'
      }
    ]
  }),
  mounted () {
    this.$axios.get('https://5e4b062d6eafb7001488c99e.mockapi.io/something123/users')
    .then(({data}) => {
      this.tableData = data
    })
  }
}
</script>

<style>

body {
  font-family: Helvetica, sans-serif;
  font-weight: 400;
}
</style>
