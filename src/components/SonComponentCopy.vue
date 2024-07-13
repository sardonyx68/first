<template>
    <!-- <img src="@/assets/images/main_4.jsp" width="300" height="150"> -->
    <h3>App.vue 11:07</h3>
    <hr color="blue">
    <h3>SonComponent.vue 문서 점심식사후</h3>
    <!-- <SonComponent>
      <template #mypage="{age, city}">
      나이 : {{ age }} <br>
      도시 : {{ city }}
      </template>
    </SonComponent> -->
    
    <div>
      이름 : <input type="text" size="5" @blur="testCap" :value="name" @input="$emit('update:name', $event.target.value)" ><br>
      hr   : <input type="text" size="5" :value="hp" @input="$emit('update:hp', $event.target.value)">
  
    </div>
  </template>
  
  <script>
  // import SonComponent from './components/SonComponent.vue'
  
  export default {
    name: 'SonComponent',
    // components: {
    //   SonComponent
    // },
    props : {
      name : { type: String,
               defalut: ''},
      hp : { type : Number,
             defalut : 0  }
    },
    emits : {
      event : '{update:name, update:hp}'
    },
    data () {
      return {
        interName : this.name,
        interHp : this.hp
      }
    },
    methods : {
      test(){ console.log("test메소드 함수")  },
      testCap(){ 
        //첫글자만 대문자표시 charAt(), toUppdercase(), slice(1) : 1번째부터 마지막까지
        const mycap = this.interName.charAt(0).toUpperCase() + this.interName.slice(1);
        this.$emit('update:name', mycap);
      }
    },
    created(){
      const mycap = this.interName.charAt(0).toUpperCase() + this.interName.slice(1);
      this.$emit('update:name', mycap);
  
    },
    watch : { //속성 항목값이 변경되면 자동갱신변경적용
      name(newVal){
        this.interName = newVal;
      },
      hp(newVal) {
        this.interHp = newVal;
      }
    }
  }
  </script>
  
  <style>
  #app {
    margin-top: 60px;
  }
  </style>
  