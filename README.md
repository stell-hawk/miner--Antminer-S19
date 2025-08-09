# miner--Antminer-S19

про работу с API VNISH:
часть API доступна без ключей доступа.
например общая информация можно открыть в браузере http://{IP}/api/v1/summary
и увидеть много полезного.
часть же методов доступна только с авторизацией.
для этого идем в раздел Система-безопасность- API ключи -создаем ключ. (32 любых символа- надо ввести самостоятельно)
список методов доступен тут http://{IP}/docs/
например чтобы выключить майнинг надо компьютере находящемся в той же сети что и асик выполнить команду
curl -v -X POST --header "x-api-key:{API_KEY}" --header "accept:application/json" http://{IP}/api/v1/mining/stop
чтобы включить:
curl -v -X POST --header "x-api-key:{API_KEY}" --header "accept:application/json" http://{IP}/api/v1/mining/start
сменить профиль  на 1500:
curl -v -X POST --header "x-api-key:{API_KEY}"  --header "accept:application/json" --header "Content-Type: application/json" --data "{\"miner\":{\"overclock\":{\"preset\":\"1500\"}}}" http://{IP}/api/v1/settings
запуск по расписанию можно сделать например через планировщик задач.или если это Linux через cron. 
утилита curl имеется и в винде и на линукс.
PS: {IP} -надо изменить на IP асика
{API_KEY} -заменить на созданный ключ.
