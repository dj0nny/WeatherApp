<template>
  <div class="search">
    <div class="row">
      <div class="col-md-12">
        <form id="check-weather" @submit.prevent="submitSearch">
          <div class="form-row align-items-center">
            <div class="col-sm-6 my-1">
              <label class="sr-only" for="inlineFormInputName">Name</label>
              <input type="text" class="form-control" v-model="cityName" placeholder="City">
            </div>
            <div class="col-auto my-1">
              <button type="submit" class="btn btn-primary">Check Weather</button>
            </div>
          </div>
          <div class="error" v-if="isEmpty">
            This field cannot be empty
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Search',
  data: () => ({
    cityName: '',
    isEmpty: false,
  }),
  methods: {
    submitSearch() {
      if (this.cityName !== '') {
        this.isEmpty = false;
        this.$emit('triggeredSearch', this.cityName);
        this.cityName = '';
      } else {
        this.isEmpty = true;
      }
    },
  },
};
</script>
