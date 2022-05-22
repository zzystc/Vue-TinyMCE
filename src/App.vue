<template>
  <div >
    <textarea id="mytextarea"></textarea>
  </div>
</template>

<script>

export default {
  name: 'App',
  mounted() {
    tinymce.init({
      selector: '#mytextarea',
      language: 'zh_CN',
      branding: false,
      toolbar: [
        'undo redo | styleselect | bold italic | link image',
        'alignleft aligncenter alignright hr'
      ],
      menu: {
        file: {title: 'File', items: 'newdocument'},
        edit: {title: 'Edit', items: 'undo redo | cut copy paste pastetext | selectall'},
        insert: {title: 'Insert', items: 'link media | template hr'},
        view: {title: 'View', items: 'visualaid'},
        format: {title: 'Format', items: 'bold italic underline strikethrough superscript subscript | formats | removeformat'},
        table: {title: 'Table', items: 'inserttable tableprops deletetable | cell row column'},
        tools: {title: 'Tools', items: 'spellchecker code'},
        plugins: "hr",
        setup: function(editor) {
          editor.on('click', function(e) {
            console.log('Editor was clicked');
          });
        },
        init_instance_callback : function(editor) {
          console.log("Editor: " + editor.id + " is now initialized.");
          }
        }
    });
  },
}
</script>
