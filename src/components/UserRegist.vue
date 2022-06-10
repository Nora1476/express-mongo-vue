<template>
  <div>
      <form id="user-form" ref="userform">
        <fieldset>
          <legend>사용자 등록</legend>
          <div><input id="username" ref="usrname" type="text" placeholder="이름"></div>
          <div><input id="age" ref="age" type="number" placeholder="나이"></div>
          <div><input id="married" ref="married" type="checkbox"><label for="married">결혼 여부</label></div>
          <button type="submit" @click.prevent="regist">등록</button>
        </fieldset>
      </form>
    </div>
</template>

<script>
import { reactive, ref } from '@vue/reactivity';
export default {
    name:'ToRegist',
    setup(){
        const state = reactive({

        })

        const userform = ref(null)
        const username = ref(null)
        const age = ref(null)
        const married = ref(null)

        function regist() {
            async (e) => {
            e.preventDefault();
            if (!username) {
                return alert('이름을 입력하세요');
            }
            if (!age) {
                return alert('나이를 입력하세요');
            }
            try {
                await axios.post('/users', { username, age, married });
                getUser();
            } catch (err) {
                console.error(err);
            }
            e.target.username.vlaue.value = '';
            e.target.age.value.value = '';
            e.target.married.value.checked = false;

            userform.value.submit();
        }

         
        return{
            state, userform, username, age, married, regist,
            }
        }
    }
}
</script>

<style>

</style>