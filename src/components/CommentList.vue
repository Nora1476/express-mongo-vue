<template>
    <table id="comment-list">
      <thead>
      <tr>
        <th>아이디</th>
        <th>작성자</th>
        <th>댓글</th>
        <th>수정</th>
        <th>삭제</th>
      </tr>
      </thead>
      <tbody></tbody>
    </table>
</template>

<script>
export default {
}
// 댓글 로딩
// async function getComment(id) {
//   try {
//     const res = await axios.get(`/users/${id}/comments`);
//     const comments = res.data;
//     const tbody = document.querySelector('#comment-list tbody');
//     tbody.innerHTML = '';
//     comments.map(function (comment) {
//       // 로우 셀 추가
//       const row = document.createElement('tr');
//       let td = document.createElement('td');
//       td.textContent = comment._id;
//       row.appendChild(td);
//       td = document.createElement('td');
//       td.textContent = comment.commenter.name;
//       row.appendChild(td);
//       td = document.createElement('td');
//       td.textContent = comment.comment;
//       row.appendChild(td);
//       const edit = document.createElement('button');
//       edit.textContent = '수정';
//       edit.addEventListener('click', async () => { // 수정 클릭 시
//         const newComment = prompt('바꿀 내용을 입력하세요');
//         if (!newComment) {
//           return alert('내용을 반드시 입력하셔야 합니다');
//         }
//         try {
//           await axios.patch(`/comments/${comment._id}`, { comment: newComment });
//           getComment(id);
//         } catch (err) {
//           console.error(err);
//         }
//       });
//       const remove = document.createElement('button');
//       remove.textContent = '삭제';
//       remove.addEventListener('click', async () => { // 삭제 클릭 시
//         try {
//           await axios.delete(`/comments/${comment._id}`);
//           getComment(id);
//         } catch (err) {
//           console.error(err);
//         }
//       });

</script>

<style>
#comment-list{
  margin :0 auto;
}

</style>