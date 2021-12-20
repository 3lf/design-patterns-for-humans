<div dir="rtl">

![Design Patterns For Humans](https://cloud.githubusercontent.com/assets/11269635/23065273/1b7e5938-f515-11e6-8dd3-d0d58de6bb9a.png)
***

<h3 dir="rtl" align="center">
🎉 توضیح ساده دیزاین پترن ها ! 🎉
</h3>

<p dir="rtl" align="center">
فهمیدن دیزاین پترن ها از اون موضوع هاست که ذهن رو به چالش میکشه. اینجا سعی میکنم با مثال های ساده از دنیای واقعی و دنیای کد ، اونو راحت وارد ذهنتون کنم
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

پس اول ما اینترفیس مربوط به درب رو میسازیم و در ادامه یک نمونه پیاده سازی براش پیاده سازی میکنیم

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

و حالا یک کلاس factory برای ساخت درب میسازیم
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

> In class-based programming, the factory method pattern is a creational pattern that uses factory methods to deal with the problem of creating objects without having to specify the exact class of the object that will be created. This is done by creating objects by calling a factory method—either specified in an interface and implemented by child classes, or implemented in a base class and optionally overridden by derived classes—rather than by calling a constructor.

</div>




**مثال برنامه نویسی**

بیاین از مثال مدیر استخدام برای درک بهتر استفاده کنیم.

پس اول یک اینترفیس برای مصاحبه کننده ها میسازیم و چند پیاده‌سازی هم برای اون ایجاد می‌کنیم.
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

خب حالا `HiringManager` رو میسازیم
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
>  این دیزاین پترن تا حد زیادی مشابه simple factory هست با این تفاوت که `مجموعه ای` از اشیا مرتبط بهم رو ایجاد میکنه.

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

یعنی مثلا برای در زمانی که نیاز به درب چوبی داریم برای ابجکت درب از کلاس `WoodenDoor` و برای ابجکت متخصص از `Carpenter` استفاده می‌کنیم.

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

همونطور که میبیند براحتی میتونیم از پیاده سازی مشابه برای هر دو نوع درب استفاده کنیم و ازین موضوع مطمئن باشیم که متخصص
اشتباه برای یک درب انتخاب نمیشه.

<br>

**چه موقع باید ازش استفاده کنیم؟**

زمانی که وابستگی های منطقی نه چندان ساده برای ایجاد وجود داره، میتونیم ازین دیزاین پترن استفاده کنیم



</div>
