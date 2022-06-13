<template>
  <div>
      <form id="user-form" ref="userform" action="">
        <fieldset>
          <legend>사용자 등록</legend>
          <div><input id="username" ref="usrname" type="text" placeholder="이름"></div>
          <div><input id="age" ref="age" type="number" min="1"  placeholder="나이"></div>
          <div><input id="married" ref="married" type="checkbox"><label for="married">결혼 여부</label></div>
          <button type="submit" id="uBtn" @click.prevent="uRegist">등록</button>
        </fieldset>
      </form>
    </div>
</template>

<script>
import { reactive, ref } from '@vue/reactivity';
export default {
    name:'ToUserRegist',
    setup(){
        const state = reactive({

        })

        const userform = ref(null)
        const username = ref(null)
        const age = ref(null)
        const married = ref(null)

        function uRegist() {
            if (username.vlaue.vlaue=="") {
                alert('이름을 입력하세요');
                username.value.focus();
                return

            }
            if (age.value.value=="") {
                alert('나이를 입력하세요');
                age.value.focus();
                return
            }

            userform.value.submit();
        }

         
        return{
            state, userform, username, age, married, uRegist,
            }
        }
    }
</script>

<style>
#user-form {
  width: 40%;
  margin:0 auto;
}

#username,
#age,
#married,
#uBtn {
  margin :10px;
}
</style>