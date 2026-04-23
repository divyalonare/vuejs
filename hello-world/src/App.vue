<template>
  <div>
    <pre>
      {{ JSON.stringify(formValues, null, 2) }}
    </pre>
  </div>
  <form @submit.prevent="submitForm">
  <div class="form-row">
    <label for="name">Name:</label>
    <input type="text" id="name" v-model.trim.lazy="formValues.name"/>
  </div>
  
  <div class="form-row">
    <label for="email">Email:</label>
    <input type="email" id="email" v-model.trim.lazy="formValues.email"/>
  </div>
  
  <div class="form-row">
    <label for="age">Age:</label>
    <input @keyup.enter="submitForm" type="number" id="age" v-model.number="formValues.age"/>
  </div>
  
  <div class="form-row">
    <label for="country">Country:</label>
    <select id="country" v-model="formValues.country">
      <option value="">select a country</option>
      <option value="India">India</option>
      <option value="vietnam">Vietnam</option>
      <option value="singapore">Singapore</option>
    </select>
  </div>
  
  <div class="form-row">
    <label for="joblocation">Job Location:</label>
    <select id="joblocation" multiple v-model="formValues.jobLocation">
      <option value="India">India</option>
      <option value="vietnam">Vietnam</option>
      <option value="singapore">Singapore</option>
    </select>
  </div>

  <div>
    <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork" true-value="yess" false-value="no"/>
    <label for="remoteWork">Willing to work remotely ?</label>
  </div>

  <div class="checkbox-group">
  <label class="group-label">Skill set</label>
  <div class="checkbox-row">
    <input type="checkbox" id="html" value="HTML" v-model="formValues.SkillSet"/>
    <label for="html">HTML</label>
  </div>
  <div class="checkbox-row">
    <input type="checkbox" id="css" value="CSS" v-model="formValues.SkillSet"/>
    <label for="css">CSS</label>
  </div>
  <div class="checkbox-row">
    <input type="checkbox" id="javascript" value="JavaScript" v-model="formValues.SkillSet"/>
    <label for="javascript">JavaScript</label>
  </div>
</div>
<div>
  <label>Years Of Experience</label>
  <input type="radio" id="0-2" value="0-2" v-model="formValues.YearsOfExperience"/>
  <label for="0-2">0-2</label>
  <input type="radio" id="3-5" value="3-5" v-model="formValues.YearsOfExperience"/>
  <label for="3-5">3-5</label>
  <input type="radio" id="6-10" value="6-10" v-model="formValues.YearsOfExperience"/>
  <label for="6-10">6-10</label>
</div>
<div>
  <button type="submit">Submit</button>
</div>
</form>

 <div>{{greet}} {{ name }}</div>
 <div v-html='channel'></div>
 <div v-text="name"></div>
  <h3 :id='headingId'>Welcome to Vue.js</h3>
  <button :disabled="!isDisabled">bind</button>
  <h4 class="underline">This is an underlined text</h4>
  <h2 class="underline" :class="status">status</h2>
  <h2 :class="ispromoted && 'promoted'">promoted movie</h2>
  <h2 :class="issoldout ? 'sold-out' :'new'">soldout? movie</h2>
  <h2 :class="['new','promoted']">new and promoted movie</h2>
  <h2 :style="{
    color: higlightColor,
    'font-size': HeaderSize + 'px',
    padding: '10px',
    }">highlighted text</h2>
  <h1 :style="HeaderStyleObject">styled object</h1>
  <div :style="[baseStyleObject,sucessStyleObject]">joint multiple styles</div>
  <div :style="[baseStyleObject,dangerStyleObject]">danger styles</div>
  <h2 v-if="num === 0">Number is zero</h2>
  <h2 v-else-if="num > 0">no. is positive</h2>
  <h2 v-else-if="num < 0">no. is negative</h2>
  <h2 v-else>Is not a no.</h2>
  <div v-if="display">
    <h2>Divya</h2>
    <h2>VueJs</h2>
  </div>
  <h2 v-show="showElement">Show Element</h2>
  <h2 v-for="(name, index) in people" :key="name">{{ index }} {{ name }}</h2>
  <h2 v-for="person in fullnames" :key="person.first">{{ person.first }} {{ person.last }}</h2>
  <div v-for="actor in actors" :key="actor.name">
    <h2>{{ actor.name }}</h2>
     <h3>{{ actor.age }}</h3>
     <h3 v-for="age in actors.age" :key="age">{{ age }}</h3>
    <h3 v-for="movie in actor.movies" :key="movie">{{ movie }}</h3>
  </div>
  <h2 v-for="(value,key,index) in myinfo" :key="value">{{index}} {{key}} {{ value }}</h2>
  <template v-for="name in names" :key="name">
    <h2 v-if="name === 'divya'">{{ name }}</h2>
  </template>
  <h2>{{ 4+5 }}</h2>
  <h2> add method - {{ add(2,3,4) }}</h2>
  <h2> add method - {{ add(7,8,9) }}</h2>
  <h2> multiply method - {{ multiply(basevalue) }}</h2>
  <div>
    <h2 v-pre>{{ namevar }}</h2>
    <h2>{{ namevar }}</h2>
    <button v-on:click="namevar = 'DIVYA'">Change Name</button>
    <button v-on:mouseover="namevar = 'Divya'">Change Name</button>
  </div>
  <div>
    <h2>Count: {{ count }}</h2>
    <button @click="increment(1)">Increment 1</button>
    <button @click="decrement(1)">Decrement 1</button>
    <button @click="increment(5)">Increment 5</button>
    <button @click="decrement(5)">Decrement 5</button>
  </div>
  <div>
  <h2>Fullname - {{ firstname }} {{ lastname }}</h2>
  <h2>Fullname using computed - {{ fullname }}</h2>
  <button @click="changeFullname">change name</button>
  <button @click="items.push({ id: 4, name: 'tablet', price: 500 })">Add Item</button>
  <h2> Total - {{ items.reduce((total, curr) => (total = total + curr.price), 0) }}</h2>
  <h2> Total using computed - {{ total }}</h2>
 </div>
 <template v-for="item in items" :key="item.id">
    <h2 v-if="item.price > 1000">{{ item.name }} - {{ item.price }}</h2>
 </template>
  <h2 v-for="item in expensiveItems" :key="item.id">{{ item.name }} - {{ item.price }}</h2>
  <h2>volume Tracker (0-20)</h2>
  <h3>current Volume - {{ volume }}</h3>
  <button @click="volume +=2">Increase Volume</button>
  <button @click="volume -=2">Decrease Volume</button>
  <input type="text" v-model="movie">
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      formValues: {
        name: '',
        email: '',
        age: null,
        country: '',
        jobLocation: [],
        remoteWork: false,
        SkillSet: [],
        YearsOfExperience: ''
      },
      items: [
        { id: 1, name: 'tv', price: 2000 },
        { id: 2, name: 'phone', price: 1000 },
        { id: 3, name: 'laptop', price: 1500 }
      ],
      movie:'bat',
      volume: 0,
      firstname: 'Divya',
      lastname: 'Lonare',
      greet: 'hello',
      name: 'divya',
      channel: '<b>Techie Delight</b>',
      headingId: 'main-heading',
      isDisabled:true,
      status: 'isdanger',
      ispromoted:true,
      issoldout:true,
      higlightColor:'orange',
      HeaderSize: 50,
      HeaderStyleObject:{
        color:'blue',
        fontSize:'40px',
        padding:'20px',
        border:'3px solid black'
      },
      baseStyleObject: {
        color: 'darkgreen',
        fontSize: '30px',
        padding: '15px',
      },
      sucessStyleObject: {
        border: '2px solid green',
        backgroundColor: 'lightgreen',
        padding: '10px',
      },
      dangerStyleObject: {
        border: '2px solid red',
        backgroundColor: 'lightcoral',
        padding: '10px',
      },
      num: 8,
      display :true,
      showElement: true,
      names:['divya', 'clark','diana'],
      people: ['divya', 'clark','diana'],
      fullnames:[
        {first:'Divya', last:'Lonare'},
        {first:'Clark', last:'Kent'},
        {first:'Diana', last:'Prince'}
      ],
      actors :[ 
        {
          name: 'robert downey jr',
          age: 58,
          movies: ['ironman','avengers','sherlock holmes']  
        },
        {
          name: 'chris evans',
          age: 42,
          movies: ['captain america','avengers','snowpiercer']
        },
      ],
      myinfo: {
        name: 'divya',
        age: 20,
        city: 'sausar'
      },
      baseMultiplier: 5,
      basevalue: 10,
    namevar: 'Disha',
    count:0
    }
  },
  computed: {
    fullname: {
      get() {
        return `${this.firstname} ${this.lastname}`;
      },
      set(value) {
        const names = value.split(' ');
        this.firstname = names[0];
        this.lastname = names[1];
      }
    },
    total() {
      return this.items.reduce((total, curr) => total + curr.price, 0);
    },
    expensiveItems() {
      return this.items.filter(item => item.price > 1000);
    }
  },
  methods: {
    add(a, b, c) {
      return a + b + c;
    },
    multiply(num) {
      return num * this.baseMultiplier;
    },
    increment(num) {
      this.count += num;
    },
    decrement(num) {
      this.count -= num;
    },
    submitForm() {
      console.log('Form values:', this.formValues);
    },
    changeFullname() {
      this.fullname = 'Divyaaa Lonareee ';
    }
  },
  watch: {
    volume(newValue, oldValue) {
      if (newValue > oldValue && newValue === 16) {
        alert('Volume is too high');
      }
    },
    movie : {
      handler (newValue) {
      console.log(`calling api for movie: ${newValue}`);
    },
      immediate: true,
    },
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
form {
  max-width: 600px;
  margin: 0 auto;  /* center the form */
  padding: 20px;
}
.form-row {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 15px;
}

.form-row label {
  min-width: 120px;  /* same width for all labels */
  text-align: right;
}

.form-row select,
.form-row input {
  flex: 1;  /* dropdowns take remaining space */
  max-width: 300px;
}

.underline{
  text-decoration: underline;
  
}
.promoted{
  font-style:italic;
}
.new{
  color:green;
}
.sold-out{
  color:red
}

input[type='text'],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
}
.checkbox-group {
  margin: 20px 0;
}

.group-label {
  display: block;
  font-weight: bold;
  margin-bottom: 10px;
}

.checkbox-row {
  display: flex;
  align-items: center;
  gap: 8px;
  margin-bottom: 8px;
}

.checkbox-row input[type="checkbox"] {
  width: auto;      /* override display:block */
  margin: 0;
  flex-shrink: 0;
}

.checkbox-row label {
  min-width: unset; /* override form-row label width */
  text-align: left;
  margin: 0;
  cursor: pointer;
}

</style>
