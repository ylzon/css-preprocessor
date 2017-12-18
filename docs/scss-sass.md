# SCSS和Sass的区别

## 扩展名
* Sass文件名后缀为.sass
* SCSS文件后缀名为.scss

## 整体写法
* Sass属于缩进式写法，能简则简
* 省略分号、花括号
```scss
$variable: #666666
section.s1 div
  height: 50px
  background-color: $variable
```

* Scss属于兼容常规CSS的写法，相对符合W3C规范
* 保留省略引号、分号、花括号
* 对空格不敏感
```scss
$variable: #666666;
section.s1 div{
  height: 50px;
  background-color: $variable;
}
  
// 对空格不敏感，也可以写成
$variable: #666666;
section.s1 div { height: 50px;background-color: $variable; }
```

## 注释

* Sass注释
```scss
// 1. 单行注释，标准编译和压缩编译后不会保留

/* 2. 多行注释
    标准编译后会保留注释
    压缩编译后不会保留

/*!3. 强制保留注释
    标准编译后会保留注释
    即使压缩也会保留，使用与版权声明
```

* SCSS注释
```scss
// 1. 单行注释，标准编译和压缩编译后不会保留

/* 2. 多行注释
* 标准编译后会保留注释
* 压缩编译后不会保留 */

/*!
* 3. 强制保留注释
* 标准编译后会保留注释
* 即使压缩也会保留，使用与版权声明
*/
```

## @import
* Sass引入文件无需加引号
```scss
@import ../common/scss/base
```
* Scss则需要加引号
```scss
@import "../common/scss/base";
```

## @mixin
* Sass
```scss
=block($bg_color) {
  height: 50px;
  background-color: lighten($bg_color, 30%);
}
section.s5{
  div {
    +block(red);
  }
}
```
* SCSS
```scss
@mixin block($bg_color) {
  height: 50px;
  background-color: lighten($bg_color, 30%);
}
section.s5{
  div {
    @include block(red);
  }
}
```

## 总结
通过上述对比，Sass的两种语法Sass和SCSS后者更偏向于前端开发的主流，前者已经很少人在用，故推荐SCSS作为CSS预编译的开发工具。