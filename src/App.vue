<template>
  <div class="container mx-auto px-4 py-6">
    <div class="max-w-md mx-auto bg-white rounded-xl shadow-md overflow-hidden md:max-w-2xl">
      <div class="p-8">
        <div class="text-xl font-bold">{{ value }}</div>
        <div class="mt-4">Date: {{ date }}</div>
        <div class="mt-4">Day: {{ day }}</div>
        <div class="mt-4">Month: {{ month }}</div>
        <div class="mt-4">
          <input class="border-2 border-gray-200 rounded p-1 w-full" type="text" v-model="input" />
        </div>
        <button
          class="bg-blue-500 text-white rounded px-4 py-2 mt-4 w-full"
          @click="changeTheWorld"
        >
          Change The World
        </button>
        <div class="flex justify-between mt-4">
          <button class="bg-green-500 text-white rounded px-2 py-1" @click="addDay">
            Add a day
          </button>
          <button class="bg-red-500 text-white rounded px-2 py-1" @click="addMonth">
            Add a month
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      input: '',
      date: new Date(),
      value: 'Hello World'
    }
  },
  computed: {
    day() {
      return this.date.getDate()
    },
    month() {
      return this.date.getMonth()
    }
  },
  methods: {
    addDay() {
      const newDate = new Date(this.date)
      newDate.setDate(newDate.getDate() + 1)
      this.date = newDate
    },
    addMonth() {
      const newDate = new Date(this.date)
      newDate.setMonth(newDate.getMonth() + 1)
      this.date = newDate
    },
    changeTheWorld() {
      this.value = this.input
    }
  },
  watch: {
    input() {
      console.log('Input changed')
    }
  }
}
</script>
