# Route

路由，其实就是指向的意思，当点击页面上的home按钮时，页面中就要显示home的内容，
如果点击页面上的about 按钮，页面中就要显示about 的内容。Home按钮  => home 内容，
about按钮 => about 内容，也可以说是一种映射. 所以在页面上有两个部分，一个是点击部分，
一个是点击之后，显示内容的部分。

客户端中的路由，实际上就是dom 元素的显示和隐藏。当页面中显示home 内容的时候，about 中的内容全部隐藏，反之也是一样。
客户端路由有两种实现方式：基于hash 和基于html5 history api.

**本项目swad-webUI 因为是基于Vue框架，所以用到路由组件 Vue-router**

