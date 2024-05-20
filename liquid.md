### 变量

使用双大括号{{ }}包围变量名即可输出变量的值:{{variable_name}}

### 过滤器
用于对变量的值进行处理。它们放置在变量之后，并用管道符号 | 分隔:
{{ variable_name | filter_name }} <br>
常见的过滤器有：<br>
capitalize：将字符串的首字母大写。
downcase：将字符串转换为小写。<br>
upcase：将字符串转换为大写。<br>
replace：替换字符串中的子字符串。
truncate：截断字符串到指定长度。

### 标签
标签使用 {% %} 包围 <br>
{% if condition %}
  <!-- 条件为真时执行 -->
{% elsif another_condition %}
  <!-- 另一个条件为真时执行 -->
{% else %}
  <!-- 所有条件都不成立时执行 -->
{% endif %}

{% for item in collection %}
  <!-- 对集合中的每一项执行操作 -->
  {{ item }}
{% endfor %}

assign：分配变量

### 对象
对象是 Liquid 模板中的核心元素，通常由点号 . 进行属性访问
site：站点相关信息。
page：当前页面的信息。
content：当前内容。
{{ product.title }}
{{ article.author.name }}

### 注释
单行注释：{# This is a comment #}
多行注释：{% comment %}
  This is a 
  multi-line comment.
{% endcomment %}

site.people  Jekyll中，数据集合是一种组织和管理数据的方式，类似于数据库表。
通常在 Jekyll 配置文件 _config.yml 中定义集合，例如 people。这些集合可以包含多个数据项，每个数据项可以是一个独立的 Markdown 或 YAML 文件，存储在 _people 文件夹中。



