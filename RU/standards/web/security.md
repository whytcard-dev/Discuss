# Стандарты веб-безопасности 

## Основные принципы безопасности 

- Глубокая защита (несколько уровней безопасности) 
- Принцип наименьших привилегий 
- Безопасность по умолчанию и запроектированная 
- Регулярное тестирование и аудит безопасности 
- Поддержание зависимостей безопасности в актуальном состоянии 
- Безопасный отказ (безопасные значения по умолчанию) 
- Полное посредничество (проверка каждого запроса) 
- Обучение безопасности для всех членов команды 

## Аутентификация и авторизация 

### Аутентификация 

- Внедрение политик надежных паролей 
- Минимальная длина: 12 символов 
- Требование комбинации символов, цифр, символов 
- Проверка по общим спискам паролей 
- Поддержка многофакторной аутентификации (MFA) 
- Использование безопасного управления сеансами 
- Файлы cookie только для HTTP 
- Безопасный флаг для HTTPS 
- Атрибут SameSite 
- Соответствующее истечение срока действия 
- Реализация блокировки учетной записи после неудачных попыток 
- Безопасные потоки сброса пароля 
- Использование безопасного хранилища паролей (bcrypt/Argon2) 
- Рассмотрите варианты без пароля (WebAuthn, магические ссылки) 

### Авторизация 

- Внедрите управление доступом на основе ролей (RBAC) 
- Используйте управление доступом на основе атрибутов для сложных разрешений 
- Проверяйте авторизацию при каждом запросе 
- Внедряйте надлежащие проверки контроля доступа 
- Используйте безопасную обработку сеансов 
- Внедряйте авторизацию API (OAuth 2.0, JWT) 
- Избегайте прямых ссылок на объекты 
- Регистрируйте все сбои контроля доступа 

## Защита данных 

### Конфиденциальные данные 

- Идентифицируйте и классифицируйте конфиденциальные данные 
- Шифруйте конфиденциальные данные в состоянии покоя 
- Используйте TLS 1.3 для данных в пути 
- Внедряйте надлежащее управление ключами 
- Минимизируйте сбор конфиденциальных данных 
- Применяйте принципы минимизации данных 
- Внедряйте безопасное удаление данных 
- Используйте безопасное хранилище для ключей и секретов API 

### Проверка входных данных 

- Проверка всех входных данных на стороне сервера 
- Использование параметризованных запросов для доступа к базе данных 
- Реализация очистки входных данных 
- Проверка надлежащих типов данных, длины, формата 
- Использование разрешенных списков вместо запрещенных списков 
- Реализация кодирования выходных данных с учетом контекста 
- Проверка загрузок файлов (тип, размер, содержимое) 
- Реализация ограничения скорости для входных данных 

## Предотвращение распространенных уязвимостей 

### Предотвращение инъекций 

- Использование параметризованных запросов/подготовленных операторов 
- Применение ORM с надлежащим экранированием 
- Проверка и очистка всех входных данных 
- Реализация кодирования выходных данных с учетом контекста 
- Использование безопасных API, которые избегают инъекции интерпретатора 

### Предотвращение XSS 

- Реализация политики безопасности контента (CSP) 
- Использование автоматического кодирования выходных данных 
- Применение кодирования с учетом контекста 
- Очистка входных данных HTML 
- Использование современных фреймворков со встроенной защитой от XSS 
- Проверка URL-адресов в перенаправлениях 
- Применить флаг HTTPOnly к конфиденциальным файлам cookie 

### Предотвращение CSRF 

- Внедрить анти-CSRF токены 
- Использовать атрибут cookie SameSite 
- Проверить заголовки origin и referrer 
- Требовать повторной аутентификации для конфиденциальных действий 
- Использовать правильную конфигурацию CORS 

### Заголовки безопасности 

- Content-Security-Policy (CSP) 
- X-Content-Type-Options: nosniff 
- Strict-Transport-Security (HSTS) 
- X-Frame-Options 
- Referrer-Policy 
- Permissions-Policy 
- Заголовки Cache-Control для конфиденциальных данных 
- Clear-Site-Data для выхода из системы 

## Безопасность инфраструктуры 

### Безопасность сервера 

- Поддерживать актуальность программного обеспечения сервера 
- Использовать безопасные конфигурации сервера 
- Внедрить правильные правила брандмауэра 
- Включить Только HTTPS (перенаправление HTTP на HTTPS) 
- Настройте правильные параметры TLS 
- Отключите ненужные службы 
- Используйте модули веб-сервера, ориентированные на безопасность 
- Реализуйте ограничение скорости и защиту от DDoS 

### Безопасность API 

- Используйте HTTPS для всех конечных точек API 
- Реализуйте правильную аутентификацию 
- Применяйте ограничение скорости 
- Проверяйте полезные данные запросов 
- Возвращайте соответствующие коды состояния 
- Избегайте раскрытия конфиденциальной информации в ответах 
- Используйте ключи API для связи между службами 
- Документируйте требования безопасности для потребителей API 

### Управление зависимостями 

- Регулярно сканируйте уязвимые зависимости 
- Используйте файлы блокировки для закрепления версий зависимостей 
- Реализуйте автоматическое сканирование уязвимостей 
- Быстро обновляйте зависимости 
- Минимизируйте использование зависимостей 
- Проверяйте целостность зависимостей (контрольные суммы) 
- Отслеживайте атаки на цепочку поставок 
- Имейте план реагирования на уязвимости 

## Тестирование безопасности 

### Статический Анализ 

- Внедрение автоматизированных инструментов SAST 
- Интеграция проверки безопасности в CI/CD 
- Сканирование на наличие жестко закодированных секретов 
- Анализ кода на наличие антишаблонов безопасности 
- Проверка конфигураций безопасности 
- Проверка на наличие устаревших зависимостей 
- Внедрение стандартов безопасного кодирования 

### Динамическое тестирование 

- Регулярное тестирование на проникновение 
- Внедрение автоматизированного сканирования DAST 
- Использование интерактивного тестирования безопасности приложений 
- Регулярное проведение оценок уязвимостей 
- Тестирование потоков аутентификации и авторизации 
- Проверка заголовков и конфигураций безопасности 
- Моделирование распространенных сценариев атак 

## Мониторинг безопасности и реагирование 

### Ведение журнала и мониторинг 

- Внедрение комплексного журнала безопасности 
- Регистрация событий аутентификации 
- Регистрация сбоев контроля доступа 
- Мониторинг подозрительной активности 
- Внедрение оповещений в режиме реального времени 
- Использование централизованного управления журналами 
- Обеспечение устойчивости журналов к несанкционированному доступу 
- Сохранение журналов в течение соответствующего времени периоды 

### Реагирование на инциденты 

- Разработка плана реагирования на инциденты 
- Определение ролей и обязанностей 
- Установление протоколов связи 
- Документирование процедур сдерживания 
- Внедрение возможностей судебного анализа 
- Проведение обзоров после инцидента 
- Практика сценариев реагирования на инциденты 
- Поддержание связи с сообществом безопасности 

## Соответствие и конфиденциальность 

### Соответствие нормативным требованиям 

- Определение применимых нормативных актов (GDPR, CCPA и т. д.) 
- Внедрение требуемых средств контроля безопасности 
- Регулярное проведение оценок соответствия 
- Документирование мер соответствия 
- Обучение команды требованиям соответствия 
- Внедрение конфиденциальности по умолчанию 
- Ведение требуемой документации 

### Соображения конфиденциальности 

- Внедрение четких политик конфиденциальности 
- Получение надлежащего согласия на сбор данных 
- Предоставление доступа к данным и механизмов удаления 
- Минимизация сбора и хранения данных 
- Внедрение переносимости данных 
- Проведение оценок влияния на конфиденциальность 
- Учет конфиденциальности во всех проектных решениях 