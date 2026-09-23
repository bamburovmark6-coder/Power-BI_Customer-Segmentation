# Customer Segmentation & Analytics Dashboard

Интерактивный дашборд для анализа клиентской базы, сегментации клиентов и оценки ключевых бизнес-метрик в Power BI.
  
## Содержание
- [Описание]
- [Возможности]
- [Ключевые метрики]
- [Визуализации]
- [Требования]
- [Использование]
- [Структура данных]
- [DAX формулы]
- 
Скриншоты и видео - Dashboard 1.pdf, Dashboard 2.pdf, Visualization.mp4

## Описание

Проект представляет собой комплексный аналитический дашборд для сегментации клиентов и анализа их поведения. Дашборд помогает бизнесу:
- Выявлять наиболее прибыльные сегменты клиентов
- Оценивать риск оттока (churn risk)
- Анализировать удовлетворенность клиентов (CSAT)
- Отслеживать ключевые финансовые показатели
- Принимать data-driven решения для повышения лояльности

## Возможности

## Интерактивная фильтрация
- **Демография**: возраст, пол, страна, город
- **Сегментация**: customer segment, loyalty tier, RFM категория
- **Поведение**: каналы продаж, устройства, категории товаров
- **Время**: dataset year

### Аналитические возможности
- RFM-анализ (Recency, Frequency, Monetary)
- Оценка пожизненной ценности клиента (CLV)
- Анализ стоимости привлечения (CAC)
- Прогнозирование оттока клиентов
- Оценка удовлетворенности (CSAT)
- Анализ эффективности маркетинговых каналов

## Ключевые метрики

## Финансовые показатели
|      Метрика      |                Описание                |
|-------------------|----------------------------------------|
| **Total Revenue** | Общая выручка от всех клиентов         |
| **Total Profit**  | Общая прибыль с учетом CAC             |
| **Avg CLV**       | Средняя пожизненная ценность клиента   |
| **Avg CAC**       | Средняя стоимость привлечения клиента  |
| **LTV:CAC Ratio** | Коэффициент окупаемости привлечения    |
| **AOV**           | Средний чек (Average Order Value)      |

### Метрики удержания
|        Метрика        |                 Описание                 |
|-----------------------|------------------------------------------|
| **High Churn Risk %** | Доля клиентов с высоким риском оттока    |
| **Avg CSAT**          | Средняя оценка удовлетворенности (0-5)   |
| **Avg Tenure**        | Средняя продолжительность взаимодействия |
| **Return Rate**       | Процент возвратов товаров                |

##  Визуализации

1. **KPI Cards** — ключевые показатели в виде карточек
2. **Gauge Chart (Датчик)** — визуализация CSAT относительно целевого значения
3. **Clustered Bar Chart** — выручка и прибыль по сегментам
4. **100% Stacked Bar Chart** — распределение риска оттока по каналам
5. **Tables** — детализация по:
   - Возрастным группам (age_group)
   - Сегментам клиентов (customer_segment)
   - Уровням лояльности (loyalty_tier)
   - Географии (country, city)
6. **Slicers** — интерактивные фильтры для динамического анализа

##  Требования

- **Power BI Desktop** (бесплатно)
  - Рекомендуемая версия: последняя стабильная

##  Использование
  Базовая навигация
1. Фильтрация данных: Используйте срезы (slicers) в верхней/боковой части дашборда
2. Детализация: Кликайте на элементы графиков для углубленного анализа
3. Сброс фильтров: Нажмите иконку ластика в правом верхнем углу среза

##  Сценарии использования
  Анализ прибыльных сегментов
1. Выберите интересующий customer_segment
2. Изучите KPI: Total Revenue, Total Profit, Avg CLV
3. Проверьте распределение по loyalty_tier

##  Выявление риска оттока
  Отфильтруйте по churn_risk_category = "High"
1. Проанализируйте характеристики этих клиентов:
2. Какие каналы они используют?
3. Какой у них days_since_last_purchase?
4. Какой satisfaction_score?

##  Оценка эффективности каналов
  Используйте срез shopping_channel
   Сравните метрики:
1. LTV:CAC Ratio по каналам
2. High Churn Risk % по каналам
3. Conversion Rate

##  Структура данных
  Основные таблицы
    Sheet1 (основная таблица клиентов)
    Демографические данные
1. customer_id — уникальный идентификатор
2. age, age_group — возраст и возрастная группа
3. gender — пол
4. country, city — география

##  Финансовые показатели
1. total_spent_usd — общая сумма покупок
2. total_purchases — количество покупок
3. avg_order_value_usd — средний чек
4. customer_lifetime_value_usd — LTV
5. customer_acquisition_cost_usd — CAC
6. customer_profitability_usd — прибыльность

##  Поведенческие метрики
1. tenure_months — срок взаимодействия (месяцы)
2. purchase_frequency — частота покупок
3. days_since_last_purchase — дней с последней покупки
4. recency_score, frequency_score, monetary_score — RFM компоненты
5. shopping_channel — предпочтительный канал
6. device_used — используемое устройство
7. payment_method — способ оплаты

##  Сегментация и оценка
1. customer_segment — сегмент клиента
2. segment_category — категория сегмента
3. loyalty_tier — уровень лояльности
4. rfm_score, rfm_category — RFM анализ
5. churn_risk_score, churn_risk_category — риск оттока
6. customer_health_score, health_status — здоровье клиента

##  Маркетинг и качество
1. email_open_rate — открываемость писем
2. click_through_rate — CTR
3. conversion_rate — конверсия
4. satisfaction_score, satisfaction_level — удовлетворенность
5. return_count — количество возвратов
6. complaint_count — количество жалоб

##  DAX формулы
// Общая выручка
Total Revenue = SUM(Sheet1[total_spent_usd])

// Общая прибыль
Total Profit = SUM(Sheet1[customer_profitability_usd])

// Средняя пожизненная ценность клиента
Avg CLV = AVERAGE(Sheet1[customer_lifetime_value_usd])

// Средняя стоимость привлечения
Avg CAC = AVERAGE(Sheet1[customer_acquisition_cost_usd])

// Коэффициент LTV к CAC
LTV:CAC Ratio = DIVIDE([Avg CLV], [Avg CAC], 0)

// Средний чек
AOV = DIVIDE(
    SUM(Sheet1[total_spent_usd]), 
    SUM(Sheet1[total_purchases]), 
    0
)

// Процент клиентов с высоким риском оттока
High Churn Risk % = 
DIVIDE(
    CALCULATE(
        COUNTROWS(Sheet1), 
        Sheet1[churn_risk_category] = "High"
    ), 
    COUNTROWS(Sheet1), 
    0
)

// Средняя удовлетворенность
Avg CSAT = AVERAGE(Sheet1[satisfaction_score])

// Общее количество клиентов
Total Customers = COUNTROWS(Sheet1)

// Доля клиентов в сегменте
Customer Share % = 
DIVIDE(
    [Total Customers],
    CALCULATE([Total Customers], ALL(Sheet1)),
    0
)


