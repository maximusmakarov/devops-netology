# devops-netology
## И так начнём же курс по DevOps


Состояние Terraform описывает текущую развернутую инфраструктуру и хранится в файлах с расширением .tfstate. Файл состояния создается после развертывания инфраструктуры и может быть сразу загружен в Object Storage. Загруженный файл состояния будет обновляться после изменений созданной инфраструктуры.
Игнорируются все файлы *.tfstate , *.tfstate.*

Игнорируются все файлы журнала сбоев crash.log
Исключаются все файлы .tfvars, которые могут содержать отправляемые данные, такие как сереты: пароль, закрытые ключи и т.д. Они никоим образом не должны контрлироваться системой контроля версий, т.к. они являются данными, которые потенциально чувствительны и подвержены меняться в зависимости от окружения среды

Игнорируются файлы переопределения override.tf, override.tf.json, * _override.tf, * _override.tf.json т.к. они обычно используются для локального переопределения ресурсов.
Для включения файлов переопределения следут перед шаблоном сделать так:
! example_override.tf

Также можно включить файлы tfplan для игнорирования вывода плана команды: terraform plan -out = tfplan

Пример: * tfplan *


Игнорируются все файлы конфигурации CLI .terraformrc terraform.rc


