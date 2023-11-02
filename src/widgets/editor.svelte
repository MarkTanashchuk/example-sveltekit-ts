<script lang="ts">
  import { onMount } from 'svelte';

  onMount(() => {
    let configs = {
      // emoticons: {
      //     emoticons_append: {
      //         custom_mind_explode: {
      //             keywords: ['brain', 'mind', 'explode', 'blown'],
      //             char: '🤯'
      //         }
      //     }
      // }
      autosave: {
        autosave_ask_before_unload: false,
        autosave_restore_when_empty: true,
        autosave_interval: '20s',
        autoresize_overflow_padding: 50
      },
      image: {
        // image_prepend_url: 'https://url/to/admin/panel/images',
        image_list: [
          {
            title: 'Cat',
            value: 'cat.png'
          },
          {
            title: 'Dogs',
            menu: [
              {
                title: 'Alaskan Husky',
                value: 'husky.jpg'
              },
              {
                title: 'Dingo',
                value: 'dingo.png'
              }
            ]
          }
        ],
        image_class_list: [
          {
            title: 'None',
            value: ''
          },
          {
            title: 'Borders',
            menu: [
              {
                title: 'Green border',
                value: 'img_green_border'
              }
            ]
          }
        ],
        image_advtab: true,
        image_title: true
        // style_formats: [
        // 	{title: 'Image Left', selector: 'img', styles: {
        // 		'float' : 'left',
        // 		'margin': '0 10px 0 10px'
        // 	}},
        // 	{title: 'Image Right', selector: 'img', styles: {
        // 		'float' : 'right',
        // 		'margin': '0 10px 0 10px'
        // 	}}
        // ]
      },
      codesample: {
        codesample_global_prismjs: true,
        codesample_languages: [{ text: 'HTML/XML', value: 'markup' }]
      },
      charmap: {
        charmap_append: [
          [0x2600, 'sun'],
          [0x2601, 'cloud']
        ]
      },
      date: {
        insertdatetime_element: true
      },
      nbsp: {
        nonbreaking_force_tab: true
      },
      fontSize: {
        // fontsize_formats: "8pt 10pt 12pt 14pt 16pt 18pt 21pt 24pt 30pt 36pt 45pt 57pt"
      }
    };

    let styleFormat = [
      {
        title: 'Headers',
        items: [
          { title: 'Header 1', format: 'h1' },
          { title: 'Header 2', format: 'h2' },
          { title: 'Header 3', format: 'h3' },
          { title: 'Header 4', format: 'h4' },
          { title: 'Header 5', format: 'h5' },
          { title: 'Header 6', format: 'h6' }
        ]
      },
      {
        title: 'Blocks',
        items: [
          { title: 'Paragraph', format: 'p' },
          { title: 'Blockquote', format: 'blockquote' },
          { title: 'Div', format: 'div' },
          { title: 'Pre', format: 'pre' }
        ]
      }
    ];

    tinymce.init(
      Object.assign(...Object.values(configs), {
        selector: '#mytextarea',
        maxWidth: '45vh',
        skin: 'oxide-dark',
        content_css: 'dark',
        statusbar: false,
        style_formats: styleFormat,
        plugins:
          'table lists advlist nonbreaking directionality visualchars charmap emoticons insertdatetime autosave autolink autoresize wordcount code codesample quickbars preview searchreplace image media',
        toolbar: [
          '| undo redo | bold italic underline strikethrough blockquote | removeformat | superscript subscript |',
          '| insertdatetime charmap emoticons | code codesample | searchreplace wordcount preview restoredraft',
          '| styleselect | fontselect | fontsizeselect |',
          '| image imagetools quickimage | bullist numlist | table | forecolor backcolor  |',
          '| alignnone alignleft aligncenter alignright alignjustify | outdent indent | ltr rtl visualchars nonbreaking |'
        ],
        toolbar_mode: 'floating'
      })
    );
  });
</script>

<div id="modal">
  <div id="mytextarea">
    <p style=" font-size: 18pt;text-align: center;">Some text about new events there</p>
    <div
      style="
      width: 100%;
      padding: 24px 0;

      background-color: rgb(182, 165, 85);

      color: rgb(0, 0, 0);

      font-size: 24pt;
      text-align: center;
"
    >
      Event text!
    </div>
  </div>
</div>

<style>
  #modal {
    position: absolute;
    z-index: 9998;

    display: flex;

    align-items: center;
    justify-content: center;

    width: 100%;
    height: 100%;
  }

  :global(.tox) {
    z-index: 9999 !important;
  }
</style>
