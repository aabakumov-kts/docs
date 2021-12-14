# Как создать первую форму

Начните знакомство с сервисом с создания простой формы:

1. [Добавьте на форму вопросы, на которые будут отвечать пользователи](#create-form).

1. [Опубликуйте форму и попросите пользователей ее заполнить](#publish).

1. [Получите таблицу с ответами пользователей](#get-answers).

## Шаг 1. Создайте форму {#create-form}

1. {% include [forms-versions](../_includes/forms/forms-versions.md) %}

1. На верхней панели нажмите кнопку **Создать форму**.

1. Из списка слева выберите блоки и расположите их на форме в следующем порядке:
    
    № | Блоки | Настройки
    ----- | ----- | -----
    1 | ![](../_assets/forms/text-block.png) | Введите текст:<br/>`Пожалуйста, заполните эту пробную форму.`<br/>Добавьте комментарий:<br/>` Звездочкой отмечены обязательные поля.`
    2 | ![](../_assets/forms/short-text-block.png) | Введите вопрос:<br/>` Фамилия:`<br/>Включите опцию **Обязательный вопрос**.
    3 | ![](../_assets/forms/single-option-block.png) | Введите вопрос:<br/>`Пол:`<br/>Добавьте ответы:<ul><li>`мужской`<li>`женский`<ul/>
    4 | ![](../_assets/forms/drop-down-list-block.png) | Введите вопрос:<br/>`Семейное положение:`<br/>Добавьте ответы:<ul><li>`холост`<li>`женат/замужем`<ul/>
    5 | ![](../_assets/forms/short-text-block.png) | Введите вопрос:<br/>`Девичья фамилия:`
    
1. Настройте условия появления вопроса <q>Девичья фамилия</q>:

    1. Наведите указатель на блок <q>Девичья фамилия</q> и нажмите появившийся значок ![](../_assets/forms/conditions.png).

    1. Добавьте два условия и заполните поля, как показано на рисунке:
        
        ![](../_assets/forms/block-conditions-settings.png)

    Теперь этот вопрос появится в форме только при условии, что в предыдущих вопросах выбран женский пол и семейное положение — <q>женат/замужем</q>.


## Шаг 2. Опубликуйте форму {#publish}

Чтобы пользователи могли заполнять форму, ее нужно опубликовать:

1. Нажмите кнопку **Поделиться**.

1. Чтобы скопировать ссылку на форму, в поле **Ссылка** нажмите значок ![](../_assets/forms/icon-copy.png).

1. Вставьте ссылку в адресную строку браузера и перейдите по ней. Если вы все сделали правильно, откроется новая форма:
    
    ![](../_assets/forms/form-example.png)

1. Отправьте ссылку на форму пользователям.


## Шаг 3. Получите ответы на вопросы {#get-answers}

Чтобы получить таблицу с ответами пользователей на вопросы формы:

1. Перейдите на вкладку **Ответы**.

1. В списке **Скачать ответы на вопросы** включите опцию **Все**.

1. В списке **В формате** выберите опцию **XLSX**.

1. В списке **Фильтр по дате ответа** выберите опцию **За все время**.

1. Нажмите кнопку **Скачать**.