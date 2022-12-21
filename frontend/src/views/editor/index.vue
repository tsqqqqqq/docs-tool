<template>
  <div id="editorComponent">
    <div id="editor" />
  </div>
</template>

<script setup>
import Vditor from 'vditor'
import "vditor/dist/index.css"
import {onMounted, ref} from "vue";

const vditor = ref(null)
onMounted(() => {
  vditor.value = new Vditor('editor', {
    height: '100%',
    width: '100%',
    lang: 'en_US',
    mode: 'wysiwyg',
    cache: {
      enable: false
    },
    after: () => {
      // eslint-disable-next-line no-undef
      vditor.value.setValue("dataValue")
    },
    toolbar: [
      {
        name: 'headings',
        tipPosition: 's'
      },
      {
        name: 'bold',
        tipPosition: 's'
      },
      {
        name: 'italic',
        tipPosition: 's'
      },
      {
        name: 'link',
        tipPosition: 's'
      },
      {
        name: '|',
        tipPosition: 's'
      },
      {
        name: 'list',
        tipPosition: 's'
      },
      {
        name: 'ordered-list',
        tipPosition: 's'
      },
      {
        name: 'check',
        tipPosition: 's'
      },
      {
        name: 'outdent',
        tipPosition: 's'
      },
      {
        name: 'dent',
        tipPosition: 's'
      },
      {
        name: '|',
        tipPosition: 's'
      },
      {
        name: 'quote',
        tipPosition: 's'
      },
      {
        name: 'code',
        tipPosition: 's'
      },
      {
        name: '|',
        tipPosition: 's'
      },
      {
        name: 'upload',
        tip: 'upload',
        tipPosition: 's'
      },
      {
        name: 'table',
        tipPosition: 's'
      },
      {
        name: '|',
        tipPosition: 's'
      },
      {
        name: 'undo',
        tipPosition: 's'
      },
      {
        name: 'redo',
        tipPosition: 's'
      },
      {
        name: 'line',
        tipPosition: 's'
      },
      {
        name: '|',
        tipPosition: 's'
      },
      {
        name: 'fullscreen',
        tipPosition: 's'
      },
      {
        name: 'edit-mode',
        tipPosition: 'e'
      }
    ]
//     upload: {
//       url: '/api/v1/attachment',
//       max: 1024 * 1024 * 1024,
//       linkToImgUrl: '/api/v1/attachment',
//       fieldName: 'files',
//       setHeaders() {
//         return {
//           // 'X-ACCESS-TOKEN': getAccessToken(),
//           // 'X-REFRESH-TOKEN': getRefreshToken(),
//           'X-USERID': getUserId()
//         }
//       },
//       extraData: {
//         'issue_id': self.issue_id,
//         'category': 'editor'
//       },
//       validate(files) {
//         // if (files[0].type.indexOf('image') === -1) {
//         //   return self.$tc('editor.uploadValidate')
//         // }
//         return true
//       },
//       async success(editor, msg) {
//         const data = JSON.parse(msg).data
//         let value = ''
//         for (let i = 0; i < data.length; i++) {
//           const env = process.env.VUE_APP_Backend_BASE_URL
//           // const env = 'http://192.168.0.100:3000/'
//           console.log()
//           if (self.equal(self.media, data[i]) !== undefined) {
//             // <video src="http://192.168.0.100:3000/attachment/c073f3b67c5611ed93b4fda9e36b6ca7/1671246882_test.mp4" controls="">test.mp4</video>
//             // self.contentEditor.renderPreview(env + data[i])
//             value = `<video src="${env}${data[i]}" controls="" />`
//           } else if (self.equal(self.images, data[i]) !== undefined) {
//             const image = env + data[i]
//             value = `![images](${image})\n`
//           } else {
//             value = `<center>
//     <img style="border-radius: 0.3125em;
//     box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);"
//     src="/image.png">
//     <br>
//     <div style="color:orange; border-bottom: 1px solid #d9d9d9;
//     display: inline-block;
//     color: #999;
//     padding: 2px;">${data[i]}</div>
// </center>`
//           }
//           self.contentEditor.insertValue(value)
//         }
//       },
//       error(msg) {
//         console.log(msg)
//       }
//     },
//     input(value) {
//       self.$emit('input', value)
//     }
  })
})
</script>

<style scoped>
#editorComponent {
  height: 100%;
  width: 85%;
}
</style>