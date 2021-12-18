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
این ریپازیتوری نسخه فارسی شده    [این](https://github.com/rommel-sunga/design-patterns-for-humans-python) ریپازیتوریه که خودش نسخه پایتونیزه شده [این](https://github.com/kamranahmedse/design-patterns-for-humans) ریپازیتوریه
***


🚀 مقدمه
=================

### دیزاین پترن ها یک سری دستور العمل برای مقابله با یک سری مشکلات رایج هستند.

اونا یک سری کلاس، پکیج یا کتابخونه نیستند که با اضافه کردنشون به پروژه‌تون جادو کنن. در عوض یک سری راه حل بهتون میدن که در شرایط خاص به مشکل نخورین.


<br>

> پس دیزاین پترن ها راه حلی برای مشکلات تکراری هستن

<br>

**ویکی پدیا** دیزاین پترن‌ها رو اینطوری توصیف میکنه:

>در مهندسی نرم‌افزار، الگوی طراحی یک راه‌حل عمومی قابل تکرار برای مشکلات متداول در زمینه طراحی نرم‌افزار است. الگوی طراحی، یک طراحی تمام‌شده نیست که به صورت مستقیم بتواند تبدیل به کد منبع یا ماشین شود؛ بلکه، یک توضیح یا قالب برای حل یک مسئله در شرایط مختلف است. الگوها در واقع بهترین روش ممکن هستند که یک برنامه‌نویس می‌تواند در هنگام طراحی یک برنامه برای حل مشکلاتش از آن‌ها استفاده کند.


<br>

⚠ هشدار
-----------------

- الگو های طراحی برای همه مشکلات راه حل ندارن.
- سعی نکنین حتما توی پروژه هاتون از اونا استفاده کنین و  یادتون باشه دیزاین پترن ها راه حلی برای مشکلات هستن، نه راه حلی برای پیدا کردن مشکلات، پس خیلی درگیر پیدا کردن دلیل برای استفاده ازشون نباشین.
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
> در نظر بگیرید، شما در حال ساختن یک خونه هستید و به چند درب‌ نیاز دارید. اگر هر بار که به یک در نیاز داشتید، لباس های نجاری خودتون رو بپوشید و شروع به ساختن در کنید، قراره کلی بی نظمی پیش بیاد. در نتیجه مردم ترجیح میدن از یک کارخونه در بخرن.


به زبون ساده:
> این دیزاین پترن برای کاربر یک instance میسازه بدون اینکه اون کاربر رو درگیر منطق پشتش بکنه

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

```diff
+ جمله طلایی : factory design کارش اینه که کاربر از پیچیدگی های ساخت یک ابجکت دور کنه
```


</div>