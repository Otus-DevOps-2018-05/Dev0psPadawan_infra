# Dev0psPadawan_infra
Dev0psPadawan Infra repository
	 

	**Homework-04**


bastion_IP = 35.205.64.104 
someinternalhost_IP = 10.132.0.3


	**Homework-05** 

 
gcloud compute instances create reddit-app\
  --boot-disk-size=10GB \
  --image-family ubuntu-1604-lts \
  --image-project=ubuntu-os-cloud \
  --machine-type=g1-small \
  --tags puma-server \
  --restart-on-failure \
  --zone europe-west1-d \
  --metadata-from-file startup-script=./startup_script.sh

testapp_IP = 35.205.36.8
testapp_port = 9292

gcloud compute firewall-rules create default-puma-server \
>  --network default \
>  --direction INGRESS \
>  --allow tcp:9292 \
>  --target-tags


	**Homework-06**

Created all tasks. Resalts has been saved in /packer dirrectory.

	**Homework-07**

Основное задание:
1. Определил input переменную для приватного ключа,
использующегося в определении подключения для
провижинеров (connection);
2. Определил input переменную для задания зоны в ресурсе
"google_compute_instance" "app";
3. Отформатировал все конфигурационные файлы используя
команду terraform fmt;
4. Создал файл terraform.tfvars.example, в котором
указал переменные для образца.

Задание *:
1. Использовал ресурс google_compute_project_metadata_item 
для добавления ключа пользователя(ей) appuser1 (и appuser2)
 в метаданные проекта.
2. Добавил ssh ключ пользователю appuser_web через
веб интерфейс. После выполниния terraform apply
ключ был удалён терраформом, т.к. его не было прописано
в main.tf

