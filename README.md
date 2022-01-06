<div dir="rtl">

![Design Patterns For Humans](https://cloud.githubusercontent.com/assets/11269635/23065273/1b7e5938-f515-11e6-8dd3-d0d58de6bb9a.png)
***

<h3 dir="rtl" align="center">
🎉 توضیح ساده دیزاین پترن ها ! 🎉
</h3>

<p dir="rtl" align="center">
فهمیدن دیزاین پترن ها از اون موضوع هاست که ذهن رو به چالش میکشه. اینجا سعی می‌کنم با مثال های ساده از دنیای واقعی و دنیای کد ، اونو راحت وارد ذهنتون کنم
</p>


***
این ریپازیتوری نسخه فارسی شده    [این](https://github.com/rommel-sunga/design-patterns-for-humans-python) ریپازیتوریه که
خودش نسخه پایتونیزه شده [این](https://github.com/kamranahmedse/design-patterns-for-humans) ریپازیتوریه
***


🚀 مقدمه
=================

### دیزاین پترن ها یک سری دستور العمل برای مقابله با یک سری مشکلات رایج هستند.

اونا یک سری کلاس، پکیج یا کتابخونه نیستند که با اضافه کردنشون به پروژه‌تون جادو کنن. در عوض یک سری راه حل بهتون میدن که
در شرایط خاص به مشکل نخورین.


<br>

> پس دیزاین پترن ها راه حلی برای مشکلات تکراری هستن

<br>

**ویکی پدیا** دیزاین پترن‌ها رو اینطوری توصیف میکنه:

> در مهندسی نرم‌افزار، الگوی طراحی یک راه‌حل عمومی قابل تکرار برای مشکلات متداول در زمینه طراحی نرم‌افزار است. الگوی طراحی، یک طراحی تمام‌شده نیست که به صورت مستقیم بتواند تبدیل به کد منبع یا ماشین شود؛ بلکه، یک توضیح یا قالب برای حل یک مسئله در شرایط مختلف است. الگوها در واقع بهترین روش ممکن هستند که یک برنامه‌نویس می‌تواند در هنگام طراحی یک برنامه برای حل مشکلاتش از آن‌ها استفاده کند.


<br>

⚠ هشدار
-----------------

- الگو های طراحی برای همه مشکلات راه حل ندارن.
- سعی نکنین حتما توی پروژه هاتون از اونا استفاده کنین و یادتون باشه دیزاین پترن ها راه حلی برای مشکلات هستن، نه راه حلی
  برای پیدا کردن مشکلات، پس خیلی درگیر پیدا کردن دلیل برای استفاده ازشون نباشین.
- اگه از اونا جای درست استفاده کنین، شما پروژه رو از مشکلات نجات دادین درغیر اینصورت قراره فاجعه به بار بیاد.

<br>
<br>

***

<br>

<div align="center">

# Creational Design Patterns

</div>



به زبون ساده:
> #### الگو های طراحی سازنده، به مشکلات مربوط به ساخت ابجکت ها می‌پردازن

ویکی پدیا:
<div dir="ltr">

> In software engineering, creational design patterns are design patterns that deal with object creation mechanisms, trying to create objects in a manner

</div>

<br>

<div align="center">

## 🏠 Simple Factory

</div>

یک مثال از دنیای واقعی:
> فرض کنید درحال ساخت یک خونه هستین و توی بخش های مختلف به درب نیاز دارین، خب اگه برای هر کدومش بخواین لباس نجاری بپوشین و درگیر ساختنش بشین، قراره کلی هرج و مرج تجربه کنین. پس مردم ترجیح میدن برای حل این مشکل اونو از یک کارخونه تهیه کنن.


به زبون ساده:
> این دیزاین پترن برای کاربر اون چیزی که نیاز داره رو میسازه بدون اینکه اون کاربر رو درگیر منطق پشتش بکنه

ویکی پدیا:
<div dir="ltr">

> In object-oriented programming (OOP), a factory is an object for creating other objects – formally a factory is a function or method that returns objects of a varying prototype or class from some method call, which is assumed to be "new".

</div>

### **مثال برنامه نویسی**

توی این مثال میخوایم از اون مثال ساخت درب استفاده کنیم

پس اول ما اینترفیس مربوط به درب رو میسازیم و در ادامه یک نمونه پیاده سازی براش پیاده سازی میکنیم:

<div dir="ltr">

```python
class Door:
    def getWidth(self):
        pass

    def getHeight(self):
        pass


class WoodenDoor(Door):
    width = None
    height = None

    def __init__(self, width=5, height=5):
        self.width = width
        self.height = height

    def getWidth(self):
        return self.width

    def getHeight(self):
        return self.height
```

</div>

و حالا یک کلاس factory برای ساخت درب میسازیم:
<div dir="ltr">

```python
class DoorFactory:
    @staticmethod
    def makeDoor(width, height):
        return WoodenDoor(width, height)
```

</div>

حالا بیاین ببینیم چطوری می‌تونیم ازشون استفاده کنیم:

<div dir="ltr">

```python
door = DoorFactory.makeDoor(10, 10)
print(door.getHeight())
print(door.getWidth())
```

</div>


<br>
<br>



<div align="center">

## 🏭 Factory Method

</div>


یک مثال از دنیای واقعی:
> یک مدیر رو فرض کنید که وظیفه استخدام افراد رو به عهده داره. مطمئنن براش غیر ممکنه که مصاحبه با همه افراد در پوزیشن های مختلف شرکت رو خودش انجام بده! پس میاد با توجه به پوزیشن تصمیم میگیره که کدوم یکی از کارمند ها مسئولیت مصاحبه رو به عهده بگیره.

به زبون ساده:
> این دیزاین پترن میگه جای اینکه خودمون مستقیم درگیر ساخت ابجکت بشیم، این کار رو به عهده کلاس های فرزند بزاریم.

ویکی پدیا:
<div dir="ltr">

> In class-based programming, the factory method pattern is a creational pattern that uses factory methods to deal with the problem of creating objects without having to specify the exact class of the object that will be created. This is done by creating objects by calling a factory method—either specified in an interface and implemented by child classes, or implemented in a base class and optionally overridden by derived classes—rather than by calling a constuctor.

</div>




**مثال برنامه نویسی**

بیاین از مثال مدیر استخدام برای درک بهتر استفاده کنیم.

پس اول یک اینترفیس برای مصاحبه کننده ها میسازیم و چند پیاده‌سازی هم برای اون ایجاد می‌کنیم:
<div dir="ltr">

```python
class Interviewer:
    def askQuestions(self):
        pass


class Developer(Interviewer):
    def askQuestions(self):
        print
        'Asking about design patterns'


class CommunityExecutive(Interviewer):
    def askQuestions(self):
        print
        'Asking about community building'
```

</div>

خب حالا `HiringManager` رو میسازیم:
<div dir="ltr">

```python
class HiringManager:
    def makeInterviewer(self):
        pass

    def takeInterview(self):
        interviewer = self.makeInterviewer()
        interviewer.askQuestions()

```

</div>

در نهایت هر فرزند میتونه ازش ارث بری کنه و متد `makeInterviewer` خودش رو داشته باشه
<div dir="ltr">

```python
class DevelopmentManager(HiringManager):
    def makeInterviewer(self):
        return Developer()


class MarketingManager(HiringManager):
    def makeInterviewer(self):
        return CommunityExecutive()
```

</div>

و برای استفاده ازش به این صورت عمل می کنیم:
<div dir="ltr">

```python
devManager = DevelopmentManager()
devManager.takeInterview()

marketingManager = MarketingManager()
marketingManager.takeInterview()
```

</div>

<br>

**چه موقع باید ازش استفاده کنیم؟**

اساساً زمانی ازین الگو استفاده میشه که چندین کلاس با ریشه مشترک داریم (یعنی چندین کلاس یک کلاس parent رو پیاده‌سازی
می‌کنند) و با توجه به شرایط تصمیم میگیریم از یکی از اون ها استفاده کنیم


<br>

<div align="center">

## 🔨 Abstract Factory

</div>



یک مثال از دنیای واقعی:
> بیاین از مثال مربوط به Simple Factory اینجا استفاده کنیم. فرض کنید در حال ساخت خونه هستین و نیاز به چند درب مختلف دارید ولی اینبار نیاز به درب چوبی، درب ضد سرقت، درب شیشه و ... دارین. به طبع هم برای خرید باید به مغازه های مختلفی مراجعه کنید ، از طرفی برای استفاده ازشون هم ممکنه نیاز به متخصص مربوطه داشته باشین پس باید به متخصص مربوط به خودش مراجعه کنید. برای مثال ما برای درب چوبی به چوب فروشی میریم و برای نصبش هم از یک نجار کمک میگیریم یا برای درب شیشه ای به مغازه و متخصص مربوط به خودش مراجعه میکنیم.

به زبون ساده:
> این دیزاین پترن تا حد زیادی مشابه simple factory هست با این تفاوت که `مجموعه ای` از اشیا مرتبط بهم رو ایجاد میکنه.

ویکی پدیا:
<div dir="ltr">

> The abstract factory pattern provides a way to encapsulate a group of individual factories that have a common theme without specifying their concrete classes

</div>

<br>

**مثال برنامه نویسی**

خب همون مثال ساخت خونه و نیاز به درب های مختلف رو ترجمه میکنیم.

اول باید اینترفیس درب رو بسازیم و چند پیاده‌سازی ازش ایجاد کنیم :
<div dir="ltr">

```python
class Door:
    def getDescription(self):
        pass


class WoodenDoor(Door):
    def getDescription(self):
        print
        'I am a wooden door'


class IronDoor(Door):
    def getDescription(self):
        print
        'I am an iron door'
```

</div>

در مرحله بعد برای هر درب متخصص مربوطه رو ایجاد می‌کنیم:

<div dir="ltr">

```python
class DoorFittingExpert:
    def getDescription(self):
        pass


class Welder(DoorFittingExpert):
    def getDescription(self):
        print
        'I can only fit iron doors'


class Carpenter(DoorFittingExpert):
    def getDescription(self):
        print
        'I can only fit wooden doors'
```

</div>

حالا اینجاست که ما سراغ پیاده‌سازی دیزاین پترن‌مون میریم.

برای مثال کلاس `DoorFactory` زمانی استفاده میشه که نیاز به درب چوبی داریم و کارش اینه که برای ایجاد ابجکت درب (که اینجا
درب چوبی هست) از کلاس `WoodenDoor` و برای ایجاد ابجکت متخصص (که اینجا نجار هست) از `Carpenter` استفاده کنه.

این موضوع برای درب آهنی و ... هم بطور مشابه پیاده سازی میشه.

<div dir="ltr">

```python
class DoorFactory:
    def makeDoor(self):
        pass

    def makeFittingExpert(self):
        pass


class WoodenDoorFactory(DoorFactory):
    def makeDoor(self):
        return WoodenDoor()

    def makeFittingExpert(self):
        return Carpenter()


class IronDoorFactory(DoorFactory):
    def makeDoor(self):
        return IronDoor()

    def makeFittingExpert(self):
        return Welder()
```

</div>

روش استفاده ازش هم به این صورت هست:
<div dir="ltr">

```python
woodenFactory = WoodenDoorFactory()

door = woodenFactory.makeDoor()
expert = woodenFactory.makeFittingExpert()

door.getDescription()
expert.getDescription()

-----------------------------------------------

ironFactory = IronDoorFactory()

door = ironFactory.makeDoor()
expert = ironFactory.makeFittingExpert()

door.getDescription()
expert.getDescription()
```

</div>

همونطور که میبیند، می‌تونیم بطور مشابه با هر دو نوع درب برخورد کنیم و ازین موضوع مطمئن باشیم که متخصص اشتباه برای یک درب
انتخاب نمی‌کنیم.

<br>

**چه موقع باید ازش استفاده کنیم؟**

زمانی که وابستگی های منطقی نه چندان ساده برای ایجاد وجود داره، میتونیم ازین دیزاین پترن استفاده کنیم






<br>

<div align="center">

## 🔨 Builder

</div>

یک مثال از دنیای واقعی:
> فرض کنید به یک رستوران رفتید و شما یک همبرگر معمولی سفارش می‌دید. این یک مثال از Simple Factory هست یعنی بدون اینکه سوال اضافه ای بپرسن اون رو براتون میارن. توی بعضی موارد پیش میاد که نیاز به یک سفارش سفارشی تر دارین. یعنی میخواین نوع نون رو مشخص کنید یا نوع سسی که براتون استفاده میکنن، توی این شرایط Builder به کمکمون میاد.


<br>

به زبون ساده:
> در واقع کار Builder اینه که توی ساخت ابجکت های پیچیده یا ابجکت هایی که نیاز به شخصی سازی زیادی دارن، بهمون کمک بکنه.
>
> در واقع روش کارش به این صورت هست که بجای اینکه تعداد زیادی پارامتر رو از ورودی تابع سازنده دریافت کنیم (`__init__`) ، اون دیتارو بصورت مرحله به مرحله دریافت کنیم.

برای همه ما پیش اومد که یک تابع سازنده به این شکل ببینیم:

<div dir="ltr">

```python
def __init__(self, size, cheese=True, pepperoni=True, tomato=False, lettuce=True)
```

</div>

در این شرایط معمولا Builder میتونه به دادمون برسه.


<br>

ویکی پدیا:

<div dir="ltr">

> The builder pattern is an object creation software design pattern with the intentions of finding a solution to the telescoping constructor anti-pattern.
</div>

<br>

**مثال برنامه نویسی**

در بخش برنامه نویسی هم میخوام مثال برگر رو براتون ترجمه کنم.

اولین مرحله اینه که یک کلاس برگر معمولی داشته باشیم:

<div dir="ltr">

```python
class Burger:
    _size = None

    _cheese = False
    _pepperoni = False
    _lettuce = False
    _tomato = False

    def __init__(self, builder):
        self._size = builder.size
        self._cheese = builder.cheese
        self._pepperoni = builder.pepperoni
        self._lettuce = builder.lettuce
        self._tomato = builder.tomato
```

</div>

در ادامه کلاس Builder رو براش ایجاد میکنیم:

<div dir="ltr">

```python
class BurgerBuilder:
    size = None

    cheese = False
    pepperoni = False
    lettuce = False
    tomato = False

    def __init__(self, size):
        self.size = size

    def addPepperoni(self):
        self.pepperoni = True
        return self

    def addLettuce(self):
        self.lettuce = True
        return self

    def addCheese(self):
        self.cheese = True
        return self

    def addTomato(self):
        self.tomato = True
        return self

    def build(self):
        return Burger(self)
```

</div>

روش استفاده از کلاس Builder هم به این صورت هست:
<div dir="ltr">

```python
burger = BurgerBuilder(10).addPepperoni().addLettuce().addTomato().build()

print(vars(burger))
```

</div>

**چه موقع باید ازش استفاده کنیم؟**

همونطور که قبل تر اشاره کردم این دیزاین پترن رو معمولا برای ساخت ابجکت های پیچیده یا ابجکت هایی که نیاز به شخصی سازی
زیادی دارن استفاده میکنیم.





















<br>

<div align="center">

## 🐑 Prototype

</div>




یک مثال از دنیای واقعی:
> چیزی درمورد دالی شنیدین ؟ ([اگه نه اینجارو بخونید](https://fa.wikipedia.org/wiki/%D8%AF%D8%A7%D9%84%DB%8C_(%DA%AF%D9%88%D8%B3%D9%81%D9%86%D8%AF)))
>
>خیلی اینجا توضیح نمیدم، فقط بدونید همه‌چیز مربوط به شبیه سازیه!

به زبون ساده:
> مشکل از اینجا شروع میشه که یک ابجکت دارید و نیاز دارید از اون یک کپی ایجاد کنین. چطوری این کار رو میکنین؟ اول باید یک ابجکت جدید از همون کلاس ایجاد کنین بعد باید مقادیر ابجکت اصلی رو در ابجکت جدید کپی کنید. حالا از همین پروسه طاقت فرسا که بگذریم، این مشکل وجود داره این هست که به متغیر های خصوصی دسترسی ندارید.
>
> دیزاین پترن Prototype میگه یک Interface مشترک داشته باشید که وظیفه‌ش ساخت یک ابجکت کپی از روی ابجکت فعلی باشه.




ویکی پدیا:
<div dir="ltr">

> The prototype pattern is a creational design pattern in software development. It is used when the type of objects to create is determined by a prototypical instance, which is cloned to produce new objects.
</div>



**مثال برنامه نویسی**

فرض کنید کلاس SomeComponent به این صورت تعریف شده:


<div dir="ltr">

```python
class SomeComponent:
    def __init__(self, some_int, some_list_of_objects, some_circular_ref):
        self.some_int = some_int
        self.some_list_of_objects = some_list_of_objects
        self.some_circular_ref = some_circular_ref
```

</div>


پایتون magic method هایی برای این مساله در نظر گرفته که ماهم از همون دو تابع معروف copy و deep copy استفاده میکنیم:
<div dir="ltr">

```python
    def __copy__(self):


    some_list_of_objects = copy.copy(self.some_list_of_objects)
some_circular_ref = copy.copy(self.some_circular_ref)
new = self.__class__(
    self.some_int, some_list_of_objects, some_circular_ref
)
new.__dict__.update(self.__dict__)
return new


def __deepcopy__(self, memo={}):
    some_list_of_objects = copy.deepcopy(self.some_list_of_objects, memo)
    some_circular_ref = copy.deepcopy(self.some_circular_ref, memo)
    new = self.__class__(
        self.some_int, some_list_of_objects, some_circular_ref
    )
    new.__dict__ = copy.deepcopy(self.__dict__, memo)

    return new
```

</div>

**تفاوت Copy و Deep Copy ؟**
<br>
توی copy، یک متغیر ساخته می‌شود و به مکانی توی حافظه، که مقدار متغیر قبلی توش قرار گرفته، اشاره می‌کنه. پس اگر شما مقدار
متغیر اول رو تغییر بدین، متغیر دوم هم تغییر می‌کنه. و همین‌طور اگر مقدار متغیر دوم رو تغییر بدین، مقدار متغیر اول هم
تغییر می‌کنه.

ولی توی deep copy، یک متغیر ساخته می‌شه و مقدار متغیر قبلی توی اون کپی می‌شه. در نتیجه تغییر ابجکت اول یا ابجکت کپی
تغییری توی اون یکی به وجود نمیاره.





<br>

<div align="center">

## 💍 Singleton

</div>
در هر زمان فقط یک رئیس جمهور یک کشور می تواند وجود داشته باشد. همان رئیس جمهور باید هر زمان که وظیفه می خواهد وارد عمل شود. رئیس جمهور اینجا مجرد است.


یک مثال از دنیای واقعی:
> در هر زمان فقط یک رئیس جمهور میتونه برای کشور وجود داشته باشه. در نتیجه هرجا به رئیس جمهور نیاز هست باید خودش وارد عمل بشه. رئیس جمهور توی این مثال singleton هست.

به زبون ساده:
> این دیزاین پترن تضمین می‌کنه از یک کلاس خاص فقط یک ابجکت وجود داشته باشه.

ویکی پدیا:

<div dir="ltr">

> In software engineering, the singleton pattern is a software design pattern that restricts the instantiation of a class to one object. This is useful when exactly one object is needed to coordinate actions across the system.
</div>
⚠️ دیزاین پترن singleton در واقع یک آنتی پترن شناخته می‌شه و باید از استفاده زیاد اون جلوگیری کنیم. لزوما بد نیست و میتونه کاربرد های خوبی داشته باشه ولی باید با احتیاط ازش استفاده کرد چون تغییر توی هر بخش برنامه، میتونه روی بخش‌های دیگه هم تاثیر بزاره که ابن خودش دیباگ کردن پروژه هارو خیلی سخت می‌کنه.

<br>

**مثال برنامه نویسی**

بطور کلی برای ساخت singleton باید تابع سازنده private بشه، cloning و متود های copy بسته بشن و تابع استاتیکی برای ساخت
ابجکت تعریف بشه.

ولی توی پایتون راه حل ساده تری وجود داره که اون استفاده از metaclass هاست:
<div dir="ltr">

```python
class SingletonMeta(type):
    _instances = {}

    def __call__(cls, *args, **kwargs):
        if cls not in cls._instances:
            instance = super().__call__(*args, **kwargs)
            cls._instances[cls] = instance
        return cls._instances[cls]


class Singleton(metaclass=SingletonMeta):
    def some_business_logic(self):
# ...


```

</div>

نحوه فراخوانی هم در این روش تفاوتی نمیکنه:
<div dir="ltr">

```python
if __name__ == "__main__":
    # The client code.

    s1 = Singleton()
    s2 = Singleton()

    if id(s1) == id(s2):
        print("Singleton works, both variables contain the same instance.")
    else:
        print("Singleton failed, variables contain different instances.")
```

</div>





<br>
<br>

***

<br>

<div align="center">

# Creational Design Patterns

</div>

به طور کلی با روابط بین موجودیت‌ها سروکار دارند، این الگوها کار موجودیت‌ها با یکدیگر را ساده‌تر می‌کنند. به زبون ساده:
> بطور کلی الگو های طراحی ساختاری با روابط بین موجودیت ها و ترکیب کردن اونا کار دارن.


ویکی پدیا:

<div dir="ltr">

> In software engineering, structural design patterns are design patterns that ease the design by identifying a simple way to realize relationships between entities.

</div>


<br>

<div align="center">

## 🔌 Adapter

</div>

یک مثال از دنیای واقعی:
> واضح ترین مثال برای این الگوی طراحی خوده آداپتور ها هستن (برای مثال، آداپتور های تبدیل سه شاخه به دو شاخه رو برای شارژر ها)
>
> یا مترجمی که کلمات یک نفر رو برای فرد دیگه ترجمه میکنه

به زبون ساده:
> آداپتور بهتون کمک میکنه تا یک شی ناسازگار رو سازگار کنین تا بتونین توی کلاس های مختلف ازش استفاده کنین.


ویکی پدیا:
<div dir="ltr">

> In software engineering, the adapter pattern is a software design pattern that allows the interface of an existing class to be used as another interface. It is often used to make existing classes work with others without modifying their source code.
</div>

**مثال برنامه نویسی**

فرض کنید یک شکارچی به شیر ها حمله میکنه و اون ها غرش میکنن

خب اول باید یک اینترفیس `lion` بسازیم که انواع شیر های مختلف ازش استفاده کنن
<div dir="ltr">

```python
class Lion:
    def roar(self):
        pass


class AfricanLion(Lion):
    def roar(self):
        pass


class AsianLion(Lion):
    def roar(self):
        pass
```

</div>

خب حالا شکارچی وقتی شکار انجام بده اون شیر غرش انجام میده

<div dir="ltr">

```python
class Hunter:
    def hunt(self, lion):
        lion.roar()
```

</div>

حالا فرض کنید یک موجودیت جدید مثل `سگ وحشی` به برنامه اضافه شده.

خب سگ غرش انجام نمیده بجای اون `bark` انجام میده.

خب اینجا `سگ وحشی` با تابع `hunt` شکارچی ناسازگار میشه. (چون توی تابع hunt ما برای حیوونی در حال شکار شدن هست تابع roar
رو صدا میزنیم)

برای حلش به این صورت میتونیم براش آداپتور تعریف کنیم.

<div dir="ltr">

```python
class WildDog:
    @staticmethod
    def bark():
        pass


class WildDogAdapter(Lion):
    _dog = None

    def __init__(self, dog):
        self._dog = dog

    def roar(self):
        self._dog.bark()
```

</div>

در ادامه هم نحوه استفاده ازش رو میبینید:

<div dir="ltr">

```python
wildDog = WildDog
wildDogAdapter = WildDogAdapter(wildDog)

hunter = Hunter()
hunter.hunt(wildDogAdapter)
```


</div>
در واقع مثال خیلی خوبی نبود ولی مفهوم رو به خوبی منتقل میکنه.

پیشنهاد میکنم برای درک بهتر این موضوع رو برای این سناریو آداپتور تعریف کنید: ورودی یک کلاس excel است ولی دیتای شما csv هست.





</div>
