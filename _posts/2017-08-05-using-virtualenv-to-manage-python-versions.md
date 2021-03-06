---
layout: post
title: "virtualenv لإدارة إصدارات البايثون"
date: 2017-08-05 19:38:41 +0100
image: 'http://i.imgur.com/ciwlCWa.png'
description: "تنصيب و إعداد virtualvenv لإدارة إصدارات البايثون على جهازك, و تطوير برمجياتك بكل سهولة"
tags:
- python
- virtualenv
- virtual environments
categories:
- Python
twitter_text:
---


غالبا ما ستظطر إلى تنصيب إصدارات عدة من لغة برمجة واحدة, ربما لأن بعض الحزم تعتمد إلى إصدارات حديثة و العكس وارد, و ربما برنامج يحتاج إلى مكتبة في إصدارتها الأولى, و آخر يحتاج الإصدارة الثانية, لكن تنصيب إصدارات عدة على نظام تشغيل واحد, و هو أمر غير منصوح به لأنه سيصعب عليك لاحقا إدارة كل تلك الإصدارات, في حين البرامج أو سكريبتاتك أو مجرد تنفيد أوامر من موجه الأوامر __Teminal__ سيكون عليك توجيها إلى المفسر الصحيح, و لن يكون الأمر نفسه على جهاز اخر, في أنت لا تريد الدخول في هذه المتاهة, و بالطبع المجتمع عانى من هذه الصعوبة أيضا في إدارة الإصدارات, و ليس في البايثون فقط, بل أغلب اللغات "التفسيرية", لذلك كان الحل هو إنشاء بيئات وهمية Virtual environments.
 
## ماذا نعني بالبيئات الوهمية Virtual environments ؟
 
 الأمر ببساطة و كما يدل الإسم هو إنشاء بيئة وهمية لا تستخدم المفسر الأساسي/الإفتراضي الخاص بنظام تشغيل, و تشغيل أي إصدار من مفسر البايثون و أيضا الحزم أو المكتبات بدون أن تمس تلك الخاصة بالنظام أو البرامج أو أي مكون, و كل هذا سيكون في متناول يدك, كل ما عليك تفعيل البيئة و من ثم طور عليها برنامجك/تطبيقك بالمتطلبات التي تحتاجها, و لا حقا يمكنك عمل `Freeze` للمتطلبات ليسهل حمله !
 
## ماذا تحتاج لإنشاء بيئة وهمية لتطوير برنامجك ؟
 
 بالطبع هناك العديد من المكتبات أو الإضافات التي سأذكرها, لكن لن يسعنا الوقت لشرحها في هذه التدوينة, سنشرح التعامل مع واحدة و سأترك لك حرية التعرف على الأخريات, إن كنت مهتما, بالطبع يمكنك قراءة الثوثيق الرسمي, و ستصبح على دراية بكيفية التعامل مع كل واحدة, يجدر الذكر أن هناك مكتبات قياسية, أي يتم تضمينها مع مكتبات الأساسية الخاصة بالمفسر و أخرى هي حزم تطور من طرف أشخاص أو مجتمعات..

### 1 - [venv][1]

يعتبر Venv مكتبة قياسية منذ الإصدارة الثالثة من البايثون و يمكنك إستعماله بالأمر `python3 -m venv` لكن تجدر الإشارة إلى أن بعض التوزيعات جعلت من المكتبة حزمة منفردة مثلا دبيان/أوبونتو يمكنك إستعمال الأمر التالي `python3-venv`, ما يميز venv أنك لن تحتاج لنسخ مفسرات البايثون في كل مكان تريد عمل بيئة وهمية __بإستثناء وندوز__, ربما قد تجده مناسبا لك خصوصا أنه تحت إشراف مؤسسة البايثون بعد أن تم [تجاوز مكتبة __pyvenv__ في الإصدار 3.6][2].

### 2 - [virtualenv][3]

بالطبع الأمر ليس حكرا على المكتبات القياسية, هناك أدوات أخرى و لعل بعضها أخد شعبية واسعة ضمن المجتمع, و على رأس القائمة  __virtualvenv__, طبعا أداة قوية و إن لم تكن قد تعاملت معها, فقد حان الوقت لأنه ما من مبرمج بايثون يجب أن يغفلها, و هو ما سنتعامل معه في باقي التدوينة.

### 3 - [pyenv][4]

كنت سأنهي اللائحة هنا, لكن يجب أن أذكر __pyenv__ لانها تفرعت من[rbvenv][5] و هي أداة تعاملت معها سابقا لإدارة إصدارات __Ruby__ تسمى  ما يميز هذه الأداة أنه يمكنك التعامل مع إصدارات عدة من البايثون, بالطبع هذا مفيد أن أردت أن تجرب برنامجك على إصدارات متعددة مثلا 2.6, 2.7, 3.3, 3.4, 3.5 أو 3.6 يمكنك زيارة الموقع للتعرف على كيفية تعاملك مع المفسرات, ربما قد تجد الأمر مشوقا !

## ثتبيت virtualenv

طبعا بعد ذكرنا بعض الأدوات على سبيل المثال لا الحصر, و يمكنك أن تراجع صفحات البحث حول __Python virtual environments__ لتتعرف على مكتبات و أدوات أخرى, بالنسبة لنا سنتعامل مع __virtualenv__.

 الحزمة متواجدة على __PyPI__ و بالتالي يمكنك بسهولة تنصيبها, بالطبع يجب أن يكون مفسر البايثون و __pip__ متبثين على نظامك مسبقا, إن كان نظامك مبني/مشابه للــUNIX, فغالبا البايثون متبث إفتراضيا, يمكنك التأكد بواسطة الأمر:
 
``` bash
    python --version
```


مخرج هذا الأمر يجب أن يكون كالتالي:


``` bash
    Python 2.7.13
```

لا يهم رقم الإصدار, لأن هذا ما نحاول أن نتجاوزه, إن لم يتم التعرف على الأمر فالأرجح أنك تحتاج إلى [ثتبيت البايثون][6], الان تأكد من أن __pip__ متبث و بإصدار 1.3 أو أعلى بالأمر التالي:

``` bash
    pip --version
```


مخرج الأمر سيكون تقريبا كالتالي:


``` bash
pip 9.0.1 from /usr/lib/python2.7/site-packages (python 2.7)
```

في حالة كان إصدار __pip__ أقل من 1.3 و هو أمر مستبعد يمكنك أن أن تحديثه إلى اخر نسخة:

``` bash

pip install --upgrade pip

```

إن كنت من مستعملي الوندوز, جرب الأمر التالي:

``` bash

python -m pip install --upgrade pip

```

الآن يمكنك تتبيث __virtualenv__ ببساطة:

``` bash

[sudo] pip install virtualenv

```

لسبب ما لا تتوفر على pip أو صلاحياتك محدودة, يمكنك تجربة طرق [أخرى لتتبيث/إستعمال virtualenv ][7].

## إنشاء بيئتك الوهمية

الآن بإفتراض أن كل الخطوات السابقة كانت ناجحة, سننتقل إلى إنشاء بيئة وهمية:

``` bash

virtualenv my_first_env

```

طبعا مع مراعاة أن `my_first_env` هو المجلد الذي تود إنشاء البيئة عليه, ستخبرك الأداة أن تم إنشاء الملفات التنفيدية داخل المجلد __bin__ الموجود بدوره داخل مجلد البيئة, و ثتبيت بعد الأدوات من ضمنها __pip__, الآن بيئتك جاهزة للتطوير, __من داخل مجلد البيئة__ نفذ الأمر التالي لتفعيل البيئة الوهمية:

``` bash

source bin/activate

```

بعدها مباشرة سيظهر لك على موجه الأوامر كالتالي:

``` bash

(my_first_env) [yassine@localhost my_first_env]$ 

```
لاحظ أن السطر يبتدأ بــ`my_first_env` هذا يعني أن تستخدم الآن بيئتك الوهمية, و مخرج الأمر

``` bash

pip --version

```

سيظهر لك المعطيات التالي و التي تشير إلى أن مفسر البايثون المستعمل هو داخل مجلد البيئة الوهمية:

``` bash

pip 9.0.1 from /home/yassine/projects/my_first_env/lib/python2.7/site-packages (python 2.7)

```

لكن غالبا, لا تريد إنشاء بيئة وهمية بنفس إصدار البايثون الخاص بنظامك, و هو ما فعلناه في هذه الحالة, لا مشكلة أولا لتعطيل البيئة الوهمية نستعمل اﻷمر `deactivate` و لحذفها الأمر ببساطة إحدف المجلد و جميع محتوياته, الآن سنقوم بإنشاء بيئة وهمية بإصدار البايثون 3, و لفعل هذا هناك مجموعة من الخيارات الخاصة بالأمر `virtualenv` التي تساعدك لإنشاء البيئة المناسبة لك, من ضمنها `-p` أو `--python` مثلا لإنشاء بيئة وهمية تشتمل على الإصدار 3 للبايثون و ليكن 3.6 نستعمل __أمر واحد من الأمرين التالين__:

``` bash

virtualenv -p python3.6 my_first_env

virtualenv --python=python3.6 my_first_env

```

الأن أعد الخطوة الخاصة بتفعيل البيئة و من ثم جلب معلومات الخاصة بإصدار البايثون, و ستجد أنه موجه الأوامر سيظهر لك الإصدار 3.6, هنئيا الآن يمكنك تطوير برامجك بإي إصدار تريد, و بدون الحاجة إلى التعامل مع مفسر و المكتبات المتبثة إفتراضيا على نظامك, هناك أيضا [خيارات أخرى يمكنك التعرف عليها][8] إن أردت تخصيص بيئتك الوهمية.

[1]: https://docs.python.org/3/library/venv.html "venv"
[2]: https://docs.python.org/dev/whatsnew/3.6.html#id8 "ما الجديد في البايثون 3,6"
[3]: https://pypi.python.org/pypi/virtualenv "virtualenv"
[4]: https://github.com/pyenv/pyenv "pyenv"
[5]: https://github.com/rbenv/rbenv "rbenv"
[6]: https://www.python.org/downloads/ "تحميل البايثون"
[7]: https://virtualenv.pypa.io/en/stable/installation/ "تتبيث virtualenv"
[8]: https://virtualenv.pypa.io/en/stable/reference/#options "virtualenv options"
