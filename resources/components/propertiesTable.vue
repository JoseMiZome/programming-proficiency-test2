<template>
  <div class="propertiesTable">
    <div class="flex flex-col">
      <div class="-my-2 overflow-x-auto sm:-px-6 lg:-px-8">
        <div class="py-2 align-middle inline-block min-w-full sm:px-6 lg:px-8">
          <div
            class="
              shadow
              overflow-hidden
              border-b border-gray-200
              sm:rounded-lg
            "
          >
            <table class="min-w-full divide-y divide-gray-200">
              <thead class="bg-gray-50">
                <tr>
                  <th
                    v-for="(header, index) in headers"
                    :key="index"
                    scope="col"
                    class="
                      px-6
                      py-3
                      text-left text-xs
                      font-medium
                      text-gray-500
                      uppercase
                      tracking-wider
                    "
                  >
                    {{ header.label }}
                  </th>
                </tr>
              </thead>
              <tbody class="bg-white divide-y divide-gray-200">
                  <tr v-for="(property, index) in properties" :key="index">
                    <td
                      v-for="(header, index) in headers"
                      :key="index"
                      class="px-6 py-4 whitespace-nowrap text-left"
                    >
                      {{ property[header.value] }}
                    </td>
                  </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "propertiesTable",
  props: {
    headers: { type: Array, required: true, default: () => [] },
    properties: { type: Array, required: true, default: () => [] },
  },
  mounted() {
    console.log(this.properties);
  },
};
</script>

<style scoped>
.propertiesTable {
}
</style>
