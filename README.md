# Тест-кейсы для Tenjin


---


## 1. Основной позитивный кейс: Успешное получение данных аттрибуции (Android/iOS)

Тип теста: Ручной
Автор: vladimir shishkin

### Предусловия

1. Наличие эмулятора / устройства на Android/iOS

| # | Действие                                                                                                                                  | Ожидаемый результат                                                                                                                                                                   |
|---|-------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1 | Установить приложение по ссылке с рекламной компании, например: <br> https://yourapp.onelink.me/abcd?pid=adnetwork&c=campaign_123         | Приложение установлено                                                                                                                                                                |
| 2 | Запустить приложение                                                                                                                      | Приложение запущено                                                                                                                                                                   |
| 3 | Проверить логи OpenSearch.client      sss                                                                                                 | В логах лежит SendEventHelper.SendEventMessage::Event TenjinInfo was added to sending queue. <br>В TenjinInfo: tenjinCampaignName ≠ Organic, tenjinCampaignId ≠ null, tenjinId ≠ null |
| 4 | Записать идентификаторы TenjinId, TenjinCampaignId и TenjinCampaignName из TenjinInfo                                                     | Данные из TenjinInfo записаны                                                                                                                                                         |
| 5 | Проверить что в OpenSearch.technical появился лог с записанными ранее из TenjinInfo: <br> TenjinId, TenjinCampaignId и TenjinCampaignName | TenjinId, TenjinCampaignId и TenjinCampaignName в логах OpenSearch.technical соответствует записанным из OpenSearch.client                                                            