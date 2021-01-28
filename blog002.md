# HTML 入门笔记 2：常用重要标签

![hello](./hello.png)

1. 超链接标签`<a></a>`<br>

    - href 属性：规定指向超链接的目标，href 可以指向的链接类型：
        1. 外部链接："https://google.com"
        2. 内部链接："index.html"（自己写的页面）
        3. 锚点链接：快速定位到页面的某个位置（这个功能用 js 做的更好）
        4. 伪协议：javascript:;实现 a 标签但不刷新不跳转、mailto:邮箱;发送邮件、tel:手机号;打电话。

    * targe 属性：规定超链接的打开方式，比如新建页面打开，常用取值:
        1. \_self：在本页面打开
        2. \_blank：在新建页面打开
        3. \_top：在顶级页面打开
        4. \_parsent：在当前页面的上一层打开

2. 表格标签`<table></table>`<br>

    - 内部的标签有表头`<thead></thead>`、表身`<tbody></tbody>`、表脚`<tfoot></tfoot>`，以办写法如下：

    ```html
    <table>
    	<thead>
    		<tr>
    			<th>标题1</th>
    			<th>标题2</th>
    		</tr>
    	</thead>
    	<tbody>
    		<tr>
    			<td>内容a</td>
    			<td>内容c</td>
    		</tr>
    		<tr>
    			<td>内容b</td>
    			<td>内容d</td>
    		</tr>
    	</tbody>
    </table>
    ```

    - 效果如下：
      <table>
      <thead>
      <tr>
      <th>标题 1</th>
      <th>标题 2</th>
      </tr>
      </thead>
      <tbody>
      <tr>
      <td>内容 a</td>
      <td>内容 c</td>
      </tr>
      <tr>
      <td>内容 b</td>
      <td>内容 d</td>
      </tr>
      </tbody>
      </table>

    * 常用 css 修饰：
        1. table_layout:fixed;表格等宽
        2. border-collapse:collapse;表格合并
        3. border-spacing:0px;间隔 0 像素

3. 图片标签`<img />`（发出 get 请求，展示一张图片）<br>

    - src 属性：图片地址
    - alt 属性：显示失败时显示 alt 内容
    - height 和 weight 属性：长宽属性，只写其中一个时，另一个会自适应
    - js 重要事件：onload 加载成功调用，onerror 加载失败调用
    - css 修饰：max-width:100%;实现自适应手机界面

4. 表单标签`<form></form>`(发出 get 或 post 请求，然后刷新页面)<br>

    - action 属性：路径
    - method 属性：get、post。默认发 get 请求
    - autocomplete 属性：on 表示启用浏览器自动记录之前输入值（如：用户名表单一般会显示以往输入过的用户名），off 表示不启用（如：密码表单以办不会显示输入过的密码）。
    - ！！！form 内嵌套的 input 标签最好要有 name 属性。

5. 输入框标签：`<input />`
    - type 属性：指定输入框类型，如 radio 表示单选、hidden 表示隐藏（这种是留给机器操作的）
    - 重要事件：onchange、onfocus 和 onblur：监听事件（注：一般不监听 input 事件）

个人感悟：很多 html 标签的视觉效果很刻板，多配合 css，js 使用才能贴切实现用户需求。

![end](./end.png)
