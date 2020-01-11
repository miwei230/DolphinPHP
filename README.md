#### ThinkAdmin图片裁切插
+ 使用方式：
    * 对于已有的写好的图片上传代码无需改什么，直接安装就好。
+ 原理：
    * cropper插件重写了ThinkAdmin的 `$.fn.uploadOneImage`图片上传函数，所以只要使用到该函数的时候都会变成裁切。
    * 在vender/mi8888插件中，已经定义了图片上传简洁代码：
    ```
        $element.find('[data-upload-image]').map(function () {
            var mode = $(this).data('upload-image') || 'one';
            if (mode === 'one') {
                $(this).uploadOneImage();
            } else {
                $(this).uploadMultipleImage();
            }
        });
    ```
    所以只需给input文本增加data-upload-image属性即可：` <input name="logo" data-upload-image type="hidden" value="{$vo.logo|default=''}">`就能实现上传裁切功能。
