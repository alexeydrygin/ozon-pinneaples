# Софт для сбора ананасов с ozon.ru
v1.11: [Оповещения про обновления](https://t.me/+qY4o75AoHXkxYzY6)
---
# Изменения
- [2024-12-22 - v1.1]: Обновление версии приложения.
- [2024-12-01 - v1.1]: Изменения логики запуска потока.
- [2024-11-25 - v1.09]: Фикс ошибки "invalid literal for int() with base 10".
- [2024-11-13 - v1.08]: [BETA] Опция случайной генерации abt_data каждые 30 секунд.
---

### ✨ Функционал
- **Поддержка нескольких аккаунтов одновременно**: Одновременный сбор ананасов с нескольких аккаунтов.
- **Умная обработка ошибок**: Подробные сообщения об ошибках и действиях аккаунтов.
- **Настройки задержек**: Возможность установки задержки перед каждым сбором.

---

### ⚙️ Установка и использование

1. Получите ваши **Cookies**:
   - Перейдите на [ozon.ru](https://www.ozon.ru) и получите свои куки через F12.

2. Настройте `config.json`:
    ```json
    {
        "Accounts": [
            {
                "account_name": "Аккаунт 1",
                "x-o3-app-version": "17.48.0(2528)",
                "__Secure-access-token": "",
                "__Secure-refresh-token": "",
                "abt_data": "",,
                "generate_abt_data": true,
                "use_proxy": false,
                "proxy": ""
            }
        ],
        "Sleep_settings": {
            "sleep_between_pinneaples": true,
            "min_delay": 1,
            "max_delay": 1,
            "afk": true,
            "chance_to_afk": 1,
            "afk_time_min": 1,
            "afk_time_max": 1,
            "sleep_between_products": true,
            "min_time": 0.1,
            "max_time": 1.1
        },
        "Error_handling": {
            "sleep_if_403_status_code": true,
            "sleep_time_min": 1,
            "sleep_time_max": 3,
            "max_product_check_tries": 1
        }
    }
    ```
   - Accounts:
       - `account_name`: название аккаунта
       - `x-o3-app-version`: версия приложения (не советую менять)
       - `__Secure-refresh-token`, `__Secure-access-token`, `abt_data`: ваши куки, abt_data заполнять необязательно
       - `generate_abt_data`: генерация abt_data каждые 30 секунд (beta)
       - `use_proxy`: использование прокси (true/false)
       - `proxy`: прокси в формате `login:password@ip:port`, поддерживаются `HTTP` прокси
    
   - Sleep_settings:  
       - `sleep_between_pinneaples`: задержка после каждого сбора ананаса (true/false)
       - `min_delay`: минимальная задержка после каждого сбора (в секундах)
       - `max_delay`: максимальная задержка после каждого сбора (в секундах)
       - `afk`: опция для рандомного ухода аккаунта в спячку после сбора ананасов (true/false)
       - `chance_to_afk`: шанс для ухода в спячку (от 0 до 100)
       - `afk_time_min`: минимальное время спячки (в минутах)
       - `afk_time_max`: максимальное время спячки (в минутах)
       - `sleep_between_products`: задержка между проверкой продуктов на наличие ананаса (true/false)
       - `min_time`: минимальная задержка между проверкой продуктов (в секундах)
       - `max_time`: максимальная задержка между проверкой продуктов (в секундах)

   - Error_handling:
       - `sleep_if_403_status_code`: спячка в случае статус кода 403
       - `sleep_time_min`: минимальньое время спячки в случае статус кода 403 (в минутах)
       - `sleep_time_max`: максималньое время спячки в случае статус кода 403 (в минутах)
       - `max_product_check_tries`: максимальное количество повторений запроса на проверку продукта в случае статус кода 403


3. Установка зависимостей:
    ```bash
    pip install -r requirements.txt
    ```
   
4. Запуск (python 3.12+):
    ```bash
    py main.py
    ```

---

### 🔄 Использование нескольких аккаунтов

Если вы используете несколько аккаунтов, добавьте их в `config.json` в соответствующем формате:

```json
{
    "Accounts": [
        {
            "account_name": "Аккаунт 1",
            "x-o3-app-version": "17.48.0(2528)",
            "__Secure-access-token": "",
            "__Secure-refresh-token": "",
            "abt_data": "",,
            "generate_abt_data": true,
            "use_proxy": false,
            "proxy": ""
        },
        {
            "account_name": "Аккаунт 2",
            "x-o3-app-version": "17.48.0(2528)",
            "__Secure-access-token": "",
            "__Secure-refresh-token": "",
            "abt_data": "",,
            "generate_abt_data": true,
            "use_proxy": false,
            "proxy": ""
        },
        {
            "account_name": "Аккаунт 3",
            "x-o3-app-version": "17.48.0(2528)",
            "__Secure-access-token": "",
            "__Secure-refresh-token": "",
            "abt_data": "",,
            "generate_abt_data": true,
            "use_proxy": false,
            "proxy": ""
        }
    ]
}
```
### 📜 Лицензия
- Этот проект распространяется под MIT лицензией. Использование данного софта разрешается исключительно в образовательных целях. Все действия с использованием этого инструмента должны быть выполнены в рамках законодательства. Владелец не несет ответственности за использование данного софта.
- Telegram: [@churk_yyy](https://t.me/churk_yyy) (НЕ пишите с вопросами по скрипту).
