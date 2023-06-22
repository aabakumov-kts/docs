# Уменьшение объема диска виртуальной машины

## Описание задачи {#case-description}
Возникла необходимость уменьшить объем ранее созданного диска, снимка или образа ВМ Compute Cloud.

## Решение {#case-resolution}

Изменение размера диска возможно только в большую сторону — это архитектурная особенность технологий, используемых Yandex Cloud. Подробнее об этом пишем в соответствующем [материале документации](../../../compute/operations/disk-control/update.md#change-disk-size).

Если возникла необходимость уменьшить объем загрузочного диска виртуальной машины, целевую ВМ понадобится создать заново, указав требуемый размер диска. 

Для этого вы можете создать снимок диска вашей виртуальной машины и создать новый диск из этого снимка, указав новый размер. 

{% note alert %}

Следует учитывать, что создать из снимка диск меньшего размера, чем родительский диск, не получится.

{% endnote %}

Если же возникла необходимость уменьшить объем дополнительных дисков виртуальной машины, которые не являются загрузочными, вы можете создать пустой диск требуемого размера и, не пересоздавая ВМ, перенести данные со старого диска на новый, удалив старый диск по завершении переноса данных.

Также вы можете воспользоваться сервисом Object Storage для хранения данных. Бакет можно монтировать в качестве каталога [с помощью FUSE и GeeseFS](../../../storage/tools/geesefs.md)