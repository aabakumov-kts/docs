# Управление заданиями Hive

В кластере {{ dataproc-name }} можно управлять [заданиями (jobs)](../concepts/jobs.md), а также получать логи их выполнения. Примеры заданий см. в разделе [{#T}](../solutions/job-overview.md).


## Создать задание {#create}

{% list tabs %}

* Консоль управления

    1. Перейдите на страницу каталога и выберите сервис **{{ dataproc-name }}**.
    1. Нажмите на имя нужного кластера и выберите вкладку **Задания**.
    1. Нажмите кнопку **Создать задание**.
    1. (Опционально) Укажите имя задания.
    1. В поле **Тип задания** выберите `Hive`.
    1. Укажите свойства задания.

       {% include [Особенности указания аргументов, свойств и настроек](../../_includes/data-proc/job-properties-requirements.md) %}

    1. (Опционально) Включите настройку **Продолжать при ошибке**.
    1. Укажите переменные скрипта.
    1. (Опционально) Укажите пути к JAR-файлам, если они используются:

        {% include [Допустимые пути к файлам](../../_includes/data-proc/jar-file-path-requirements.md) %}

    1. Выберите один из типов драйвера и укажите, что использовать для запуска задания:
        * список запросов, которые необходимо выполнить;
        * путь к файлу с запросами, которые нужно выполнить.
    1. Нажмите кнопку **Создать задание**.

* CLI

    {% include [cli-install](../../_includes/cli-install.md) %}

    {% include [default-catalogue](../../_includes/default-catalogue.md) %}

    Чтобы создать задание:

    1. Посмотрите описание команды CLI для создания заданий типа `Hive`:

        ```bash
        yc dataproc job create-hive --help
        ```

    1. Создайте задание (в примере приведены не все доступные параметры):

        ```bash
        yc dataproc job create-hive \
           --cluster-name <имя кластера> \
           --name <имя задания> \
           --query-file-uri <URI файла запроса> \
           --script-variables <список значений переменных, разделенных запятыми>
        ```

        Пути к необходимым для выполнения задания файлам передавайте в формате:

        {% include [Допустимые пути к файлам](../../_includes/data-proc/jar-file-path-requirements.md) %}

    Идентификатор и имя кластера можно получить со [списком кластеров в каталоге](./cluster-list.md#list).

* API

    Воспользуйтесь методом API [create](../api-ref/Job/create) и передайте в запросе:

    * Идентификатор кластера в параметре `clusterId`. Его можно получить со [списком кластеров в каталоге](./cluster-list.md#list).
    * Имя задания в параметре `name`.
    * Свойства задания в параметре `hiveJob`.

{% endlist %}

## Получить список заданий {#list}

{% list tabs %}

* Консоль управления

    1. Перейдите на страницу каталога и выберите сервис **{{ dataproc-name }}**.
    1. Нажмите на имя нужного кластера и выберите вкладку **Задания**.

* CLI

    {% include [cli-install](../../_includes/cli-install.md) %}

    {% include [default-catalogue](../../_includes/default-catalogue.md) %}

    Чтобы получить список заданий, выполните команду:

    ```bash
    yc dataproc job list --cluster-name <имя кластера>
    ```

    Идентификатор и имя кластера можно получить со [списком кластеров в каталоге](./cluster-list.md#list).

* API

    Воспользуйтесь методом API [list](../api-ref/Job/list) и передайте идентификатор кластера в параметре `clusterId` запроса.

    Идентификатор кластера можно получить со [списком кластеров в каталоге](./cluster-list.md#list).

{% endlist %}


## Получить общую информацию о задании {#get-info}

{% list tabs %}

* Консоль управления

    1. Перейдите на страницу каталога и выберите сервис **{{ dataproc-name }}**.
    1. Нажмите на имя нужного кластера и выберите вкладку **Задания**.
    1. Нажмите на имя нужного задания.

* CLI

    {% include [cli-install](../../_includes/cli-install.md) %}

    {% include [default-catalogue](../../_includes/default-catalogue.md) %}

    Для получения общей информации о задании выполните команду:

    ```bash
    yc dataproc job get \
       --cluster-name <имя кластера> \
       --name <имя задания>
    ```

    Идентификатор и имя кластера можно получить со [списком кластеров в каталоге](./cluster-list.md#list).

* API

    Воспользуйтесь методом API [get](../api-ref/Job/get) и передайте в запросе:

    * Идентификатор кластера в параметре `clusterId`. Его можно получить со [списком кластеров в каталоге](./cluster-list.md#list)
    * Идентификатор задания в параметре `jobId`. Его можно получить со [списком заданий в кластере](#list).

{% endlist %}


## Получить логи выполнения задания {#get-logs}

{% list tabs %}

* Консоль управления

    1. Перейдите на страницу каталога и выберите сервис **{{ dataproc-name }}**.
    1. Нажмите на имя нужного кластера и выберите вкладку **Задания**.
    1. Нажмите на имя нужного задания.

* CLI

    {% include [cli-install](../../_includes/cli-install.md) %}

    {% include [default-catalogue](../../_includes/default-catalogue.md) %}

    Чтобы получить логи выполнения задания, выполните команду:

    ```bash
    yc dataproc job log \
       --cluster-name <имя кластера> \
       --name <имя задания>
    ```

    Идентификатор и имя кластера можно получить со [списком кластеров в каталоге](./cluster-list.md#list).

* API

    Воспользуйтесь методом API [listLog](../api-ref/Job/listLog) и передайте в запросе:

    * Идентификатор кластера в параметре `clusterId`. Его можно получить со [списком кластеров в каталоге](./cluster-list.md#list).
    * Идентификатор задания в параметре `jobId`. Его можно получить со [списком заданий в кластере](#list).

{% endlist %}