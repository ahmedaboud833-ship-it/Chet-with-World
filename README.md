# Chat with World - تطبيق دردشة عالمي لنظام Android

تطبيق مراسلة فورية حقيقي عالي الأداء مبني بالكامل باستخدام **Kotlin** و **Jetpack Compose (Material 3)** ومدعوم بـ **Supabase** (المصادقة برقم الهاتف، قاعدة بيانات PostgreSQL، التحديثات اللحظية عبر Realtime WebSockets، ومستودع الوسائط Storage).

---

## 📱 المميزات الرئيسية
- 🔐 **تسجيل الدخول برقم الهاتف عبر OTP**: إرسال وتحقق حقيقي لرموز SMS عبر Supabase Auth وتنسيق E.164 الدولي.
- 💬 **محادثات فورية لحظية (Realtime)**: إرسال واستقبال الرسائل في أجزاء من الثانية بالاعتماد على WebSockets مع الحفظ الدائم في PostgreSQL.
- 👥 **المحادثات الخاصة والمجموعات**: إنشاء مجموعات، إضافة أعضاء، وتحديد المشرفين.
- 📷 **الوسائط والملفات والرسائل الصوتية**: إرسال الصور والمستندات والرسائل الصوتية عبر Supabase Storage.
- ⭕ **نظام الحالات (Stories)**: نشر الحالات النصية والوسائط التي تنتهي صلاحيتها بعد 24 ساعة.
- 🛡️ **حماية كاملة بـ Row Level Security (RLS)**: منع غير الأعضاء من الوصول للرسائل أو انتحال الهوية.
- 🎨 **تصميم احترافي وداعم للعربية بالكامل (RTL)** والوضع الداكن والفاتح.
- ⚙️ **إعدادات الخصوصية والملف الشخصي**: تعديل الاسم، الصورة، النبذة، والتحكم في إيصالات القراءة وحظر المستخدمين.

---

## 🏗️ هيكلية المشروع (Project Architecture)
```
com.example/
├── core/                  # إعدادات Supabase، إدارة الجلسات، الشبكة والـ WebSocket
├── data/
│   ├── models/            # نماذج البيانات (Profile, Conversation, Message, Status, etc.)
│   ├── remote/            # استدعاءات Supabase REST & WebSocket API
│   └── repository/        # مستودع البيانات وإدارة التدفقات (Flows)
├── ui/
│   ├── theme/             # ألوان وهوية Chat with World، الخطوط والمظهر
│   └── screens/           # شاشات التطبيق:
│       ├── SplashScreen
│       ├── WelcomeScreen
│       ├── PhoneLoginScreen
│       ├── OtpVerificationScreen
│       ├── ProfileSetupScreen
│       ├── HomeScreen
│       ├── ChatScreen
│       ├── NewChatScreen
│       ├── CreateGroupScreen
│       ├── StatusScreen
│       ├── SettingsScreen
│       └── ProfileScreen
└── viewmodel/             # ViewModels لإدارة حالات الشاشات (MVVM)
```

---

## 🚀 طريقة البناء والتشغيل
1. استورد المشروع داخل **Android Studio**.
2. اتبع الخطوات في `SETUP_SUPABASE.md` لإعداد مشروع Supabase وتطبيق ملفات SQL.
3. أضف `SUPABASE_URL` و `SUPABASE_ANON_KEY` في ملف `.env` أو Secrets.
4. اضغط على **Run** لتشغيل التطبيق على الهاتف أو المحاكي.
