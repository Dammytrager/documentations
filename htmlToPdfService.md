#### HTML to PDF Service

___

METHOD - `POST`

Request Body

| Parameter       | description                                                  | required   | Type    |
| --------------- | ------------------------------------------------------------ | ---------- | ------- |
| s_id            |                                                              | `true`     | string  |
| html            | The full html content to be converted to pdf                 | `true`     | string  |
| format          | The format of the resulting conversion format should be `pdf` for pdf conversion | `true`     | string  |
| show_paging     | For resulting pdf of more than one page, this property determines if the paging e.g (`page 1 of 2`) should be shown at the bottom fo each page. Default value is `false` | `optional` | boolean |
| paging_template | This propety is applicable if the `show_paging` option is set to `true`. It sets the template of how the paging should be displayed. The template doesn't have to be a full html document rather it should be an html snippet. More details of this is explained in the section below. If the `paging_template` option is not set, the default template is used. | `optional` | string  |

##### paging_template examples

The paging shown at the bottom of each page has the current page and the total number of page. 

An html element with a class of  `page` will render the current page, while an html element with a class of  `to_page` will render the total number of pages.

For example, the snippet below will result in 

```html
<footer style="height: 50px; position: absolute; bottom: 0; left: 0; width: 100%;">
  <div style="float: left; padding-left: 60px;">
    <p>Monthly Statement</p>
  </div>
  <div style="float: right; padding-right: 60px">
    <p>Page <span class="page"></span> of <span class="topage"></span></p>
  </div>
</footer
```

![Screenshot 2021-11-02 at 10.51.18](/Users/damilare/Desktop/Screenshot 2021-11-02 at 10.51.18.png)



```ruby
File.open('/Users/miker/Desktop/out_rails.pdf', 'w') { |file| file.write(HtmlToImageService.convert(html: '<b>yay</b>', format: :pdf)) }
```