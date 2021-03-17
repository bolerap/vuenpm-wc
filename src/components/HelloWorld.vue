<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <div class="calendar">
      <b-row>
        <b-col md="auto">
          <b-calendar
            v-model="value"
            @context="onContext"
            locale="en-US"
          ></b-calendar>
        </b-col>
        <b-col>
          <p>
            Value: <b>'{{ value }}'</b>
          </p>
          <p class="mb-0">Context:</p>
          <pre class="small">{{ context }}</pre>
        </b-col>
      </b-row>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      value: "",
      context: null
    };
  },
  methods: {
    onContext(context: any) {
      this.context = context;
    }
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.calendar {
  display: flex;
  justify-content: center;
  align-items: center;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
