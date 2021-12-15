(قابلية قراءة الشفرة للتطبيق)=
# كتابة كود مقروء بشري

كتابة شفرة واضحة ومعلقة جيدا وقابلة للقراءة وإعادة الاستخدام لا تفيد فقط المجتمع (أو الجمهور) الذي تقوم بتطويره من أجله. قد يكون هذا مختبرك، أو متعاونين خارجيين، أو أصحاب المصلحة، أو قد تكتب برمجيات مفتوحة المصدر للتوزيع العالمي! أيّاً كان المقياس الذي تعمله، فإن القروية تُعدّ!

إليك بعض الجوانب التي يجب مراعاتها عند جعل التعليمات البرمجية الخاصة بك سهلة القراءة من قبل الآخرين.

## طول الخط

وهناك بعض الاتفاق على طول خطوط الترميز. ويقترح PEP8 حرف كحد أقصى 79 حرف في السطر الواحد و80 حرف في دليل أسلوب R. وهذا يعني أن الخطوط يمكن أن تتواءم بسهولة مع الشاشة، ويمكن فتح نوافذ برمجة متعددة. يقال إنه إذا كان سطرك أطول من هذا فستكون دالتك معقدة للغاية ويجب فصلها! هذا هو جوهر طريقة برمجة R، الذي لديه حتى مشغل خاص `٪>٪` الذي ينقل الكائن السابق إلى الوظيفة التالية، لذا مطلوب عدد أقل من الأحرف:

```r
تم استرداد_melt_dat <- قراءة_csv('~/files/2019-05-17_dat.csv') ٪>
استرجاع () ٪>٪
ذوبان () #لدينا الآن بيانات مستعادة ومذابة تسمى مستعادة_melt_dat
```

## التعليق

تم وصف التعليقات بأنها "رسائل حب لنفسك في المستقبل" من قبل جون بييرس، منشئ النفس. التعليقات يمكن حظرها أو إدخالها.  
المبادئ التوجيهية لـ PEP8 لديها اقتراحات ثابتة بأن تمنع التعليقات يجب أن تكون جمل كاملة، لديك مسافتين بعد فترة زمنية، واتبع دليل نمط التاريخ (Strunk and White). لحسن الحظ، لم تعد عناصر النمط 'تتطلب` تركيزا غير منصف على الضمائر الذكرية. في حين أن التعليقات الواردة ينبغي أن تستخدم بشكل محدود. الاحتفاظ بتعليقات واضحة وموجزة لا يسمح لك فقط بتتبع القرارات التي اتخذتها، ما هي الوظائف المعينة التي تقوم بها، وما هي المتغيرات المستخدمة، كما أنها تسمح لأشخاص آخرين برؤية عمليات تفكيركم. بناء الجملة للتعليقات يتفاوت حسب لغات البرمجة. في R و Python، يتم استخدام هاشتاج، في حين يتم استخدام الأقواس `/* * /*` في C و Java، وفي C+++/C# هناك خط مزدوج `//` يبدي أسطر واحدة.

في بايثون
```python
مرات = 10 # تعيين عدد صحيح
my_variable = "متغيري هو %s مرات أفضل منك" %tiملم #تعيين my_variable إلى سلسلة
print(my_variable) #طباعة القيمة
```

في R:
```r
my_func = function(number){ #R function

(number * 5) - 2
}
print(my_function (2))
```

للحصول على تعليقات أطول، يمكن إدراج المعلومات فوق كتلة التعليمات البرمجية. في بايتون، يمكنك استخدام علامات الكلام الثلاثية كقوسين. وهذا سيعلق على أي شيء بينهما.

```python
"""
الدالة التالية تأخذ رقما، تضرب في 5، وتطرح 2.
وقد يبدو هذا عديم الجدوى، ولكنه أمر بسيط بالنسبة للمظاهرة.
"""
def myfunc(numb): #python function
      عادة(numb*5)-2)
print(myfunc(8))
```
الكتل الأطول من التعليقات غير متوفرة في R. هناك طرق حول هذا، مثل إعداد سلسلة أو بيان إذا(مزيف):

```r
"1- هذه سلسلة لن يتم تقييمه بواسطة R ولن تثير
والاستثناء"

if(false){
2 - كل تعليقك يمكن أن يذهب إلى هنا ولن يتم تقييمه أبدا.
كما يعني أنك تحتفظ باقتراح طول سطر 80 حرفاً.
أيضًا في RStudio يمكنك طي التعليق بعيداً باستخدام السهم المجاور لرقم السطر
من بيان الحالة.
}
```

أو التعليق على سطر فردي:

```r
#هذا أيضا تعليق طويل جدا
#يغطي العديد من الأسطر.
```
قد يكون لدى IDE الخاص بك اختصار لوحة المفاتيح للتعليق على الكتل.

## النزول

ويقترح دليل أسلوب "R" أنه ينبغي فصل الخطوط:
```r
بواسطة
  مساحتين
```
وليس
```r
 مزيج
   من
    علامات التبويب
      والمسافات.
```

ومن الواضح أن حجج الوظيفة يمكن أحيانا أن توسع 80 حرفا بكثير. وفي هذه الحالة، يوصى بأن يكون السطر الثاني مفقودا في بداية الحجج، على النحو التالي:

```r
my_variable <- a_really_long_function(البيانات = "2019-05-17_Long_File_Name_2",
                                      رأس = TRUE, فلونز = TRUE)

```

هذه بالطبع مجرد مبادئ توجيهية، ويجب عليك اختيار العناصر التي تناسب أسلوب البرمجة الخاص بك. ومع ذلك، ومرة أخرى، من المهم ضمان أن تكون متسقا عند التعاون، وأن تكون قادرا على الاتفاق على أسلوب مشترك. قد يكون من المفيد إنشاء ملف جديد يصف نمط البرمجة الخاص بك حتى يمكن للمتعاونين أو المساهمين اتباع العرض الخاص بك.

### ...نهاية. ...نهاية.  ...أو نهاية \\n

إذا كنت تشارك الملفات النصية أو تعمل بشكل تعاوني على الأدلة أو الوثائق، ثم هناك الكثير من الجدل حول ما إذا كان سيتم استخدام مسافة أو مساحتين بعد فترة من الزمن. عند استخدام Markdown، يمكن أن يكون من الأوضح إدراج سطر جديد بعد كل جملة. هذا الفصل (ومعظم هذا الكتاب، إن لم يكن كله) له سطر جديد بعد كل جملة تجعل النص الخام أسهل قراءته، مراجعة مشكلة المباعدة بين الولادات وحلها.

```{figure} ../../figures/xkcd1285.png
---
الطول: 500px
الاسم: xkcd1285
بديل : مجموعتان تحملان أعلام مختلفة و تقاتل، واحد يقول "مساحتين بعد فترة" والآخر يقول "مسافة واحدة بعد فترة". بينما يقف شخص مع علمه الذي يقول "استراحة الخط بعد كل جملة"
---
*استراحة الخط بعد كل جملة تجعل من السهل مراجعتها والتعليق عليها - [XKCD Link](https://www. xplainxkcd.com/wiki/index.php/1285:_Third_Way)*
```