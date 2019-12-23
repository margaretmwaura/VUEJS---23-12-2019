<template>
  <div id="app-one">
    <p v-once>{{ message }}</p>
    <span>Enter your name:</span>
    <br>
    <br>
    <input v-model="message">
    <br>
    <br>
    <span> Dear {{ message }}</span><p v-once>{{ messagetwo }}</p>

    <ol v-for="item in properties" :key="item">
      <li>{{item.text}}</li>
    </ol>

    <p>Pick a choice between one and two</p>

    <input type="checkbox" id="Alma" value="Alma" v-model="checkedNames">
    <label for="Alma">Alma</label>
    <input type="checkbox" id="Karen" value="Karen" v-model="checkedNames">
    <label for="Karen">Karen</label>
    <br>
    <span>Checked names: {{ checkedNames }}</span>
    <br>
    <br>
    <select v-model="selected">
      <option disabled value="">Please select one</option>
      <option>Pay by cash</option>
      <option>Pay by Visa Card</option>
      <option>Mpesa</option>
    </select>
    <span>Selected: {{ selected }}</span>

    <br>
    <br>
    <span v-if="selected === 'Pay by cash'"> You can proceed to the accounts office</span>
    <span v-else-if="selected === 'Pay by Visa Card'">Please proceed to the bank</span>
    <span v-else-if="selected === 'Mpesa'">The organization cannot help you</span>
    <span v-else>Please select</span>

    <div :class="{red:isActive , green:hasNoError}">

      <p>Finish by submitting </p>
      <button @click="isActive=!isActive">Click me</button>
      <button @click="hasNoError=!hasNoError">Click me for change in text color</button>
    </div>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data(){
    return{
      message: 'Client',
      messagetwo: ' we are very happy that you have choosen to invest with us this  time of the year,' +
    'fill in the following details  and choose an item',
      properties: [
                       {id: 0, text: 'AlmaRidge hometown'},
                       {id: 1, text: 'Karen dagoretti rural'},
                  ],
      checkedNames: [],
      selected: '',
      isActive:false,
      hasNoError: true
    }

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .red{
    background-color:blue;
  }
  .green{
    color:indianred;
  }
</style>
