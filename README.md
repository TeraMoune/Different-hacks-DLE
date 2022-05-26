# Different-hacks-DLE
#### Различные-хаки-DLE
---
Различные хаки которые не дотягивают до полноценных модулей.
Может кому-то пригодятся.

### Установка
Скачайте архив затем установите нужный плагин из папки plugins.

### Список
---
 1.  [Added tags in categorymenu](https://github.com/TeraMoune/Different-hacks-DLE#added-tags-in-categorymenuxml)
 2.  [Hr text for news](https://github.com/TeraMoune/Different-hacks-DLE#hr-text-for-newsxml)
 3.  [Edit date comments](https://github.com/TeraMoune/Different-hacks-DLE#edit-date-commentsxml)
 4.  [Auto width column image](https://github.com/TeraMoune/Different-hacks-DLE#auto-width-columnxml)
 5.  [Fast edit extension](https://github.com/TeraMoune/Different-hacks-DLE#fast-edit-extensionxml)
 6.  [Recover password](https://github.com/TeraMoune/Different-hacks-DLE#recover-passwordxml)
 7.  [Added foto tag in email templates](https://github.com/TeraMoune/Different-hacks-DLE#added-foto-tag-in-email-templatesxml)
 8.  [Tags count in category](https://github.com/TeraMoune/Different-hacks-DLE#tag-count-news-in-categoryxml)
 9.  [Check exists tags](https://github.com/TeraMoune/Different-hacks-DLE#check-exists-tagsxml)
 10. [Comments functions](https://github.com/TeraMoune/Different-hacks-DLE#comments-functionsxml)
 11. [Aviable date](https://github.com/TeraMoune/Different-hacks-DLE#aviable-datexml)
 12. [Specialization from the category](https://github.com/TeraMoune/Different-hacks-DLE#specialization-from-the-categoryxml)
 13. [Validity period publications for groups](https://github.com/TeraMoune/Different-hacks-DLE#Validity-period-publications-for-groupsxml)
 14. [Approve files in xfields](https://github.com/TeraMoune/Different-hacks-DLE#approve-files-in-xfieldsxml)
 15. [Mod search plugins](https://github.com/TeraMoune/Different-hacks-DLE#mod-search-pluginsxml)
 16. [Explode xfields](https://github.com/TeraMoune/Different-hacks-DLE#explode-xfieldsxml)
 17. [Search users null news](https://github.com/TeraMoune/Different-hacks-DLE#search-users-null-newsxml)
 18. [Remove view category in catmenu](https://github.com/TeraMoune/Different-hacks-DLE#remove-view-category-in-catmenuxml)
 19. [Add xfields in search users admin](https://github.com/TeraMoune/Different-hacks-DLE#add-xfields-in-search-users-adminxml)
 20. [Checkbox userxfields](https://github.com/TeraMoune/Different-hacks-DLE#checkbox-userxfieldsxml)
 21. [Info-tags in attachment](https://github.com/TeraMoune/Different-hacks-DLE#info-tags-in-attachmentxml)
 22. [Auto-upload image](https://github.com/TeraMoune/Different-hacks-DLE#auto-upload-imagexml)
 23. [Ifxf aviable](https://github.com/TeraMoune/Different-hacks-DLE#ifxf-aviablexml)
 24. [Pagination_range](https://github.com/TeraMoune/Different-hacks-DLE#pagination_rangexml)
 25. [Disable category sitemap](https://github.com/TeraMoune/Different-hacks-DLE#disable-category-sitemapxml)
 26. [From and to in custom.xml](https://github.com/TeraMoune/Different-hacks-DLE#from-and-to-in-customxml)
 27. [Global tags](https://github.com/TeraMoune/Different-hacks-DLE#global-tagsxml)


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

#### Edit-date-comments.xml
---
Добавляет поле изменения даты комментарию для администратора.
CSS оформление взять в файле `engine/skins/stylesheets/application.css` перенести стили `.xdsoft_datetimepicker` к себе в шаблон к стилям.

#### Auto-width-column.xml
---
При загрузке картинок под выбором выравнивания будет два параметра, колонки и ширины. Установив в колонке число и выбрав все или часть картинок то им будет задан параметр `width` таким образом, чтобы уместилось в одну линию указанное число картинок. А ширина задаёт одинаковую ширину вставляемым изображениям.

#### Fast-edit-extension.xml
---
Дополнительные поля в быстром редактировании новости которых нету. Изменение категории, тегов, даты, мета данных и ЧПУ ссылки.

В файле `dle_js.js` 
найти
```JavaScript
params[value.name] = value.value;
```
заменить на
```Javascript
if( params[value.name] ) params[value.name] = params[value.name] + ',' + value.value;
else params[value.name] = value.value;
```

#### recover-password.xml
---
Изменение восстановления пароля, вместо двух писем будет отправлять лишь одно с ссылками. Перейдя по ссылке пользователь увидит сгенерированный пароль в info окошке. В настройках email шаблонов можно настроить шаблон который будет использован в info окошке (можно использовать html разметку)

#### added-foto-tag-in-email-templates.xml
---
Добавляет {%foto%} тег в шаблон отправки уведомления личного сообщения.

#### tag-count-news-in-category.xml
---
Добавляет [count-news=cat_id]{c-news}[/count-news] теги в шаблон. Выводит количество новостей независимо от categorymenu.tpl.
Обязательно включить подсчёт количества новостей. Так же в течении текущего и прошедшего дня будет писать время последнего обновления категории (Учёт только добавленных новостей)

#### check-exists-tags.xml
---
  - Шаблон применения: **fullstory.tpl**, **shortstory.tpl** и кастомные шаблоны.
  
[exists-tags="tagname1,tagname2,tagname3"] text [/exists-tags] 

Выводит заключённый между блоками содержимое если указанный 'tagname' тег существует в новости. Можно указывать несколько тегов через запятую.

#### comments-functions.xml
---
Добавляет в форму добавления комментария пару элементов. Возможность выставления рейтинга новости при добавлении комментария или выбрать комментарий оффтопом. Добавленный комментарий с выбранным рейтингом можно выделить среди других, так же как и оффтоп. В самом комментарии можно вывести выбранную оценку.

Возможность выставления рейтинга имеется только пока пользователь не установился оценку новости, как только он это сделает то элеметы в форме добавления комментария будут недоступны. Рейтинг можно изменить отредактировав комментарий или вовсе удалить.

Используемые теги в шаблоне **comments.tpl**

 - [crating]{crating}[/crating] - При выставленном рейтинге принимает значение установленного рейтинга для новости.
 - {crating_class} и {offtop_class} - Классы для выделения комментариев.

#### aviable-date.xml
---
  - Шаблон применения: **fullstory.tpl**, **shortstory.tpl**.
  
[aviable_date="01.09.2019|yesterday|tomorrow"] text [/aviable_date] 

Выводит заключённый между блоками содержимое если указанная дата ровна дате публикации новости. Можно указать tomorrow или yesterday (Завтра и Вчера) tomorrow выведет текст если новость опубликована днём ранее, а yesterday обратный параметр и выведет если новость опубликуют завтра.

#### specialization-from-the-category.xml
---
  - Шаблон применения: **userinfo.tpl**.
 
{specialization}        - Просто текcт категории.

{specialization-link}   - В качестве ссылки на категорию.

{specialization-select} - Селект выборки категории в настройках профиля.

Даёт возможность использовать категории сайта в качестве выборки определённых для конкретного пользователя и вывести выбранные в профиле.

#### Validity-period-publications-for-groups.xml
---
Добавляет группам функцию 'Срок действия публикации' с рядом действий по наступлению даты. Можно выбрать автоматическое применение определённого действия при добавлении новостей участником группы. В случае если новость предварительно находится на одобрении то правило применяется в момент изменения статуса новости.

В настройках группы в разделе новости две настройки, одна указывается в днях сколько должно пройти с момента публикации. В другой действие которое должно произойти.

#### approve-files-in-xfields.xml
---
Добавляет checkbox для файлов загруженных в доп. поле. Переключатель approve параметра который так же определяет возможность скачивания файла с сервера.

В шаблоне **attachment.tpl** доступны доп. теги.
`[file-not-approve]<span class="attachment">Файл еще не проверен</span>[/file-not-approve]`

#### mod-search-plugins.xml
---
Добавляет поле поиска в раздел плагинов для удобства поиска плагина или редактируемого файла.

#### enter-rand-url-news.xml
---
Небольшой и очень простой плагин установив который на сайте появиться новый адрес **/?do=rand_url**, перейдя на который пользователя перенаправит на рандомно полученную новость.

#### explode-xfields.xml
---
  - Шаблон применения: **fullstory.tpl**, **shortstory.tpl**, и кастомные шаблоны.
  
Добавляет тег [xfvalue_name_N explode="X"]. Выведет конкретное значение по счёту где N число если строка имеет разделитель переданный X.
Например: name1,name2 (вывести name1 при помощи [xfvalue_name_1 explode=","])

#### search-users-null-news.xml
---
В раздел всех пользователей в админке под выборкой новостей добавит опцию при котором будет искать людей без добавленых новостей.

#### add-xfields-in-search-users-admin.xml
---
В разделе всех пользователей в админке добавил select выборку по доп. полям среди однострочных и поле ниже для значения этого поля.

#### remove-view-category-in-catmenu.xml
---
В редактировании и при создании категории будет опция при включении которой категория не будет видна в общем меню категорий выводимой тегом **{catmenu}**

#### checkbox-userxfields.xml
---
Добавляет дополнительное поле типа 'Переключатель'

#### info-tags-in-attachment.xml
---
  - Шаблон применения: **attachment.tpl**.

Добавляет дополнительное теги в шаблон которые создаются при вставке тега аттачмента с параметром `info="..."` в котором можно прописать дополнительные теги и их значения `tags:value||tags2:value2`. После в шаблоне можно будет использовать теги `[info_tags]{info_value}[/info_tags]`.

Например:
[attachment=N:file info="quality:HDRip||translate:Дублированный|iTunes"]

В шаблоне **attachment.tpl** доступно применение тегов:
  - [info_quality]Качество: {info_quality}[/info_quality]
  - [info_translate]Перевод: {info_translate}[/info_translate]

#### auto-upload-image.xml
---
Пытается загрузить любое внешнее изображение в описании с изменением url и созданием миниатюры согласно настройкам.

`P.S. Важно помнить чем больше изображений тем дольше время ожидания после нажатия кнопки отправить, слишком большое количество картинок может привести к превышении времени ожидания и тогда картинки будут загружены не все и новость вероятно тоже не будет опубликована, а часть картинок которая уже успела будет пылится на сервере.
Так, что применять осторожно.`

#### ifxf-aviable.xml
---
  - Шаблон применения: **main.tpl** и подключенные при помощи `{include file="name.tpl"}`.
  
Добавляет теги `[ifxf-aviable xfname="xf_name1,xf_name2" xf="xf_value1,xf_value2"] text [/ifxf-aviable]` которые работают как другие aviable и предназначен для отображения или сокрытия содержимого в тегах на страницах поиска новостей по перекрёстным ссылкам доп. полей.
Два параметра xfname и xf, первый имя поля, второй значение. Можно совмещать или использовать по отдельности. Так же можно добавить знак (!) перед (=) дабы изменить правила поиска и сделать условие всё кроме указанных значений.

#### pagination_range.xml
---
Позволяет повлиять на пагинацию в настройках в разделе **Новости** будут две настройки с префиксом [Pagination]. Одна указывает через какое количество выставлять многоточие. Вторая указывает количество кнопок по бокам от текущей.

#### disable-category-sitemap.xml
---
  - Шаблон применения: **categorymenu.tpl**.
  
В настройках категории добавляет параметр при включении которого категория будет исключена из карты сайта. А в шаблоне категорий добавляется тег **{disable-sitemap}** который выставит такой категории `rel="nofollow"`.

#### from-and-to-in-custom.xml
---
Добавляет два параметра на выборку числового диапазона, между min и max поля. 
`polename_from="X" polename_to="X"`

#### Global-tags.xml
Глобальные теги определённых данных.
`{g-year}, {g-title}, {g-link-site}, {g-description-site}, {g-short-title}, {g-sys-email}, {g-user-email}, {g-user-id}, {g-user-news}, {g-user-comments}, {g-user-group_id}, {g-user-group_name}, {g-user-login}, {g-user-lastdate}`

!Если какие-то плагины нуждаются в доработке дайте знать.

### Контакты
Email: teramoune@gmail.com

Telegram: TeraMoune

### На печеньки...
> ЮMoney: 4100115063692304
> 
> Qiwi nickname: TERAMOUNE
> 
> Wmz: Z990082286464
