# سند - نظام إدارة أداء اللاعبين

نظام متكامل لتتبع وتحليل أداء لاعبي كرة القدم، يوفر رؤى تحليلية متعمقة وتنبؤات بمخاطر الإصابات.

## المميزات

- **لوحة التحكم**: عرض إحصائيات الفريق والأداء العام
- **تحليل اللاعبين**: متابعة تفصيلية لأداء كل لاعب
- **تحليل المباريات**: تسجيل وتحليل إحصائيات المباريات
- **تحليل المخاطر**: تنبؤ بمخاطر الإصابات بناءً على مؤشرات الأداء
- **التدريبات**: تخطيط وتتبع جلسات التدريب

## متطلبات التشغيل
- Python 3.8 أو أحدث
- pip (مدير حزم Python)

## خطوات التثبيت

1. قم بإنشاء بيئة Python افتراضية وتفعيلها:
```bash
python -m venv venv
# Windows
venv\Scripts\activate
# Linux/Mac
source venv/bin/activate
```

2. قم بتثبيت المتطلبات:
```bash
pip install -r requirements.txt
```

3. قم بإنشاء ملف `.env` في المجلد الرئيسي وأضف المتغيرات التالية:
```
DATABASE_URL=sqlite:///./sannad.db
JWT_SECRET=your-secret-key
```

## تشغيل التطبيق

1. قم بتشغيل الخادم:
```bash
python -m uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

2. افتح المتصفح على العنوان:
```
http://localhost:8000
```

## هيكل المشروع

```
Sannad/
├── app.py              # نقطة دخول التطبيق
├── requirements.txt    # متطلبات المشروع
├── init_data.py       # تهيئة مجلد البيانات
├── data/              # مجلد البيانات
│   └── players_data.csv
├── routes/            # مسارات التطبيق
│   └── analysis.py
├── services/          # خدمات معالجة البيانات
│   └── data_analysis.py
├── utils/             # أدوات مساعدة
│   └── data_utils.py
└── templates/         # قوالب الصفحات
    ├── base.html
    ├── dashboard.html
    ├── players.html
    ├── matches.html
    ├── training.html
    └── analysis.html
```

## واجهات البرمجة (API)

### تحليل الفريق
- `GET /api/analysis/team`: إحصائيات الفريق واتجاهات الأداء

### تحليل اللاعبين
- `GET /api/analysis/player/<player_name>`: إحصائيات وأداء لاعب محدد
- `GET /api/analysis/players`: قائمة جميع اللاعبين مع إحصائياتهم

### تحليل المخاطر
- `GET /api/analysis/risks`: تحليل مخاطر الإصابات لجميع اللاعبين

## المساهمة

نرحب بمساهماتكم! يرجى اتباع الخطوات التالية:

1. Fork المشروع
2. إنشاء فرع للميزة الجديدة
3. تقديم طلب Pull Request

