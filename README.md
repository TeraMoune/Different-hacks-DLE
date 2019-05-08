# Different-hacks-DLE
#### Различные-хаки-DLE
---
Различные хаки которые не дотягивают до полноценных модулей.
Может кому-то пригодятся.

### Список
---
 1. [Added tags in categorymenu](https://github.com/TeraMoune/Different-hacks-DLE#added-tags-in-categorymenuxml)
 2. [Hr text for news](https://github.com/TeraMoune/Different-hacks-DLE#hr-text-for-newsxml)


#### Added-tags-in-categorymenu.xml
---
  - Шаблон применения: **categorymenu.tpl**
  
Добавляет аналогичный тегам `[isparent][/isparent]` теги `[ischildren][/ischildren]`.
Применяются между `[item][/item]` выводит текст для итема который является дочерним. (срабатывает только начиная с дочернего итема)
Тег `{sub-count}` применяется в как можно понять между мегами `[sub-prefix][/sub-prefix]` заменяется на порядковый номер дочерней категории.

#### Hr-text-for-news.xml
---
Хак добавляет `{hr-N}` тег при написании новостей, где N порядковый номер изображения. Заменяет на выходе span элементом подставляя картинку в качестве фона. Можно указать позицию изображения в %. 

Например `{hr-1 top="25"}`

Так же хак заменяет выборку для тега `{image-N}` выбирая изображения и из **full_story**, там где этого не было.

**CSS**
```CSS
.article-separation {
    width: 640px;
    height: 15px;
    display: block;
    margin: 0 auto;
    border-radius: 3px;
    box-shadow: 0px 0px 5px 1px #8e8e8e;
    background-position: 50% 50%;
    background-size: cover;
    border: 1px solid #101010;	
}

@media screen and (max-width:700px){
    .article-separation {
        width: 100%;
        height: 10px;	
    }
}
```
