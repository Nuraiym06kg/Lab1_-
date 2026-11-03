# Архитектурный проект: Веб-приложение с аналитическим ML-сервисом

Учебный проект, реализующий многоуровневую архитектуру клиент-серверного приложения с интеграцией аналитического сервиса на Python для предиктивной аналитики, RFM-анализа и кластеризации клиентской базы.

---

## 🏗 Архитектура системы

Система разделена на 5 логических уровней (согласно схеме в `draw.io`):

1. **Клиентский уровень (Frontend):** 
   * **Стек:** Next.js, React, TypeScript, Tailwind CSS.
   * **Назначение:** Интерфейсы для пользователей, менеджеров и администраторов с дашбордами и графиками (React Hooks, Zustand, Recharts).
2. **Серверный уровень (Backend):** 
   * **Стек:** NestJS, TypeScript, REST API (JSON).
   * **Назначение:** Обработка бизнес-логики (Sales, Events, Tracking, Customers, Analytics), аутентификация и разграничение прав доступа (JWT + Guards + RBAC).
3. **Уровень данных (Database):** 
   * **Стек:** PostgreSQL / ClickHouse.
   * **Назначение:** Хранение сущностей (Users, Products, Orders, OrderItems, Events, Segments) через Prisma ORM.
4. **Аналитический / ML-сервис:** 
   * **Стек:** Python, FastAPI, scikit-learn, pandas, NumPy.
   * **Назначение:** Расчет RFM-метрик, кластеризация пользователей, прогнозирование оттока и анализ трендов продаж.
5. **Экспорт и отчеты:** 
   * **Стек:** S3-совместимое хранилище / CSV / Excel.
   * **Назначение:** Сохранение сгенерированных отчетов и выгрузок.

---

## 🔄 Схема взаимодействия (Data Flow)
[Пользователь]
│ (Действия пользователя)
▼
[Next.js + React]
│ (HTTP / HTTPS REST API · JSON)
▼
[NestJS Backend] ──(Проверка доступа)──► [JWT + RBAC]
│
├──(Вызов бизнес-логики)──► [Sales / Events / Tracking]
│
├──(SQL через ORM)───────► [PostgreSQL / ClickHouse]
│
└──(Запрос аналитики)────► [FastAPI Python ML-сервис]
│
├──► [scikit-learn / pandas / NumPy]
│
▼
[Метрики и сегменты]
---

## 🚀 Быстрый старт

### Требования
* Node.js (v18+)
* Python (v3.10+)
* PostgreSQL / ClickHouse

### Установка и запуск

1. **Клонирование репозитория:**
   ```bash
   git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
   cd your-repo-name
   cd server
npm install
npm run start:dev
cd client
npm install
npm run dev
cd ml-service
pip install -r requirements.txt
uvicorn main:app --reload
Ниже представлены готовые материалы для вашей лабораторной работы: **README.md** для репозитория GitHub и структурированный **Шаблон отчета** по ГОСТу/стандартам учебных заведений.

---

# README.md

```markdown
# Архитектурный проект: Веб-приложение с аналитическим ML-сервисом

Учебный проект, реализующий многоуровневую архитектуру клиент-серверного приложения с интеграцией аналитического сервиса на Python для предиктивной аналитики, RFM-анализа и кластеризации клиентской базы.

---

## 🏗 Архитектура системы

Система разделена на 5 логических уровней (согласно схеме в `draw.io`):

1. **Клиентский уровень (Frontend):** 
   * **Стек:** Next.js, React, TypeScript, Tailwind CSS.
   * **Назначение:** Интерфейсы для пользователей, менеджеров и администраторов с дашбордами и графиками (React Hooks, Zustand, Recharts).
2. **Серверный уровень (Backend):** 
   * **Стек:** NestJS, TypeScript, REST API (JSON).
   * **Назначение:** Обработка бизнес-логики (Sales, Events, Tracking, Customers, Analytics), аутентификация и разграничение прав доступа (JWT + Guards + RBAC).
3. **Уровень данных (Database):** 
   * **Стек:** PostgreSQL / ClickHouse.
   * **Назначение:** Хранение сущностей (Users, Products, Orders, OrderItems, Events, Segments) через Prisma ORM.
4. **Аналитический / ML-сервис:** 
   * **Стек:** Python, FastAPI, scikit-learn, pandas, NumPy.
   * **Назначение:** Расчет RFM-метрик, кластеризация пользователей, прогнозирование оттока и анализ трендов продаж.
5. **Экспорт и отчеты:** 
   * **Стек:** S3-совместимое хранилище / CSV / Excel.
   * **Назначение:** Сохранение сгенерированных отчетов и выгрузок.

---

## 🔄 Схема взаимодействия (Data Flow)


```

[Пользователь]
│ (Действия пользователя)
▼
[Next.js + React]
│ (HTTP / HTTPS REST API · JSON)
▼
[NestJS Backend] ──(Проверка доступа)──► [JWT + RBAC]
│
├──(Вызов бизнес-логики)──► [Sales / Events / Tracking]
│
├──(SQL через ORM)───────► [PostgreSQL / ClickHouse]
│
└──(Запрос аналитики)────► [FastAPI Python ML-сервис]
│
├──► [scikit-learn / pandas / NumPy]
│
▼
[Метрики и сегменты]

```

---

## 🚀 Быстрый старт

### Требования
* Node.js (v18+)
* Python (v3.10+)
* PostgreSQL / ClickHouse

### Установка и запуск

1. **Клонирование репозитория:**
   ```bash
   git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
   cd your-repo-name

```

2. **Запуск серверной части (NestJS):**
```bash
cd server
npm install
npm run start:dev

```


3. **Запуск клиентской части (Next.js):**
```bash
cd client
npm install
npm run dev

```


4. **Запуск ML-сервиса (FastAPI):**
```bash
cd ml-service
pip install -r requirements.txt
uvicorn main:app --reload

```



```

---

