<template>
   <form id="comment-form" ref="commentForm" action="">
        <fieldset>
          <legend>댓글 등록</legend>

          <div>
              <input id="userid" ref="userid" type="text" placeholder="사용자 아이디">
          </div>

          <div>
              <input id="comment"  ref="comment" type="text" placeholder="댓글">
          </div>

          <button type="submit" id="cBtn" ref="cBtn" @click.prevent="cRegist">등록</button>
        </fieldset>
      </form>
</template>

<script>
import { reactive, ref } from '@vue/reactivity'
export default {
 name:'ToUserRegist',
  setup(){
        const state = reactive({
          
        })
    const commentForm = ref(null)
    const userid = ref(null)
    const comment = ref(null)
    const cBtn = ref(null)

    function cRegist(){
      if (userid.value.value=="") {
          alert('아이디를 입력하세요');
          userid.value.focus()
          return
      }
      if (comment.value.value=="") {
        alert('댓글을 입력하세요');
        return
      }

      commentForm.value.submit();

    }

      return{
        state, userid, comment, cBtn, commentForm, cRegist
      }
    
  } 

}
</script>

<style>
#comment-form {
  width: 40%;
  margin:0 auto;
}

#userid,
#comment,
#cBtn {
  margin :10px;
}
</style>