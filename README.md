# Софт для сбора ананасов с ozon.ru
v1.05: [Оповещения про обновления](https://t.me/+qY4o75AoHXkxYzY6)
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
                "x-o3-app-version": "17.40.1(2518)",
                "__Secure-access-token": "",
                "__Secure-refresh-token": "",
                "abt_data": "",
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
            "afk_time_max": 1
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
       - `use_proxy`: использование прокси (true/false)
       - `proxy`: прокси в формате `login:password@ip:port`
    
   - Sleep_settings:  
       - `sleep_between_pinneaples`: задержка после каждого сбора ананаса (true/false)
       - `min_delay`: минимальная задержка после каждого сбора (в секундах)
       - `max_delay`: максимальная задержка после каждого сбора (в секундах)
       - `afk`: опция для рандомного ухода аккаунта в спячку после сбора ананасов
       - `chance_to_afk`: шанс для ухода в спячку (от 0 до 100)
       - `afk_time_min`: минимальное время спячки (в минутах)
       - `afk_time_max`: максимальное время спячки (в минутах)

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
            "x-o3-app-version": "17.40.1(2518)",
            "__Secure-access-token": "",
            "__Secure-refresh-token": "",
            "abt_data": "",
            "use_proxy": false,
            "proxy": ""
        },
        {
            "account_name": "Аккаунт 2",
            "x-o3-app-version": "17.40.1(2518)",
            "__Secure-access-token": "",
            "__Secure-refresh-token": "",
            "abt_data": "",
            "use_proxy": false,
            "proxy": ""
        },
        {
            "account_name": "Аккаунт 3",
            "x-o3-app-version": "17.40.1(2518)",
            "__Secure-access-token": "",
            "__Secure-refresh-token": "",
            "abt_data": "",
            "use_proxy": false,
            "proxy": ""
        }
    ]
}
```
### 📜 Лицензия
- Этот проект распространяется под MIT лицензией. Использование данного софта разрешается исключительно в образовательных целях. Все действия с использованием этого инструмента должны быть выполнены в рамках законодательства. Владелец не несет ответственности за использование данного софта.
- Telegram: [@churk_yyy](https://t.me/churk_yyy) (НЕ пишите с вопросами по скрипту).
