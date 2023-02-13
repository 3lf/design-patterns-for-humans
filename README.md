<div dir="rtl">

![Design Patterns For Humans](https://cloud.githubusercontent.com/assets/11269635/23065273/1b7e5938-f515-11e6-8dd3-d0d58de6bb9a.png)

---

<h3 dir="rtl" align="center">
🎉 توضیح ساده دیزاین پترن‌ها ! 🎉
</h3>

<p dir="rtl" align="center">
فهمیدن دیزاین پترن‌ها از اون موضوع‌هاست که ذهن رو به چالش میکشه.
 اینجا سعی می‌کنم با مثال‌های ساده از دنیای واقعی و دنیای کد ، اونو راحت وارد ذهنتون کنم.
</p>

---

منبع اصلی این ریپازیتوری [این](https://github.com/rommel-sunga/design-patterns-for-humans-python) ریپازیتوری هست که
خودش نسخه پایتونیزه شده [این](https://github.com/kamranahmedse/design-patterns-for-humans) ریپازیتوریه.

در ترجمه، تعاریف و مثال‌ها از منابع مختلف فارسی و انگلیسی استفاده شده تا بهترین نتیجه حاصل بشه :)

---

</div>

<!-- TOC -->

- [Creational Design Patterns](#creational-design-patterns)
  - [🏠 Simple Factory](#-simple-factory)
  - [🏭 Factory Method](#-factory-method)
  - [🔨 Abstract Factory](#-abstract-factory)
  - [👷 Builder](#-builder)
  - [🐑 Prototype](#-prototype)
  - [💍 Singleton](#-singleton)
- [Structural Design Patterns](#structural-design-patterns)
  - [🔌 Adapter](#-adapter)
  - [🌉 Bridge](#-bridge)
  - [🌿 Composite](#-composite)
  - [☕ Decorator](#-decorator)
  - [📦 Facade](#-facade)
  - [🍃 Flyweight](#-flyweight)
  - [🎱 Proxy](#-proxy)
- [Behavioral Design Patterns](#behavioral-design-patterns)
  - [🔗 Chain of Responsibility](#-chain-of-responsibility)
  - [👮 Command](#-command)
  - [➿ Iterator](#-iterator)
  - [👽 Mediator](#-mediator)
  - [💾 Memento](#-memento)
  - [😎 Observer](#-observer)
  - [🏃 Visitor](#-visitor)
  - [💡 Strategy](#-strategy)
  - [💢 State](#-state)
  - [📒 Template Method](#-template-method)

<!-- TOC -->

<div dir="rtl" align="center">

# 🚀 مقدمه

</div>

<div dir="rtl">

دیزاین پترن‌ها یک سری دستور العمل برای مقابله با یک سری مشکلات رایج هستند.

اونا یک سری کلاس، پکیج یا کتابخونه نیستند که با اضافه کردنشون به پروژه‌تون جادو کنن. در عوض یک سری راه حل بهتون میدن که
در شرایط خاص به مشکل نخورین.

<br>

> پس دیزاین پترن‌ها راه حلی برای مشکلات رایج هستن.

<br>

**ویکی‌پدیا** دیزاین پترن‌ها رو اینطوری توصیف میکنه:

> در مهندسی نرم‌افزار، الگوی طراحی یک راه‌حل عمومی قابل تکرار برای مشکلات متداول در زمینه طراحی نرم‌افزار است. الگوی
> طراحی، یک طراحی تمام‌شده نیست که به صورت مستقیم بتواند تبدیل به کد منبع یا ماشین شود؛ بلکه، یک توضیح یا قالب برای حل
> یک
> مسئله در شرایط مختلف است. الگوها در واقع بهترین روش ممکن هستند که یک برنامه‌نویس می‌تواند در هنگام طراحی یک برنامه
> برای
> حل مشکلاتش از آن‌ها استفاده کند.

<br>
<div dir="rtl" align="right">

## ⚠ هشدار

</div>

- الگو‌های طراحی برای همه مشکلات راه حل ندارن.
- سعی نکنین حتما توی پروژه‌هاتون از اونا استفاده کنین و یادتون باشه دیزاین پترن‌ها راه حلی برای مشکلات هستن، نه راه حلی
  برای پیدا کردن مشکلات، پس خیلی درگیر پیدا کردن دلیل برای استفاده ازشون نباشین.
- اگه از اونا جای درست استفاده کنین، شما پروژه رو از مشکلات نجات دادین درغیر اینصورت قراره فاجعه به بار بیاد.

<br>
<br>

---

<br>

<div align="center">

# Creational Design Patterns

</div>

به زبون ساده:

> الگو‌های طراحی سازنده، به مشکلات مربوط به ساخت ابجکت‌ها می‌پردازن.

ویکی پدیا:

<div dir="ltr">

> In software engineering, creational design patterns are design patterns that deal with object creation mechanisms,
> trying to create objects in a manner

</div>

<br>

<div align="center">

## 🏠 Simple Factory

</div>

یک مثال از دنیای واقعی:

> فرض کنید درحال ساخت یک خونه هستین و توی بخش‌های مختلف به درب نیاز دارین، خب اگه برای هر کدومش بخواین لباس نجاری بپوشین
> و درگیر ساختنش بشین، قراره کلی هرج و مرج تجربه کنین. به همین دلیل مردم ترجیح میدن برای حل این مشکل اونو از یک کارخونه
> تهیه کنن.

به زبون ساده:

> این دیزاین پترن برای کاربر اون چیزی که نیاز داره رو میسازه بدون اینکه درگیر منطق پشتش بشه.

ویکی پدیا:

<div dir="ltr">

> In object-oriented programming (OOP), a factory is an object for creating other objects – formally a factory is a
> function or method that returns objects of a varying prototype or class from some method call, which is assumed to
> be "
> new".

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

توی این مثال میخوایم از اون مثال ساخت درب استفاده کنیم

پس اول ما اینترفیس مربوط به درب رو میسازیم و در ادامه یک نمونه پیاده‌سازی براش پیاده‌سازی میکنیم:

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

</details>

<details>
<summary>Typescript</summary>

<div dir="ltr">

```typescript
class Door {
  getWidth(): void {}
  getHeight(): void {}
}

class WoodenDoor extends Door {
  width: number | null;
  height: number | null;

  constructor(width: number = 5, height: number = 5) {
    super();
    this.width = width;
    this.height = height;
  }

  getWidth(): number {
    return this.width;
  }

  getHeight(): number {
    return this.height;
  }
}

class DoorFactory {
  static makeDoor(width: number, height: number): WoodenDoor {
    return new WoodenDoor(width, height);
  }
}

let door = DoorFactory.makeDoor(10, 10);
console.log(door.getHeight());
console.log(door.getWidth());
```

</div>

</details>

<br>
<br>

<div align="center">

## 🏭 Factory Method

</div>

یک مثال از دنیای واقعی:

> یک مدیر رو فرض کنید که وظیفه استخدام افراد رو به عهده داره. مطمئنن براش غیر ممکنه که مصاحبه با همه افراد در پوزیشن‌های
> مختلف شرکت رو خودش انجام بده! پس میاد با توجه به پوزیشن تصمیم میگیره که مسئولیت مصاحبه رو به عهده یکی از کارمند‌هاش
> بزاره.

به زبون ساده:

> این دیزاین پترن میگه جای اینکه خودمون مستقیم درگیر ساخت ابجکت بشیم، این کار رو به عهده کلاس‌های فرزند بزاریم.

ویکی پدیا:

<div dir="ltr">

> In class-based programming, the factory method pattern is a creational pattern that uses factory methods to deal with
> the problem of creating objects without having to specify the exact class of the object that will be created. This is
> done by creating objects by calling a factory method—either specified in an interface and implemented by child
> classes,
> or implemented in a base class and optionally overridden by derived classes—rather than by calling a constructor.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

بیاین از مثال مدیر استخدام برای درک بهتر استفاده کنیم.

پس اول یک اینترفیس برای مصاحبه کننده‌ها میسازیم و چند پیاده‌سازی هم برای اون ایجاد می‌کنیم:

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
        print('Asking about community building')
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

در نهایت هر فرزند میتونه ازش ارث بری کنه و متد `makeInterviewer` خودش رو داشته باشه:

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
می‌کنند) و با توجه به شرایط تصمیم میگیریم از یکی از اون‌ها استفاده کنیم.

</details>

<details>
<summary>Typescript</summary>

<div dir="ltr">

```typescript
class Interviewer {
  askQuestions(): void {}
}

class Developer extends Interviewer {
  askQuestions(): void {
    console.log("Asking about design patterns");
  }
}

class CommunityExecutive extends Interviewer {
  askQuestions(): void {
    console.log("Asking about community building");
  }
}

class HiringManager {
  makeInterviewer(): Interviewer {
    return null;
  }

  takeInterview(): void {
    let interviewer = this.makeInterviewer();
    interviewer.askQuestions();
  }
}

class DevelopmentManager extends HiringManager {
  makeInterviewer(): Developer {
    return new Developer();
  }
}

class MarketingManager extends HiringManager {
  makeInterviewer(): CommunityExecutive {
    return new CommunityExecutive();
  }
}

let devManager = new DevelopmentManager();
devManager.takeInterview();

let marketingManager = new MarketingManager();
marketingManager.takeInterview();
```

</div>

</details>

<br>

<div align="center">

## 🔨 Abstract Factory

</div>

یک مثال از دنیای واقعی:

> بیاین از مثال مربوط به Simple Factory اینجا استفاده کنیم. فرض کنید در حال ساخت خونه هستین و نیاز به چند درب مختلف
> دارید ولی اینبار نیاز به درب چوبی، درب ضد سرقت، درب شیشه و ... دارین. به طبع برای خرید باید به مغازه‌های مختلفی مراجعه
> کنید ، از طرفی برای استفاده ازشون هم ممکنه نیاز به متخصص مربوطه داشته باشین. برای مثال ما برای درب چوبی به چوب فروشی
> میریم و برای نصبش هم از یک نجار کمک میگیریم یا برای درب شیشه ای به مغازه و متخصص مربوط به خودش مراجعه میکنیم.

به زبون ساده:

> این دیزاین پترن تا حد زیادی مشابه simple factory هست با این تفاوت که `مجموعه ای` از اشیا مرتبط بهم رو ایجاد میکنه.

ویکی پدیا:

<div dir="ltr">

> The abstract factory pattern provides a way to encapsulate a group of individual factories that have a common theme
> without specifying their concrete classes

</div>

<br>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

خب همون مثال ساخت خونه و نیاز به درب‌های مختلف رو ترجمه میکنیم.

اول باید اینترفیس درب رو بسازیم و چند پیاده‌سازی ازش ایجاد کنیم :

<div dir="ltr">

```python
class Door:
    def getDescription(self):
        pass


class WoodenDoor(Door):
    def getDescription(self):
        print('I am a wooden door')


class IronDoor(Door):
    def getDescription(self):
        print('I am an iron door')
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
        print('I can only fit iron doors')


class Carpenter(DoorFittingExpert):
    def getDescription(self):
        print('I can only fit wooden doors')
```

</div>

حالا اینجاست که ما سراغ پیاده‌سازی دیزاین پترن‌مون میریم.

برای مثال کلاس `WoodenDoorFactory` زمانی استفاده میشه که نیاز به درب چوبی داریم و کارش اینه که برای ایجاد ابجکت درب (که
اینجا
درب چوبی هست) از کلاس `WoodenDoor` و برای ایجاد ابجکت متخصص (که اینجا نجار هست) از `Carpenter` استفاده کنه.

این موضوع برای درب آهنی و ... هم بطور مشابه پیاده‌سازی میشه.

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

**همونطور که میبیند، می‌تونیم بطور مشابه با هر دو نوع درب برخورد کنیم و ازین موضوع مطمئن باشیم که متخصص اشتباه برای یک
درب
انتخاب نمی‌کنیم.**

<br>

**چه موقع باید ازش استفاده کنیم؟**

زمانی که وابستگی‌های منطقی نه چندان ساده برای ایجاد وجود داره، میتونیم ازین دیزاین پترن استفاده کنیم.

</details>

<details>
<summary>Typescript</summary>

<div dir="ltr">

```typescript
class Door {
  getDescription(): void {}
}

class WoodenDoor extends Door {
  getDescription(): void {
    console.log("I am a wooden door");
  }
}

class IronDoor extends Door {
  getDescription(): void {
    console.log("I am an iron door");
  }
}

class DoorFittingExpert {
  getDescription(): void {}
}

class Welder extends DoorFittingExpert {
  getDescription(): void {
    console.log("I can only fit iron doors");
  }
}

class Carpenter extends DoorFittingExpert {
  getDescription(): void {
    console.log("I can only fit wooden doors");
  }
}

class DoorFactory {
  makeDoor(): Door {
    return null;
  }

  makeFittingExpert(): DoorFittingExpert {
    return null;
  }
}

class WoodenDoorFactory extends DoorFactory {
  makeDoor(): WoodenDoor {
    return new WoodenDoor();
  }

  makeFittingExpert(): Carpenter {
    return new Carpenter();
  }
}

class IronDoorFactory extends DoorFactory {
  makeDoor(): IronDoor {
    return new IronDoor();
  }

  makeFittingExpert(): Welder {
    return new Welder();
  }
}

let woodenFactory = new WoodenDoorFactory();

let door = woodenFactory.makeDoor();
let expert = woodenFactory.makeFittingExpert();

door.getDescription();
expert.getDescription();

-----------------------------------------------

let ironFactory = new IronDoorFactory();

door = ironFactory.makeDoor();
expert = ironFactory.makeFittingExpert();

door.getDescription();
expert.getDescription();

```

</div>

</details>

<br>

<div align="center">

## 👷 Builder

</div>

یک مثال از دنیای واقعی:

> فرض کنید به یک رستوران رفتید و شما یک همبرگر معمولی سفارش می‌دید. این یک مثال از Simple Factory هست یعنی بدون اینکه
> سوال اضافه ای بپرسن اون رو براتون میارن. توی بعضی موارد پیش میاد که نیاز به یک سفارش سفارشی تر دارین. یعنی میخواین نوع
> نون رو مشخص کنید یا نوع سسی که براتون استفاده میکنن، توی این شرایط Builder به کمکمون میاد.

<br>

به زبون ساده:

> در واقع کار Builder اینه که توی ساخت ابجکت‌های پیچیده یا ابجکت‌هایی که نیاز به شخصی سازی زیادی دارن، بهمون کمک بکنه.
>
> در واقع روش کارش به این صورت هست که بجای اینکه تعداد زیادی پارامتر رو از ورودی تابع سازنده دریافت کنیم (`__init__`) ،
> اون دیتارو بصورت مرحله به مرحله دریافت کنیم.

برای همه ما پیش اومد که یک تابع سازنده به این شکل ببینیم:

<details>
<summary>🐍 Python</summary>
<div dir="ltr">
```python
def __init__(self, size, cheese=True, pepperoni=True, tomato=False, lettuce=True)
```
</div>
</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
constructor(size: any, cheese: boolean = true, pepperoni: boolean = true, tomato: boolean = false, lettuce: boolean = true) {}

```

</div>
</details>

در این شرایط معمولا Builder میتونه به دادمون برسه.

<br>

ویکی پدیا:

<div dir="ltr">

> The builder pattern is an object creation software design pattern with the intentions of finding a solution to the
> telescoping constructor anti-pattern.

</div>

<br>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

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

همونطور که قبل تر اشاره کردم این دیزاین پترن رو معمولا برای ساخت ابجکت‌های پیچیده یا ابجکت‌هایی که نیاز به شخصی سازی
زیادی دارن استفاده میکنیم.

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
class Burger {
  private size: any;

  private cheese: boolean = false;
  private pepperoni: boolean = false;
  private lettuce: boolean = false;
  private tomato: boolean = false;

  constructor(builder: any) {
    this.size = builder.size;
    this.cheese = builder.cheese;
    this.pepperoni = builder.pepperoni;
    this.lettuce = builder.lettuce;
    this.tomato = builder.tomato;
  }
}

class BurgerBuilder {
  size: number;

  cheese: boolean = false;
  pepperoni: boolean = false;
  lettuce: boolean = false;
  tomato: boolean = false;

  constructor(size: number) {
    this.size = size;
  }

  addPepperoni() {
    this.pepperoni = true;
    return this;
  }

  addLettuce() {
    this.lettuce = true;
    return this;
  }

  addCheese() {
    this.cheese = true;
    return this;
  }

  addTomato() {
    this.tomato = true;
    return this;
  }

  build(): Burger {
    return new Burger(this);
  }
}

let burger = new BurgerBuilder(10)
  .addPepperoni()
  .addLettuce()
  .addTomato()
  .build();

console.log(Object.keys(burger));
```

</div>
</details>

<br>

<div align="center">

## 🐑 Prototype

</div>

یک مثال از دنیای واقعی:

> چیزی درمورد دالی شنیدین
>
> ؟ ([اگه نه اینجارو بخونید](<https://fa.wikipedia.org/wiki/%D8%AF%D8%A7%D9%84%DB%8C_(%DA%AF%D9%88%D8%B3%D9%81%D9%86%D8%AF)>))
>
> خیلی اینجا توضیح نمیدم، فقط بدونید همه‌چیز مربوط به شبیه سازیه!

به زبون ساده:

> مشکل از اینجا شروع میشه که یک ابجکت دارید و نیاز دارید از اون یک کپی ایجاد کنین. چطوری این کار رو میکنین؟ اول باید یک
> ابجکت جدید از همون کلاس ایجاد کنین بعد باید مقادیر ابجکت اصلی رو در ابجکت جدید کپی کنید. حالا از همین پروسه طاقت فرسا
> که
> بگذریم، این مشکل وجود داره این هست که به متغیر‌های خصوصی دسترسی ندارید.
>
> دیزاین پترن Prototype میگه یک Interface مشترک داشته باشید که وظیفه‌ش ساخت یک ابجکت کپی از روی ابجکت فعلی باشه.

ویکی پدیا:

<div dir="ltr">

> The prototype pattern is a creational design pattern in software development. It is used when the type of objects to
> create is determined by a prototypical instance, which is cloned to produce new objects.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

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

پایتون magic method‌هایی برای این مساله در نظر گرفته که ماهم از همون دو تابع معروف copy و deep copy استفاده میکنیم:

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

**تفاوت Shadow Copy و Deep Copy ؟**
<br>
توی Shadow Copy، یک متغیر ساخته می‌شود و به مکانی توی حافظه، که مقدار متغیر قبلی توش قرار گرفته، اشاره می‌کنه. پس اگر
شما مقدار
متغیر اول رو تغییر بدین، متغیر دوم هم تغییر می‌کنه. و همین‌طور اگر مقدار متغیر دوم رو تغییر بدین، مقدار متغیر اول هم
تغییر می‌کنه.

ولی توی deep copy، یک متغیر ساخته می‌شه و مقدار متغیر قبلی توی اون کپی می‌شه. در نتیجه تغییر ابجکت اول یا ابجکت کپی
تغییری توی اون یکی به وجود نمیاره.

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
class SomeComponent {
  someInt: number;
  someListOfObjects: any[];
  someCircularRef: any;

  constructor(someInt: number, someListOfObjects: any[], someCircularRef: any) {
    this.someInt = someInt;
    this.someListOfObjects = someListOfObjects;
    this.someCircularRef = someCircularRef;
  }

  copy() {
    let some_list_of_objects = Object.assign([], this.some_list_of_objects);
    let some_circular_ref = Object.assign({}, this.some_circular_ref);
    let new = new this.constructor(
    this.some_int, some_list_of_objects, some_circular_ref
    );
    Object.assign(new, this);
    return new;
  }

  deepcopy(memo: object = {}) {
    let some_list_of_objects = JSON.parse(JSON.stringify(this.some_list_of_objects));
    let some_circular_ref = JSON.parse(JSON.stringify(this.some_circular_ref));
    let new = new this.constructor(
    this.some_int, some_list_of_objects, some_circular_ref
    );
    new = JSON.parse(JSON.stringify(this));
    return new;
  }
}
```

</div>
</details>

<br>

<div align="center">

## 💍 Singleton

</div>

یک مثال از دنیای واقعی:

> در هر زمان فقط یک رئیس جمهور میتونه برای کشور وجود داشته باشه. در نتیجه هرجا به رئیس جمهور نیاز هست باید خودش وارد عمل
> بشه. رئیس جمهور توی این مثال singleton هست.

به زبون ساده:

> این دیزاین پترن تضمین می‌کنه از یک کلاس خاص فقط یک ابجکت وجود داشته باشه.

ویکی پدیا:

<div dir="ltr">

> In software engineering, the singleton pattern is a software design pattern that restricts the instantiation of a
> class to one object. This is useful when exactly one object is needed to coordinate actions across the system.

</div>
⚠️ دیزاین پترن singleton در واقع یک آنتی پترن شناخته می‌شه و باید از استفاده زیاد اون جلوگیری کنیم. لزوما بد نیست و میتونه کاربرد‌های خوبی داشته باشه ولی باید با احتیاط ازش استفاده کرد چون تغییر توی هر بخش برنامه، میتونه روی بخش‌های دیگه هم تاثیر بزاره که ابن خودش دیباگ کردن پروژه‌هارو خیلی سخت می‌کنه.

<br>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

بطور کلی برای ساخت singleton باید تابع سازنده private بشه، cloning و متود‌های copy بسته بشن و تابع استاتیکی برای ساخت
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
        pass


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
این روش Thread Safe نیست. برای اطلاعات بیشتر سرچ کنید :)

<br>
<br>

---

<br>

<div align="center">

# Structural Design Patterns

</div>

به زبون ساده:

> بطور کلی الگو‌های طراحی ساختاری با روابط بین موجودیت‌ها و ترکیب کردن اونا کار دارن.

ویکی پدیا:

<div dir="ltr">

> In software engineering, structural design patterns are design patterns that ease the design by identifying a simple
> way to realize relationships between entities.

</div>

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
class SingletonMeta extends Function {
  static _instances: { [key: string]: any } = {};

  constructor(...args: any[]) {
    const instance = super(...args);
    const className = this.constructor.name;
    if (!SingletonMeta._instances[className]) {
      SingletonMeta._instances[className] = instance;
    }
    return SingletonMeta._instances[className];
  }
}

class Singleton extends SingletonMeta {
  someBusinessLogic() {
    // implementation
  }
}

const s1 = Singleton.getInstance();
const s2 = Singleton.getInstance();
if (Object.is(s1, s2)) {
  console.log("Singleton works, both variables contain the same instance.");
} else {
  console.log("Singleton failed, variables contain different instances.");
}
```

</div>

</details>
<br>

<div align="center">

## 🔌 Adapter

</div>

یک مثال از دنیای واقعی:

> واضح ترین مثال برای این الگوی طراحی خوده آداپتور‌ها هستن. (برای مثال، آداپتور‌های شارژر که سه شاخه رو به دو شاخه تبدیل
> میکنن)
>
> **یا**
>
> مترجمی که کلمات یک نفر رو برای فرد دیگه ترجمه میکنه.

به زبون ساده:

> آداپتور بهتون کمک میکنه تا یک شی ناسازگار رو سازگار کنین تا بتونین توی کلاس‌های مختلف ازش استفاده کنین.

ویکی پدیا:

<div dir="ltr">

> In software engineering, the adapter pattern is a software design pattern that allows the interface of an existing
> class to be used as another interface. It is often used to make existing classes work with others without modifying
> their source code.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

فرض کنید یک شکارچی به شیر‌ها حمله میکنه و اون‌ها غرش میکنن.

خب اول باید یک اینترفیس `lion` بسازیم که شیر‌های مختلف ازش استفاده کنن:

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

خب حالا شکارچی وقتی شکار انجام بده اون شیر غرش انجام میده:

<div dir="ltr">

```python
class Hunter:
    def hunt(self, lion):
        lion.roar()
```

</div>

حالا فرض کنید یک موجودیت جدید مثل `سگ وحشی` به برنامه اضافه شده.

خب سگ غرش انجام نمیده بجای اون `bark` انجام میده.

خب اینجا `سگ وحشی` با تابع `hunt` شکارچی ناسازگار میشه. (چون در زمان شکار تابع roar رو صدا میزنیم و سگ شکاری این تابع رو
نداره!)

برای حلش به این صورت میتونیم براش آداپتور تعریف کنیم:

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
wildDog = WildDog()
wildDogAdapter = WildDogAdapter(wildDog)

hunter = Hunter()
hunter.hunt(wildDogAdapter)
```

</div>
در واقع مثال واقعی و قابل حس نیست ولی مفهوم رو به خوبی منتقل می‌کنه.

<br>
<br>

پیشنهاد میکنم برای درک بهتر این الگو، یک آداپتور برای این سناریو پیاده‌سازی کنید:

کلاس اول شما خروجی excel میده ولی کلاس دوم ورودیش csv هست.

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
class Lion {
  roar(): void {}
}

class AfricanLion extends Lion {
  roar(): void {}
}

class AsianLion extends Lion {
  roar(): void {}
}

class Hunter {
  hunt(lion: Lion): void {
    lion.roar();
  }
}

class WildDog {
  static bark(): void {}
}

class WildDogAdapter implements Lion {
  private dog: WildDog;

  constructor(dog: WildDog) {
    this.dog = dog;
  }

  roar(): void {
    this.dog.bark();
  }
}

const wildDog = new WildDog();
const wildDogAdapter = new WildDogAdapter(wildDog);

const hunter = new Hunter();
hunter.hunt(wildDogAdapter);
```

</div>
</details>
<br>
<br>

<div align="center">

## 🌉 Bridge

</div>

یک مثال از دنیای واقعی:

> فرض کنید یک وبسایت دارید و می‌خواید با توجه به تنظیمات کاربر از قالب‌های مختلف پشتیبانی کنید.
>
> برای انجام این کار چطور عمل می‌کنین؟
>
> به ازای هر قالب یک کپی از وبسایت ایجاد میکنید و قالب مخصوص براش اضافه میکنید؟
>
> یا قالب‌های مختلفی ایجاد میکنید با توجه به تنظیمات کاربر اون‌ها رو بارگذاری میکنید؟
>
> الگوی طراحی Bridge به شما کمک میکنه راه حل دوم رو پیاده‌سازی کنید.

![With and without the bridge pattern](https://cloud.githubusercontent.com/assets/11269635/23065293/33b7aea0-f515-11e6-983f-98823c9845ee.png)

به زبون ساده:

> این الگوی طراحی درمورد **ترجیح دادن** `ترکیب` **نسبت به** `ارث‌بری` صحبت میکنه.

ویکی پدیا:

<div dir="ltr">

> The bridge pattern is a design pattern used in software engineering that is meant to "decouple an abstraction from its
> implementation so that the two can vary independently"

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

بیاید همون مثال سایت و قالب که بالاتر درموردش صحبت کردیم رو پیاده‌سازی کنیم.

در مرحله اول کلاس `WebPage` و پیاده‌سازی‌هایی از اون رو داریم:

<div dir="ltr">

```python
class WebPage:
    _theme = None

    def __init__(self, theme):
        self.theme = theme

    def getContent(self):
        pass


class About(WebPage):
    def getContent(self):
        return "About page in " + self.theme.getColor()


class Careers(WebPage):
    def getContent(self):
        return "Careers page in " + self.theme.getColor()
```

</div>

برای قالب هم، باید کلاس و پیاده سازی‌های مختلفی بنویسیم:

<div dir="ltr">

```python
class Theme:
    def getColor(self):
        pass


class DarkTheme(Theme):
    def getColor(self):
        return 'Dark Black'


class LightTheme(Theme):
    def getColor(self):
        return 'Off White'


class AquaTheme(Theme):
    def getColor(self):
        return 'Light Blue'
```

</div>

حالا میتونید نحوه ترکیب کردن این دو تاروو باهم ببینید:

<div dir="ltr">

```python
darkTheme = DarkTheme()

about = About(darkTheme)
careers = Careers(darkTheme)

print(about.getContent())
print(careers.getContent())
```

</div>

</details>

<details>
<summary>Typescript</summary>
div dir="ltr">

```typescript
class WebPage {
  protected _theme: any;

  constructor(theme: any) {
    this._theme = theme;
  }

  getContent(): string {
    return "";
  }
}

class About extends WebPage {
  getContent(): string {
    return "About page in " + this._theme.getColor();
  }
}

class Careers extends WebPage {
  getContent(): string {
    return "Careers page in " + this._theme.getColor();
  }
}

class Theme {
  getColor(): string {
    return "";
  }
}

class DarkTheme extends Theme {
  getColor(): string {
    return "Dark Black";
  }
}

class LightTheme extends Theme {
  getColor(): string {
    return "Off White";
  }
}

class AquaTheme extends Theme {
  getColor(): string {
    return "Light Blue";
  }
}

const darkTheme = new DarkTheme();

const about = new About(darkTheme);
const careers = new Careers(darkTheme);

console.log(about.getContent());
console.log(careers.getContent());
```

</div>

</details>

<br>

<div align="center">

## 🌿 Composite

</div>

یک مثال از دنیای واقعی:

> فرض کنید شما یک کلاس ارسال مرسوله طراحی میکنید:
> <br> > ![](https://refactoring.guru/images/patterns/diagrams/composite/problem-en.png)
>
> هر کلاس یک جعبه هست که میتونه شامل چند جعبه دیگه یا شامل چند شیء باشه.
>
> برای ثبت یا محاسبه قیمت چطور عمل میکنید؟
>
> در هر جعبه رو باز میکنید و اشیای توش رو بررسی میکنید؟
>
> این قضیه توی دنیای واقعی شاید قابل انجام باشه ولی توی دنیای برنامه نویسی یا نشدنیه یا خیلی طاقت‌فرسا

به زبون ساده:

> در واقع این دیزاین پترن این امکان رو بهتون میده که ساختار‌های درختی بسازید و سپس با این ساختار‌ها طوری کار کنید که
> انگار با یک ابجکت منفرد کار کردید.

ویکی پدیا:

<div dir="ltr">

> In software engineering, the composite pattern is a partitioning design pattern. The composite pattern describes that
> a group of objects is to be treated in the same way as a single instance of an object. The intent of a composite is
> to "
> compose" objects into tree structures to represent part-whole hierarchies. Implementing the composite pattern lets
> clients treat individual objects and compositions uniformly.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

بطور کلی توی دیزاین پترن composite ما دو مدل دیتا داریم:

یک: اینکه Composite که میتونه برای خودش زیرمجموعه داشته باشه. (هرچند خودش هم وظایفی داشته باشه)

دو: Leaf که در واقع زیر مجموعه نداره و فقط یک سری وظیفه داره.

خب اول بیایم یک اینترفیس پایه برای کامپوننت‌هامون بسازیم و در ادامه هم اینترفیس‌های Composite و Leaf رو بسازیم:

<div dir="ltr">

```python
class Component():
    def add(self, component: Component) -> None:
        pass

    def remove(self, component: Component) -> None:
        pass

    def operation(self) -> str:
        pass


class Leaf(Component):
    def operation(self) -> str:
        return "Leaf"


class Composite(Component):
    def __init__(self) -> None:
        self._children: List[Component] = []

    def add(self, component: Component) -> None:
        self._children.append(component)

    def remove(self, component: Component) -> None:
        self._children.remove(component)

    def operation(self) -> str:
        results = []
        for child in self._children:
            results.append(child.operation())
        return f"Branch({'+'.join(results)})"


```

</div>
استفاده ازش هم خیلی راحته:

<div dir="ltr">

```python
tree = Composite()

branch1 = Composite()
branch1.add(Leaf())
branch1.add(Leaf())

branch2 = Composite()
branch2.add(Leaf())

tree.add(branch1)
tree.add(branch2)

print(f"RESULT: {tree.operation()}", end="")
# RESULT: Branch(Branch(Leaf+Leaf)+Branch(Leaf))

```

</div>

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
interface Component {
  add(component: Component): void;
  remove(component: Component): void;
  operation(): string;
}

class Leaf implements Component {
  operation(): string {
    return "Leaf";
  }
}

class Composite implements Component {
  private children: Component[] = [];

  add(component: Component): void {
    this.children.push(component);
  }

  remove(component: Component): void {
    const index = this.children.indexOf(component);
    this.children.splice(index, 1);
  }

  operation(): string {
    const results: string[] = [];
    for (const child of this.children) {
      results.push(child.operation());
    }
    return `Branch(${results.join("+")})`;
  }
}

const tree = new Composite();

const branch1 = new Composite();
branch1.add(new Leaf());
branch1.add(new Leaf());

const branch2 = new Composite();
branch2.add(new Leaf());

tree.add(branch1);
tree.add(branch2);

console.log(`RESULT: ${tree.operation()}`);
// RESULT: Branch(Branch(Leaf+Leaf)+Branch(Leaf))
```

</div>
</details>
<br>

<div align="center">

## ☕ Decorator

</div>

یک مثال از دنیای واقعی:

> فرض کنید یک مغازه خدمات خودرویی دارید که خدمات متنوع ای ارائه می دهید. فاکتور نهایی رو چطور محاسبه می کنید؟ شما یک
> سرویس رو انتخاب می کنید و به صورت پویا قیمت خدمات ارائه شده رو به اون اضافه می کنید تا به هزینه نهایی برسید. در اینجا
> هر
> نوع خدمات یک دکوریتور است.

به زبون ساده:

> دکوریتور به ما کمک میکنه به یک ابجکت یک Behavior اضافه کنیم بدون اینکه اون ابجکت رو تغییر بدیم.
>
> مفهوم Behavior = رفتاری که یک شیء می‌تواند از خود بروز دهد.

ویکی پدیا:

<div dir="ltr">

> In object-oriented programming, the decorator pattern is a design pattern that allows behavior to be added to an
> individual object, either statically or dynamically, without affecting the behavior of other objects from the same
> class. The decorator pattern is often useful for adhering to the Single Responsibility Principle, as it allows
> functionality to be divided between classes with unique areas of concern.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

برای مثال قهوه را در نظر بگیرید. اول از همه ما یک قهوه ساده داریم که رابط قهوه را پیاده سازی می کند.

<div dir="ltr">

```python
class Coffee:
    def getCost(self):
        pass

    def getDescription(self):
        pass


class SimpleCoffee(Coffee):
    def getCost(self):
        return 10

    def getDescription(self):
        return 'Simple Coffee'
```

</div>

ما می‌خوایم کد رو توسعه‌پذیر کنیم تا در صورت نیاز، گزینه‌ها بتونند اون رو تغییر بدند.

پس بیاید چند دکوریتور براش بسازیم:

<div dir="ltr">

```python
class MilkCoffee(Coffee):
    _coffee = None

    def __init__(self, coffee):
        self._coffee = coffee

    def getCost(self):
        return self._coffee.getCost() + 2

    def getDescription(self):
        return self._coffee.getDescription() + ', milk'


class WhipCoffee(Coffee):
    _coffee = None

    def __init__(self, coffee):
        self._coffee = coffee

    def getCost(self):
        return self._coffee.getCost() + 5

    def getDescription(self):
        return self._coffee.getDescription() + ', whip'


class VanillaCoffee(Coffee):
    _coffee = None

    def __init__(self, coffee):
        self._coffee = coffee

    def getCost(self):
        return self._coffee.getCost() + 3

    def getDescription(self):
        return self._coffee.getDescription() + ', vanilla'
```

</div>

و حالا نحوه ساخت قهوه سفارشی:

<div dir="ltr">

```python
someCoffee = SimpleCoffee()
print(someCoffee.getCost())
print(someCoffee.getDescription())

someCoffee = MilkCoffee(someCoffee)
print(someCoffee.getCost())
print(someCoffee.getDescription())

someCoffee = VanillaCoffee(someCoffee)
print(someCoffee.getCost())
print(someCoffee.getDescription())

someCoffee = WhipCoffee(someCoffee)
print(someCoffee.getCost())
print(someCoffee.getDescription())
```

</div>
همونطور که میبینید خیلی ساده میتونیم هر ابجکت رو به عنوان ورودی تابع بعدی بدیم و اینطوری چندین مرحله افزودنی رو خیلی راحت به ابجکتمون اضافه کردیم!

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
class Coffee {
  getCost(): number {
    return;
  }
  getDescription(): string {
    return;
  }
}

class SimpleCoffee extends Coffee {
  getCost(): number {
    return 10;
  }
  getDescription(): string {
    return "Simple Coffee";
  }
}

class MilkCoffee extends Coffee {
  private coffee: Coffee;

  constructor(coffee: Coffee) {
    super();
    this.coffee = coffee;
  }

  getCost(): number {
    return this.coffee.getCost() + 2;
  }

  getDescription(): string {
    return this.coffee.getDescription() + ", milk";
  }
}

class WhipCoffee extends Coffee {
  private coffee: Coffee;
  constructor(coffee: Coffee) {
    super();
    this.coffee = coffee;
  }

  getCost(): number {
    return this.coffee.getCost() + 5;
  }

  getDescription(): string {
    return this.coffee.getDescription() + ", whip";
  }
}

class VanillaCoffee extends Coffee {
  private coffee: Coffee;
  constructor(coffee: Coffee) {
    super();
    this.coffee = coffee;
  }

  getCost(): number {
    return this.coffee.getCost() + 3;
  }

  getDescription(): string {
    return this.coffee.getDescription() + ", vanilla";
  }
}

let someCoffee = new SimpleCoffee();
console.log(someCoffee.getCost());
console.log(someCoffee.getDescription());

someCoffee = new MilkCoffee(someCoffee);
console.log(someCoffee.getCost());
console.log(someCoffee.getDescription());

someCoffee = new VanillaCoffee(someCoffee);
console.log(someCoffee.getCost());
console.log(someCoffee.getDescription());

someCoffee = new WhipCoffee(someCoffee);
console.log(someCoffee.getCost());
console.log(someCoffee.getDescription());
```

</div>
</details>

<br>

<div align="center">

## 📦 Facade

</div>

یک مثال از دنیای واقعی:

> اگه ازتون بپرسم چطور یک لپ تاپ رو روشن میکنید؟ جواب شما این هست که "دکمه پاور رو میزنم"
>
> خب این چیزیه که شما بهش باور دارین، ولی در واقع دارین از یک رابط کاربری ساده میخواید تا یک عمل پیچیده با مراحل زیاد رو
> انجام بده.

به زبون ساده:

> این دیزاین پترن یک رابط ساده برای یک سیستم پیچیده دراختیار ما میزاره.

ویکی پدیا:

<div dir="ltr">

> A facade is an object that provides a simplified interface to a larger body of code, such as a class library.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

بیاین همون مثال مربوط به کامپیوتر رو پیاده‌سازی کنیم!

اول باید کلاس کامپیوتر رو بسازیم:

<div dir="ltr">

```python
class Computer:
    def getElectricShock(self):
        print("Ouch!")

    def makeSound(self):
        print("Beep Beep!")

    def showLoadingScreen(self):
        print("Loading...")

    def bam(self):
        print("Ready to be used...")

    def closeEverything(self):
        print("Bup bup bup buzzz!")

    def sooth(self):
        print("Zzzzz")

    def pullCurrent(self):
        print("Haaah!")
```

</div>

کلاس Facade به این صورت پیاده‌سازی میشه که یک ابجکت رو به عنوان ورودی دریافت میکنه و با هر تابع خودش یک سری عملیات رو
روی اون ابجکت اعمال میکنه.

به نحوه پیاده‌سازی Facade برای کلاس کامپیوتر دقت کنین:

<div dir="ltr">

```python
class ComputerFacade:
    _computer = None

    def __init__(self, computer):
        self.computer = computer

    def turnOn(self):
        self.computer.getElectricShock()
        self.computer.makeSound()
        self.computer.showLoadingScreen()
        self.computer.bam()

    def turnOff(self):
        self.computer.closeEverything()
        self.computer.pullCurrent()
        self.computer.sooth()
```

</div>

نحوه استفاده از یک کلاس فساد هم به این صورته:

<div dir="ltr">

```python
computer = ComputerFacade(Computer())
computer.turnOn()
computer.turnOff()
```

</div>

</details>

<div dir="ltr">

```typescript
class Computer {
  getElectricShock() {
    console.log("Ouch!");
  }
  makeSound() {
    console.log("Beep Beep!");
  }

  showLoadingScreen() {
    console.log("Loading...");
  }

  bam() {
    console.log("Ready to be used...");
  }

  closeEverything() {
    console.log("Bup bup bup buzzz!");
  }

  sooth() {
    console.log("Zzzzz");
  }

  pullCurrent() {
    console.log("Haaah!");
  }
}

class ComputerFacade {
  private computer: Computer;
  constructor(computer: Computer) {
    this.computer = computer;
  }

  set computer(computer: Computer) {
    this.computer = computer;
  }

  turnOn() {
    this.computer.getElectricShock();
    this.computer.makeSound();
    this.computer.showLoadingScreen();
    this.computer.bam();
  }

  turnOff() {
    this.computer.closeEverything();
    this.computer.pullCurrent();
    this.computer.sooth();
  }
}

let computer = new ComputerFacade(new Computer());
computer.turnOn();
computer.turnOff();
```

</div>

<br>

<div align="center">

## 🍃 Flyweight

</div>

یک مثال از دنیای واقعی:

> تا حالا به غرفه‌های چای فروشی رفتین؟ توی این غرفه‌ها چند فنجان چای آماده میکنن و شما از هر مدل چای که بخواید براتون یک
> فنجون میریزن. با اینکار کلی توی زمان و انرژی و ... صرفه جویی میکنن. بطور خلاصه این الگوی طراحی در رابطه با اشتراک
> گذاری
> منابع هست.

به زبون ساده:

> در واقع کار این دیزاین پترن این هست که با اشتراک گذاری بخش‌های مشترک شیء‌ها، استفاد از حافظه و هزینه‌های محاسباتی رو
> بهینه کنه.

ویکی پدیا:

<div dir="ltr">

> In computer programming, flyweight is a software design pattern. A flyweight is an object that minimizes memory use by
> sharing as much data as possible with other similar objects; it is a way to use objects in large numbers when a simple
> repeated representation would use an unacceptable amount of memory.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

بیاین مثال غرفه چای رو پیاده سازی کنیم. اول باید انواع چای رو پیاده سازی کنیم و بعدش چای ساز:

<div dir="ltr">

```python
class GreenTea:
    pass


class TeaMaker:
    _availableTea = {}

    def make(self, preference):
        if not preference in self._availableTea:
            self._availableTea[preference] = GreenTea()

        return self._availableTea[preference]
```

</div>

توی مرحله بعد ما یک کلاس `TeaShop` داریم که وظیفه ثبت سفارش و آماده کردن اون‌هارو به عهده داره:

<div dir="ltr">

```python
class TeaShop:
    _orders = {}
    _teaMaker = None

    def __init__(self, teaMaker):
        self._teaMaker = teaMaker

    def takeOrder(self, teaType, table):
        self._orders[table] = self._teaMaker.make(teaType)

    def serve(self):
        for table, tea in self._orders.iteritems():
            print("Serving tea to table #" + str(table))
```

</div>

روش استفاده ازش هم به این صورت هست:

<div dir="ltr">

```python
teaMaker = TeaMaker()
shop = TeaShop(teaMaker)

shop.takeOrder('less sugar', 1)
shop.takeOrder('more milk', 2)
shop.takeOrder('without sugar', 5)

shop.serve()
# Serving tea to table# 1
# Serving tea to table# 2
# Serving tea to table# 5
```

</div>

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
class GreenTea {}

class TeaMaker {
  private availableTea: { [key: string]: GreenTea } = {};
  make(preference: string): GreenTea {
    if (!(preference in this.availableTea)) {
      this.availableTea[preference] = new GreenTea();
    }

    return this.availableTea[preference];
  }
}

class TeaShop {
  private orders: { [key: number]: GreenTea } = {};
  private teaMaker: TeaMaker;
  constructor(teaMaker: TeaMaker) {
    this.teaMaker = teaMaker;
  }

  takeOrder(teaType: string, table: number) {
    this.orders[table] = this.teaMaker.make(teaType);
  }

  serve() {
    for (const table in this.orders) {
      const tea = this.orders[table];
      console.log(`Serving tea to table #${table}`);
    }
  }
}

let teaMaker = new TeaMaker();
let shop = new TeaShop(teaMaker);

shop.takeOrder("less sugar", 1);
shop.takeOrder("more milk", 2);
shop.takeOrder("without sugar", 5);

shop.serve();
// Serving tea to table# 1
// Serving tea to table# 2
// Serving tea to table# 5
```

</div>

</details>

<br>

<div align="center">

## 🎱 Proxy

</div>

یک مثال از دنیای واقعی:

> درب‌هایی که با کارت باز میشن رو دیدین؟ یا درب‌هایی که با رمز عددی باز میشن؟ در واقع این دو روش به عملکرد اصلی درب
> اضافه شدن تا کار مارو راحت تر کنن.

به زبون ساده:

> هدف اصلی Proxy راحت تر کردن استفاده از کلاس یا دسترسی کنترل‌شده هست.

ویکی پدیا:

<div dir="ltr">

> A proxy, in its most general form, is a class functioning as an interface to something else. A proxy is a wrapper or
> agent object that is being called by the client to access the real serving object behind the scenes. Use of the proxy
> can simply be forwarding to the real object, or can provide additional logic. In the proxy extra functionality can be
> provided, for example caching when operations on the real object are resource intensive, or checking preconditions
> before operations on the real object are invoked.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

خب بیاید مثال درب رو پیاده سازی کنیم.

اول اینترفیس درب رو میسازیم و بعدش یک مدل درب پیاده سازی میکنیم:

<div dir="ltr">

```python
class Door:
    def open(self):
        pass

    def close(self):
        pass


class LabDoor(Door):
    def open(self):
        print("Opening lab door")

    def close(self):
        print("Closing the lab door")
```

</div>

حالا ما میخوایم یک پروکسی برای اضافه کردن امنیت به درب بسازیم:

<div dir="ltr">

```python
class SecuredDoor():
    _door = None

    def __init__(self, door):
        self.door = door

    def open(self, password):
        if self.authenticate(password):
            self.door.open()
        else:
            print("Big no! It ain't possible.")

    def authenticate(self, password):
        return password == '$ecr@t'

    def close(self):
        self.door.close()
```

</div>

نحوه استفاده از اون هم به این صورته :

<div dir="ltr">

```python
door = SecuredDoor(LabDoor())
door.open('invalid')  # Big no! It ain't possible

door.open('$ecr@t')  # Opening lab door
door.close()  # Closing Lab Door
```

</div>

<br>
<br>

---

<br>

<div align="center">

# Behavioral Design Patterns

</div>

به زبون ساده:

> این الگوها به شما اجازه میدهند که رفتار کلاس‌ها رو تغییر بدین و یا اینکه این رفتار رو به کلاس‌های دیگه اضافه کنین.

ویکی پدیا:

<div dir="ltr">

> In software engineering, behavioral design patterns are design patterns that identify common communication patterns
> among objects. By doing so, these patterns increase flexibility in carrying out communication.

</div>

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
class Door {
  open(): void {}
  close(): void {}
}

class LabDoor extends Door {
  open(): void {
    console.log("Opening lab door");
  }
  close(): void {
    console.log("Closing the lab door");
  }
}

class SecuredDoor {
  private door: Door;
  constructor(door: Door) {
    this.door = door;
  }

  open(password: string): void {
    if (this.authenticate(password)) {
      this.door.open();
    } else {
      console.log("Big no! It ain't possible.");
    }
  }

  authenticate(password: string): boolean {
    return password === "$ecr@t";
  }

  close(): void {
    this.door.close();
  }
}

const door = new SecuredDoor(new LabDoor());
door.open("invalid"); // Big no! It ain't possible
door.open("$ecr@t"); // Opening lab door
door.close(); // Closing Lab Door
```

</div>

</details>

<br>

<div align="center">

## 🔗 Chain of Responsibility

</div>

یک مثال از دنیای واقعی:

> یکی از مثال‌های خوب این الگو، یک سیستم پشتیبانی هست. اگر یک کاربر یک مشکل داشته باشه، اون مشکل به یکی از مراحل
> پشتیبانی ارسال میشه. اگر مشکل در این مرحله حل نشد، مشکل به مرحله بعدی ارسال میشه و این کار تا زمانی که مشکل حل نشد
> ادامه
> پیدا میکنه.
>
> مثال دیگه ای که میشه زد اینه که شما سه تا حساب دارید که اولی ۱۰۰ تومن پول داره دومی ۳۰۰ و سومی ۱۰۰۰، حالا میخواید یک
> جنس که ۲۱۰ تومن قیمت داره رو بخرید، خب اول سعی میشه از حساب اول خرید بشه وقتی موجودی نداشت، با حساب دوم تلاش میشه و
> پرداخت انجام میشه!

به زبون ساده:

> به زبون ساده این الگو سعی میکنه در یک مسیر سعی در انجام یک کار داشته باشه و اگر اون کار در مرحله اول انجام نشد، اون
> کار رو به مرحله بعدی انتقال بده.

ویکی پدیا:

<div dir="ltr">

> In object-oriented design, the chain-of-responsibility pattern is a design pattern consisting of a source of command
> objects and a series of processing objects. Each processing object contains logic that defines the types of command
> objects that it can handle; the rest are passed to the next processing object in the chain.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

میخوایم همون مثال پرداخت رو باهم پیاده سازی کنیم:

<div dir="ltr">

```python
import inspect


class Account:
    _successor = None
    _balance = None

    def setNext(self, account):
        self._successor = account

    def pay(self, amountToPay):
        import inspect
        myCaller = inspect.stack()[1][3]
        if self.canPay(amountToPay):
            print
            "Paid " + str(amountToPay) + " using " + myCaller
        elif (self._successor):
            print
            "Cannot pay using " + myCaller + ". Proceeding .."
            self._successor.pay(amountToPay)
        else:
            raise ValueError('None of the accounts have enough balance')

    def canPay(self, amount):
        return self.balance >= amount


class Bank(Account):
    _balance = None

    def __init__(self, balance):
        self.balance = balance


class Paypal(Account):
    _balance = None

    def __init__(self, balance):
        self.balance = balance


class Bitcoin(Account):
    _balance = None

    def __init__(self, balance):
        self.balance = balance
```

</div>

خب توی کد بالا یک کلاس مرجع ساختیم که اسمش Account هست. این کلاس یک متد داره که اسمش pay هست. این متد یک مقدار رو میگیره
و سعی میکنه اون مقدار رو از حساب خود پرداخت کنه. اگر موفق نشد، اون مقدار رو به حساب بعدی انتقال میده.

تابع inspect.stack یک تابعیه که میتونه اطلاعاتی از فراخوانی تابع رو برگردونه. مثلا اگر ما از این تابع در یک تابع دیگه
استفاده کنیم، این تابع میتونه اسم تابعی که از اون استفاده شده رو برگردونه.

خب حالا میخوایم یک حساب بانکی، یک حساب پی پال و یک حساب بیت کوین بسازیم:

<div dir="ltr">

```python
bank = Bank(100)  # Bank with balance 100
paypal = Paypal(200)  # Paypal with balance 200
bitcoin = Bitcoin(300)  # Bitcoin with balance 300

bank.setNext(paypal)
paypal.setNext(bitcoin)

bank.pay(259)

'''
Output will be
==============
Cannot pay using bank. Proceeding ..
Cannot pay using paypal. Proceeding ..:
Paid 259 using Bitcoin!
'''
```

</div>

همونطور که میبینید اومدیم و بعد از ساختن این حساب‌ها اونارو به هم متصل کردیم!

سیستم اول سعی کرده با حساب بانکی پرداخت کنه ولی موجودی کافی نداشت، بعدش سعی کرده با حساب پی پال پرداخت کنه ولی موجودی
کافی نداشت، و در نهایت با حساب بیت کوین پرداخت میکنه!

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
class Account {
    protected _successor: Account | null = null;
    protected _balance: number | null = null;

    setNext(account: Account): void {
        this._successor = account;
    }

    pay(amountToPay: number): void {
        const myCaller = (new Error().stack as string).split("at ")[2].split(" ")[0];
        if (this.canPay(amountToPay)) {
            console.log(‍‍`Paid ${amountToPay} using ${myCaller}`);
        } else if (this._successor) {
            console.log(`Cannot pay using ${myCaller}. Proceeding ..`);
            this._successor.pay(amountToPay);
        } else {
            throw new Error("None of the accounts have enough balance");
        }
    }

    canPay(amount: number): boolean {
        return this._balance >= amount;
    }
}

class Bank extends Account {
    protected _balance: number | null = null;

    constructor(balance: number) {
        super();
        this._balance = balance;
    }
}

class Paypal extends Account {
    protected _balance: number | null = null;

    constructor(balance: number) {
        super();
        this._balance = balance;
    }
}

class Bitcoin extends Account {
    protected _balance: number | null = null;

    constructor(balance: number) {
        super();
        this._balance = balance;
    }
}

const bank = new Bank(100);
const paypal = new Paypal(200);
const bitcoin = new Bitcoin(300);

bank.setNext(paypal);
paypal.setNext(bitcoin);

bank.pay(259);

'''
Output will be
==============
Cannot pay using bank. Proceeding ..
Cannot pay using paypal. Proceeding ..:
Paid 259 using Bitcoin!
'''
```

</div>
</details>

<br>

<div align="center">

## 👮 Command

</div>

یک مثال از دنیای واقعی:

> فرض کنید توی یک رستوران یک غذا سفارش میدید! شما (client) از گارسون (Invoker) میخواید که براتون مقداری غذا
> بیاره (Command)! گارسون درخواست شمارو به آشپز میرسونه و آشپز اطلاعات و مهارت کافی برای اجرای درخواست شمارو داره!

به زبون ساده:

> ایده اصلی پشت این الگو اینه که مشتری رو از آشپز جدا کنه! یعنی Client یا درخواست کننده از Receiver یا همون اجراکننده
> کار جدا بشه.

ویکی پدیا:

<div dir="ltr">

> In object-oriented programming, the command pattern is a behavioral design pattern in which an object is used to
> encapsulate all information needed to perform an action or trigger an event at a later time. This information includes
> the method name, the object that owns the method and values for the method parameters.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

میخوایم یک کنترل برای لامپ درست کنیم (Receiver):

<div dir="ltr">

```python
class Bulb:
    def turnOn(self):
        print("Bulb has been lit")

    def turnOff(self):
        print("Darkness!")
```

</div>

اول باید یک ساختار برای دستورات درست کنیم (Command):

<div dir="ltr">

```python
class Command:
    _bulb = None

    def __init__(self, bulb):
        self._bulb = bulb

    def execute(self):
        pass


class TurnOn(Command):
    def execute(self):
        self._bulb.turnOn()


class TurnOff(Command):
    def execute(self):
        self._bulb.turnOff()
```

</div>

و در نهایت باید کنترل رو بسازیم که میتونه دستورات رو اجرا کنه! (Invoker)

<div dir="ltr">

```python
class RemoteControl:
    def submit(self, command):
        command.execute()
```

</div>

نحوه استفاده از این کنترل به این صورته:

<div dir="ltr">

```python
bulb = Bulb()

turnOn = TurnOn(bulb)
turnOff = TurnOff(bulb)

remote = RemoteControl()
remote.submit(turnOn)  # Bulb has been lit!
remote.submit(turnOff)  # Darkness!

```

</div>

توی این کد هم اول یک لامپ میسازیم و بعدش کامند‌های روشن کردن و خاموش کردن رو ایجاد میکنیم!

در نهایت وقتی نیاز به خاموش کردن یا روشن کردن داشته باشیم این کامند‌هارو به کنترلمون میفرستیم و اون اجراشون میکنه!

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
class Bulb {
  turnOn() {
    console.log("Bulb has been lit");
  }

  turnOff() {
    console.log("Darkness!");
  }
}

class Command {
  protected _bulb: Bulb | null = null;

  constructor(bulb: Bulb) {
    this._bulb = bulb;
  }

  execute(): void {}
}

class TurnOn extends Command {
  execute() {
    this._bulb!.turnOn();
  }
}

class TurnOff extends Command {
  execute() {
    this._bulb!.turnOff();
  }
}

class RemoteControl {
  submit(command: { execute: () => void }) {
    command.execute();
  }
}

const bulb = new Bulb();

const turnOn = new TurnOn(bulb);
const turnOff = new TurnOff(bulb);

const remote = new RemoteControl();
remote.submit(turnOn); // Bulb has been lit!
remote.submit(turnOff); // Darkness!
```

</div>
</details>

<br>

<div align="center">

## ➿ Iterator

</div>

یک مثال از دنیای واقعی:

> یک رادیو رو در نظر بگیرین که میتونین بین فرکانس‌های مختلفش جابجا بشین! در واقع این رادیو یک Iterator هستش!
>
> چون میتونین از یک فرکانس به فرکانس دیگه بروید و از اونجا به فرکانس دیگه و ... بدون اینکه درگیر فرکانس قبلی یا بعدی
> بشین!

به زبون ساده:

> دسترسی پی در پی به عناصر مختلف یک مجموعه هست بدون اینکه نیاز باشه به جزئیات بقیه عناصر نگاه کنیم!

ویکی پدیا:

<div dir="ltr">

> In object-oriented programming, the iterator pattern is a design pattern in which an iterator is used to traverse a
> container and access the container's elements. The iterator pattern decouples algorithms from containers; in some
> cases,
> algorithms are necessarily container-specific and thus cannot be decoupled.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

این مثال رو میخوایم یکم پایتونیک پیش بریم! میدونید که توی پایتون دو تا مفهوم Iterable و Iterator رو داریم پس میریم ازشون
استفاده کنیم!

<div dir="ltr">

```python
from __future__ import annotations
from collections.abc import Iterable, Iterator
from typing import Any, List


class AlphabeticalOrderIterator(Iterator):
    _position: int = None

    def __init__(self, collection: WordsCollection, reverse: bool = False) -> None:
        self._collection = collection
        self._reverse = reverse
        self._position = -1 if reverse else 0

    def __next__(self):
        try:
            value = self._collection[self._position]
            self._position += -1 if self._reverse else 1
        except IndexError:
            raise StopIteration()

        return value
```

</div>

این کلاس یک Iterator هستش که میتونه توی یک WordsCollection جابجا بشه و عناصرش رو برگردونه!

<div dir="ltr">

```python

class WordsCollection(Iterable):
    def __init__(self, collection: List[Any] = []) -> None:
        self._collection = collection

    def __iter__(self) -> AlphabeticalOrderIterator:
        return AlphabeticalOrderIterator(self._collection)

    def get_reverse_iterator(self) -> AlphabeticalOrderIterator:
        return AlphabeticalOrderIterator(self._collection, True)

    def add_item(self, item: Any) -> None:
        self._collection.append(item)
```

</div>

این کلاس یک Iterable هستش که میتونه توی یک WordsCollection جابجا بشه و عناصرش رو برگردونه!

<div dir="ltr">

```python

if __name__ == "__main__":
    collection = WordsCollection()
    collection.add_item("First")
    collection.add_item("Second")
    collection.add_item("Third")

    print("Straight traversal:")
    print("\n".join(collection))

    print("\n")
    print("Reverse traversal:")
    print("\n".join(collection.get_reverse_iterator()), end="")
```

</div>

توی این کد هم میتونید ببینید که چطوری میتونیم از Iterator‌ها استفاده کنیم!

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
interface Iterator<T> {
  next(): { value: T; done: boolean };
}

class AlphabeticalOrderIterator implements Iterator<string> {
  private position: number;

  constructor(private collection: WordsCollection, private reverse = false) {
    this.position = this.reverse ? -1 : 0;
  }

  next() {
    try {
      const value = this.collection.collection[this.position];
      this.position += this.reverse ? -1 : 1;
      return { value, done: false };
    } catch (error) {
      return { value: undefined, done: true };
    }
  }
}

class WordsCollection {
  collection: string[];

  constructor(collection: string[] = []) {
    this.collection = collection;
  }

  [Symbol.iterator]() {
    return new AlphabeticalOrderIterator(this);
  }

  getReverseIterator() {
    return new AlphabeticalOrderIterator(this, true);
  }

  addItem(item: string) {
    this.collection.push(item);
  }
}

const collection = new WordsCollection();
collection.addItem("First");
collection.addItem("Second");
collection.addItem("Third");

console.log("Straight traversal:");
for (const item of collection) {
  console.log(item);
}

console.log("\nReverse traversal:");
for (const item of collection.getReverseIterator()) {
  console.log(item);
}
```

</div>
</details>

<br>

<div align="center">

## 👽 Mediator

</div>

یک مثال از دنیای واقعی:

> وقتی دارین با یک نفر با کمک اینترنت چت میکنید، شبکه اینترنت بین شما و اون فرد قرار داره. این شبکه mediator هست!

به زبون ساده:

> این الگو یک ابجکت که ما mediator بهش میگیم بین دو ابجکت قرار میده که ارتباط بین این دو ابجکت (که بهشون colleagues
> میگیم) رو مدیریت میکنه! حالا چرا
> بهش نیاز داریم؟ چون در این صورت دیگه این دوتا نیاز نیست درمورد پیاده سازی طرف دیگه چیزی بدونن و این باعث کاهش coupling
> بین دو ابجکت میشه!

ویکی پدیا:

<div dir="ltr">

> In software engineering, the mediator pattern defines an object that encapsulates how a set of objects interact. This
> pattern is considered to be a behavioral pattern due to the way it can alter the program's running behavior.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

میخوایم یک ساختار چت روم بسازیم! (Mediator)

<div dir="ltr">

```python
class ChatRoomMediator:
    def showMessage(self, user, message):
        pass


class ChatRoom(ChatRoomMediator):
    def showMessage(self, user, message):
        time = datetime.datetime.now()
        sender = user.getName()

        print(str(time) + '[' + sender + ']: ' + message)
```

</div>

خب حالا بخش یوزر‌ها: (Colleagues)

<div dir="ltr">

```python
class User:
    _name = None
    _chatMediator = None

    def __init__(self, name, chatMediator):
        self.name = name
        self._chatMediator = chatMediator

    def getName(self):
        return self.name

    def send(self, message):
        self._chatMediator.showMessage(self, message)
```

</div>

نحوه استفاده ازشون هم به این صورته :

<div dir="ltr">

```python
mediator = ChatRoom()

john = User('John', mediator)
jane = User('Jane', mediator)

john.send('Hi There!')
jane.send('Hey!')
# Output will be
# Feb 14, 10:58 [John]: Hi there!
# Feb 14, 10:58 [Jane]: Hey!
```

</div>

به همین راحتی :)

</details>

<details>
<summary>Typescript</summary>

<div dir="ltr">

```typescript
class ChatRoomMediator {
  showMessage(user: User, message: string): void {}
}

class ChatRoom extends ChatRoomMediator {
  showMessage(user: User, message: string): void {
    let time = new Date();
    let sender = user.getName();

    console.log(`${time.toLocaleString()} [${sender}]: ${message}`);
  }
}

class User {
  private name: string;
  private chatMediator: ChatRoomMediator;

  constructor(name: string, chatMediator: ChatRoomMediator) {
    this.name = name;
    this.chatMediator = chatMediator;
  }

  getName(): string {
    return this.name;
  }

  send(message: string): void {
    this.chatMediator.showMessage(this, message);
  }
}

const mediator = new ChatRoom();

const john = new User("John", mediator);
const jane = new User("Jane", mediator);

john.send("Hi there!");
jane.send("Hey!");

// Output will be:
// Feb 14, 10:58 [John]: Hi there!
// Feb 14, 10:58 [Jane]: Hey!
```

</div>
</details>
<br>

<div align="center">

## 💾 Memento

</div>

یک مثال از دنیای واقعی:

> ماشین حساب‌های گوشی رو دیدید؟ وقتی محاسبه‌هاتون پیش میره، یک قسمت حافظه داره که محاسبه‌های قبلی رو بهتون نشون میده و
> هروقت بخواید میتونید مقدار فعلی رو برگردونید به محاسبه‌های قبلی!

به زبون ساده:

> به زبون ساده این الگو یک حافظه از حالت‌های قبلی داره که قابلیت برگشت بهشون وجود داره!

ویکی پدیا:

<div dir="ltr">

> The memento pattern is a software design pattern that provides the ability to restore an object to its previous
> state (undo via rollback).

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

میخوایم یک ادیتور متن بسازیم و قابلیت ذخیره کردن و بازگردانی بهش اضافه کنیم!

<div dir="ltr">

```python
class EditorMemento:
    _content = None

    def __init__(self, content):
        self._content = content

    def getContent(self):
        return self._content
```

</div>

خب اول یک کلاس به عنوان حافظه ادیتور میسازیم! مشخصه که وظیفه‌اش فقط نگهداری یک مقدار هست!

در ادامه یک کلاس ادیتور میسازیم که قابلیت تایپ کردن، خالی کردن، سیو و برگشت حافظه داره!

<div dir="ltr">

```python
class Editor:
    _content = ''

    def type(self, words):
        self._content = self._content + ' ' + words

    def getContent(self):
        return self._content

    def save(self):
        return EditorMemento(self._content)

    def restore(self, memento):
        self.content = memento.getContent()
```

</div>

و در مرحله آخر هم نحوه استفاده‌اش رو ببینید:

<div dir="ltr">

```python
editor = Editor()
editor.type('This is the first sentence')
editor.type('This is the second.')

saved = editor.save()
editor.type('And this is the third')

print(editor.getContent())  ## This is the first sentence. This is second. And this is third.

editor.restore(saved)
print(editor.getContent())  ## This is the first sentence. This is second.

```

</div>

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
class EditorMemento {
  private content: string | null = null;
  constructor(content: string) {
    this.content = content;
  }

  getContent(): string {
    return this.content;
  }
}

class Editor {
  private content = "";

  type(words: string): void {
    this.content = this.content + " " + words;
  }

  getContent(): string {
    return this.content;
  }

  save(): EditorMemento {
    return new EditorMemento(this.content);
  }

  restore(memento: EditorMemento): void {
    this.content = memento.getContent();
  }
}

const editor = new Editor();
editor.type("This is the first sentence");
editor.type("This is the second.");

const saved = editor.save();
editor.type("And this is the third");

console.log(editor.getContent()); // This is the first sentence. This is second. And this is third.

editor.restore(saved);
console.log(editor.getContent()); // This is the first sentence. This is second.
```

</div>
</details>

<br>

<div align="center">

## 😎 Observer

</div>

یک مثال از دنیای واقعی:

> یک سری سایت کاریابی وجود داره که شما میرید و مهارت‌هاتون رو به پروفایلتون اضافه میکنید تا هروقت شغل مناسبی براتون پیدا
> بشه، براتون ایمیل اطلاع رسانی ارسال میشه!

به زبون ساده:

> یک سری ارتباط بین ابجکت‌ها ایجاد میکنه و هروقت تغییر در وضعیت اونا رخ بده به ابجکت‌های وابسته‌شون اطلاع داده میشه!

ویکی پدیا:

<div dir="ltr">

> The observer pattern is a software design pattern in which an object, called the subject, maintains a list of its
> dependents, called observers, and notifies them automatically of any state changes, usually by calling one of their
> methods.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

در بخش اول یک کلاس برای ذخیره کردن یک شغل میسازیم و در بخش بعدی یک کلاس برای جویندگان کار میسازیم!

<div dir="ltr">

```python
class JobPost:
    _title = None

    def __init__(self, title):
        self.title = title

    def getTitle(self):
        return self.title


class JobSeeker:
    _name = None

    def __init__(self, name):
        self.name = name

    def onJobPosted(self, job):
        print('Hi ' + self.name + '! New job posted: ' + job.getTitle())

```

</div>

و حالا باید یک کلاس برای دسته بندی‌های مختلف کار ایجاد کنیم و جویندگان کار میتونن بهش اضافه بشن و اگه شغلی توی اون دسته
بندی ارسال بشه به اونا اطلاع رسانی میشه!

<div dir="ltr">

```python
class JobCategory:
    _observers = []

    def notify(self, jobPosting):
        for observer in self._observers:
            observer.onJobPosted(jobPosting)

    def attach(self, observer):
        self._observers.append(observer)

    def addJob(self, jobPosting):
        self.notify(jobPosting)
```

</div>

نحوه استفاده ازش رو ببینید:

<div dir="ltr">

```python

johnDoe = JobSeeker('John Doe')
janeDoe = JobSeeker('Jane Doe')

jobPostings = JobCategory()
jobPostings.attach(janeDoe)
jobPostings.attach(johnDoe)

jobPostings.addJob(JobPost('Software Engineer at XXX'))

# Output
# Hi John Doe! New job posted: Software Engineer
# Hi Jane Doe! New job posted: Software Engineer

```

</div>

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
class JobPost {
  private title: string | null = null;
  constructor(title: string) {
    this.title = title;
  }

  getTitle(): string {
    return this.title;
  }
}
class JobSeeker {
  private name: string | null = null;
  constructor(name: string) {
    this.name = name;
  }

  onJobPosted(job: JobPost): void {
    console.log(`Hi ${this.name}! New job posted: ${job.getTitle()}`);
  }
}

class JobCategory {
  private observers: JobSeeker[] = [];
  notify(jobPosting: JobPost): void {
    for (const observer of this.observers) {
      observer.onJobPosted(jobPosting);
    }
  }

  attach(observer: JobSeeker): void {
    this.observers.push(observer);
  }

  addJob(jobPosting: JobPost): void {
    this.notify(jobPosting);
  }
}

const johnDoe = new JobSeeker("John Doe");
const janeDoe = new JobSeeker("Jane Doe");

const jobPostings = new JobCategory();
jobPostings.attach(janeDoe);
jobPostings.attach(johnDoe);

jobPostings.addJob(new JobPost("Software Engineer at XXX"));

// Output
// Hi John Doe! New job posted: Software Engineer
// Hi Jane Doe! New job posted: Software Engineer
```

</div>
</details>

<br>

<div align="center">

## 🏃 Visitor

</div>

یک مثال از دنیای واقعی:

> شما یک وبسایت فروشگاهی دارید که دسته بندی‌های مختلفی دارید، این الگو به شما کمک میکنه درصد تخفیف متفاوتی روی دسته بندی
> ‌های مختلف اعمال کنید یا همینکار رو در زمینه دسترسی داشته باشید مثلا یک دسترسی ویژه برای دسته بندی وسایل اداری ایجاد
> کنید!

به زبون ساده:

> این الگو به شما این امکان میده که بدون نیاز به تغییر ابجکت‌ها عملیات بیشتری را بهشون اضافه کنید.
>
> اون ابجکت‌هایی که بهشون امکانات اضافه میشه، Visitee گفته میشن و اون کلاس‌هایی که ویژگی رو به ابجکت‌ها اضافه میکنن
> Visitor گفته میشن!

ویکی پدیا:

<div dir="ltr">

> In object-oriented programming and software engineering, the visitor design pattern is a way of separating an
> algorithm from an object structure on which it operates. A practical result of this separation is the ability to add
> new
> operations to existing object structures without modifying those structures. It is one way to follow the open/closed
> principle.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

فرض کنید یک باغ وحش مجازی داریم و میخوایم یک عالمه امکان رو به حیوون‌های مختلف اضافه کنیم! مثلا صداشون، نحوه پریدنشون و
...

خب بریم Visitee و Visitor برای این مثال بسازیم:

<div dir="ltr">

```python

# Visitee
class Animal:
    def accept(self, operation):
        pass


# Visitor
class AnimalOperation:
    def visitMonkey(self, monkey):
        pass

    def visitLion(self, lion):
        pass

    def visitDolphin(self, dolphin):
        pass

```

</div>

خب حالا حیوون‌هامون رو بسازیم و صداشون رو هم به کلاس خودشون اضافه کنیم:

<div dir="ltr">

```python

class Monkey(Animal):
    def shout(self):
        print('Ooh oo aa aa!')

    def accept(self, operation):
        operation.visitMonkey(self)


class Lion(Animal):
    def roar(self):
        print('Roaaar!')

    def accept(self, operation):
        operation.visitLion(self)


class Dolphin(Animal):
    def speak(self):
        print('Tuut tuttu tuutt!')

    def accept(self, operation):
        operation.visitDolphin(self)

```

</div>

حالا بیاید کلاس رو برای دیدن صداشون اضافه کنیم:

<div dir="ltr">

```python
class Speak(AnimalOperation):
    def visitMonkey(self, monkey):
        monkey.shout()

    def visitLion(self, lion):
        lion.roar()

    def visitDolphin(self, dolphin):
        dolphin.speak()
```

</div>

فراخوانیش رو ببینید:

<div dir="ltr">

```python
monkey = Monkey()
lion = Lion()
dolphin = Dolphin()

speak = Speak()
monkey.accept(speak)  # Ooh oo aa aa!
lion.accept(speak)  # Roaaar!
dolphin.accept(speak)  # Tuut tutt tuttt!
```

</div>

حالا اگه بخوایم قابلیت پریدن رو به حیوونا اضافه کنیم، کار خیلی راحته ببینید:

<div dir="ltr">

```python
class Jump(AnimalOperation):
    def visitMonkey(self, monkey):
        print('Jumped 20 feet high! on to the tree!')

    def visitLion(self, lion):
        print('Jumped 7 feet! back on the ground!')

    def visitDolphin(self, dolphin):
        print('Walked on water a little and disappeared')
```

</div>

حالا نحوه فراخوانیش رو در کنار صدای حیوونا ببینید:

<div dir="ltr">

```python
jump = Jump()

monkey.accept(speak)  # Ooh oo aa aa!
monkey.accept(jump)  # Jumped 20 feet high! on to the tree!

lion.accept(speak)  # Roaaar!
lion.accept(jump)  # Jumped 7 feet! Back on the ground!

dolphin.accept(speak)  # Tuut tutt tuutt!
dolphin.accept(jump)  # Walked on water a little and disappeared
```

</div>

یعنی بجای اینکه کلاس حیوونا رو تغییر بدیم کلاس‌های جداگانه ای برای صدا و پرش و ... میسازیم و به عنوان ورودی به حیوونا
میدیم :)

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
interface AnimalOperation {
  visitMonkey(monkey: Monkey): void;
  visitLion(lion: Lion): void;
  visitDolphin(dolphin: Dolphin): void;
}

interface Animal {
  accept(operation: AnimalOperation): void;
}

class Monkey implements Animal {
  shout() {
    console.log("Ooh oo aa aa!");
  }
  accept(operation: AnimalOperation): void {
    operation.visitMonkey(this);
  }
}

class Lion implements Animal {
  roar() {
    console.log("Roaaar!");
  }
  accept(operation: AnimalOperation): void {
    operation.visitLion(this);
  }
}

class Dolphin implements Animal {
  speak() {
    console.log("Tuut tuttu tuutt!");
  }
  accept(operation: AnimalOperation): void {
    operation.visitDolphin(this);
  }
}

class Speak extends AnimalOperation {
  visitMonkey(monkey: Monkey) {
    monkey.shout();
  }

  visitLion(lion: Lion) {
    lion.roar();
  }

  visitDolphin(dolphin: Dolphin) {
    dolphin.speak();
  }
}

const monkey = new Monkey();
const lion = new Lion();
const dolphin = new Dolphin();
const speak = new Speak();

monkey.accept(speak); // Ooh oo aa aa!
lion.accept(speak); // Roaaar!
dolphin.accept(speak); //Tuut tutt tuttt!

class Jump implements AnimalOperation {
  visitMonkey(monkey: Monkey): void {
    console.log("Jumped 20 feet high! on to the tree!");
  }

  visitLion(lion: Lion): void {
    console.log("Jumped 7 feet! back on the ground!");
  }

  visitDolphin(dolphin: Dolphin): void {
    console.log("Walked on water a little and disappeared");
  }
}

const jump = new Jump();

monkey.accept(speak); // Ooh oo aa aa!
monkey.accept(jump); // Jumped 20 feet high! on to the tree!

lion.accept(speak); // Roaaar!
lion.accept(jump); // Jumped 7 feet! Back on the ground!

dolphin.accept(speak); // Tuut tutt tuutt!
dolphin.accept(jump); // Walked on water a little and disappeared
```

</div>
</details>

<br>

<div align="center">

## 💡 Strategy

</div>

یک مثال از دنیای واقعی:

> فرض کنید که شما یک سرباز درحال جنگ هستید که چندین سلاح همراه خودتون دارید از جمله کلت، کلاش و نارنجک. حالا مشخصه که در
> شرایط مختلف با توجه به شرایط تصمیم میگیرید که یکی از اونا استفاده کنید! به این انتخاب‌های مختلف با توجه به شرایط
> استراتژی میگن!

به زبون ساده:

> این الگو به شما امکان میده الگوریتم یا استراتژی را بر اساس موقعیت تغییر بدین.

ویکی پدیا:

<div dir="ltr">

> In computer programming, the strategy pattern (also known as the policy pattern) is a behavioural software design
> pattern that enables an algorithm's behavior to be selected at runtime.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

میخوایم یک سرویس پیاده سازی کنیم که با توجه به داده‌هامون تصمیم بگیریم از یک نوع از مرتب سازی استفاده کنیم!

بخش اول پیاده سازی استراتژی‌هامون هست:

<div dir="ltr">

```python
class SortStrategy:
    def sort(self, dataset):
        pass


class BubbleSortStrategy(SortStrategy):
    def sort(self, dataset):
        print('Sorting using bubble sort')

        return dataset


class QuickSortStrategy(SortStrategy):
    def sort(self, dataset):
        print('Sorting using quick sort')
        return dataset
```

</div>

حالا باید یک کلاس بسازیم که وظیفه‌اش مدیریت این استراتژی‌ها باشه:

<div dir="ltr">

```python
class Sorter:
    _sorter = None

    def __init__(self, sorter):
        self._sorter = sorter

    def sort(self, dataset):
        return self._sorter.sort(dataset)
```

</div>

نحوه استفاده ازش هم خیلی راحته:

<div dir="ltr">

```python
dataset = [1, 5, 4, 3, 2, 8]

sorter = Sorter(BubbleSortStrategy())
sorter.sort(dataset)

sorter = Sorter(QuickSortStrategy())
sorter.sort(dataset)
```

</div>

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
interface SortStrategy {
  sort(dataset: any[]): any[];
}

class BubbleSortStrategy implements SortStrategy {
  sort(dataset: any[]): any[] {
    console.log("Sorting using bubble sort");
    return dataset;
  }
}

class QuickSortStrategy implements SortStrategy {
  sort(dataset: any[]): any[] {
    console.log("Sorting using quick sort");
    return dataset;
  }
}

class Sorter {
  private sorter: SortStrategy;

  constructor(sorter: SortStrategy) {
    this.sorter = sorter;
  }

  sort(dataset: any[]): any[] {
    return this.sorter.sort(dataset);
  }
}

const dataset = [1, 5, 4, 3, 2, 8];

const sorter = new Sorter(new BubbleSortStrategy());
sorter.sort(dataset);

const sorter2 = new Sorter(new QuickSortStrategy());
sorter2.sort(dataset);
```

</div>
</details>

<br>

<div align="center">

## 💢 State

</div>

یک مثال از دنیای واقعی:

> نرم افزار paint ویندوز رو یادتونه؟ میومدیم خودکار رو انتخاب میکردیم و شروع میکردیم به نقاشی کردن. بعد توی قسمت پالت
> رنگ قرمز کلیک میکردیم و بعدش خودکارمون قرمز میشد و میتونستیم ادامه بدیم! حتی میتونستیم خودکار رو به قلمو تغییر بدیم!
> این
> مفهوم به یاد داشتن حالت و ادامه کار مشابه الگوی State هست!

به زبون ساده:

> به شما اجازه میده یک سری ویژگی رو مشخص کنید و حالت‌شون رو به یاد داشته باشید!

ویکی پدیا:

<div dir="ltr">

> The state pattern is a behavioral software design pattern that implements a state machine in an object-oriented way.
> With the state pattern, a state machine is implemented by implementing each individual state as a derived class of the
> state pattern interface, and implementing state transitions by invoking methods defined by the pattern's superclass.
> The
> state pattern can be interpreted as a strategy pattern which is able to switch the current strategy through
> invocations
> of methods defined in the pattern's interface.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

میخوایم یک ادیتور بسازیم که قابلیت‌هایی مثل این داشته باشه که متنی که تایپ میشه حروف کوچیک باشه یا همش حروف بزرگ باشه یا
معمولی باشه!

اول بیاید کلاس‌هامون بر پایه الگوی State رو بسازیم:

<div dir="ltr">

```python
class WritingState:
    def write(self, words):
        pass


class UpperCase(WritingState):
    def write(self, words):
        print(words.upper())


class LowerCase(WritingState):
    def write(self, words):
        print(words.lower())


class DefaultText(WritingState):
    def write(self, words):
        print(words)
```

</div>

حالا ادیتور رو بسازیم و بهش یاد بدیم این کلاس‌ها رو توی خودش نگه داره و ازشون استفاده کنه!

<div dir="ltr">

```python
class TextEditor():
    _state = None

    def __init__(self, state):
        self._state = state

    def setState(self, state):
        self._state = state

    def type(self, words):
        self._state.write(words)
```

</div>

نحوه استفاده ازش هم به این صورته:

<div dir="ltr">

```python
editor = TextEditor(DefaultText())
editor.type('First Line')  # First line

editor.setState(UpperCase())

editor.type('Second Line')  # SECOND LINE

editor.type('Third Line')  # THIRD LINE

editor.setState(LowerCase())

editor.type('Fourth Line')  # fourth line

editor.type('Fifth Line')  # fifth line

```

</div>

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
interface WritingState {
  write(words: string): void;
}

class UpperCase implements WritingState {
  write(words: string): void {
    console.log(words.toUpperCase());
  }
}

class LowerCase implements WritingState {
  write(words: string): void {
    console.log(words.toLowerCase());
  }
}

class DefaultText implements WritingState {
  write(words: string): void {
    console.log(words);
  }
}

class TextEditor {
  private state: WritingState;

  constructor(state: WritingState) {
    this.state = state;
  }

  setState(state: WritingState) {
    this.state = state;
  }

  type(words: string) {
    this.state.write(words);
  }
}

const editor = new TextEditor(new DefaultText());
editor.type("First Line"); // First Line

editor.setState(new UpperCase());

editor.type("Second Line"); // SECOND LINE
editor.type("Third Line"); // THIRD LINE

editor.setState(new LowerCase());

editor.type("Fourth Line"); // fourth line
editor.type("Fifth Line"); // fifth line
```

</div>
</details>

<br>

<div align="center">

## 📒 Template Method

</div>

یک مثال از دنیای واقعی:

> فرض کنید قصد خونه سازی دارید! مراحلش به این صورته که اول باید زیربنا رو درست کنید بعد دیوار بسازید و بعد برید سراغ
> سقف! مشخصا شما نمیتونید اول سقف بزنید و بعد زیر بنا! پس این قضیه یک ترتیب داره که شما فقط میتونید مثلا جنس دیوار رو
> عوض
> کنید یا نحوه ساخت زیربنا رو عوض کنید ولی ترتیب و کلیت قضیه تغییر نمیکنه.

به زبون ساده:

> درواقع توی این الگو ما یک الگوریتم مشخص داریم که از قبل پیاده سازی شده و فقط میتونیم مراحل اون رو ما پیاده سازی کنیم
> یا تغییر بدیم!

ویکی پدیا:

<div dir="ltr">

> In software engineering, the template method pattern is a behavioral design pattern that defines the program skeleton
> of an algorithm in an operation, deferring some steps to subclasses. It lets one redefine certain steps of an
> algorithm
> without changing the algorithm's structure.

</div>

**مثال برنامه نویسی**

<details>
<summary>🐍 Python</summary>

فرض کنید ما یک زیرساخت برای ساخت اپلیکیشن‌های گوشی نیاز داریم!

خب مراحل تقریبا مشخصه و فقط ما باید مراحل build, lint , test و deploy رو پیاده سازی کنیم!

خب زیرساخت رو اینطوری میسازیم:

<div dir="ltr">

```python
class Builder:
    def build(self):
        self.test()
        self.lint()
        self.assemble()
        self.deploy()

    def test(self):
        pass

    def lint(self):
        pass

    def assemble(self):
        pass

    def deploy(self):
        pass
```

</div>

خب حالا پیاده سازی برای اندروید و آی او اس رو میسازیم:

<div dir="ltr">

```python
class AndroidBuilder(Builder):
    def test(self):
        print('Running android tests')

    def lint(self):
        print('Linting the android code')

    def assemble(self):
        print('Assembling the android build')

    def deploy(self):
        print('Deploying android build to server')


class IosBuilder(Builder):
    def test(self):
        print('Running ios tests')

    def lint(self):
        print('Linting the ios code')

    def assemble(self):
        print('Assembling the ios build')

    def deploy(self):
        print('Deploying ios build to server')
```

</div>

نحوه استفاده ازش هم به این صورته:

<div dir="ltr">

```python
androidBuilder = AndroidBuilder()
androidBuilder.build()

# Output:
# Running android tests
# Linting the android code
# Assembling the android build
# Deploying android build to server


iosBuilder = IosBuilder()
iosBuilder.build()

# Output:
# Running ios tests
# Linting the ios code
# Assembling the ios build
# Deploying ios build to server
```

</div>

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
class Builder {
  build(): void {
    this.test();
    this.lint();
    this.assemble();
    this.deploy();
  }

  test(): void {}

  lint(): void {}

  assemble(): void {}

  deploy(): void {}
}

class AndroidBuilder extends Builder {
  test(): void {
    console.log("Running android tests");
  }

  lint(): void {
    console.log("Linting the android code");
  }

  assemble(): void {
    console.log("Assembling the android build");
  }

  deploy(): void {
    console.log("Deploying android build to server");
  }
}

class IosBuilder extends Builder {
  test(): void {
    console.log("Running ios tests");
  }
  lint(): void {
    console.log("Linting the ios code");
  }

  assemble(): void {
    console.log("Assembling the ios build");
  }

  deploy(): void {
    console.log("Deploying ios build to server");
  }
}

const androidBuilder = new AndroidBuilder();
androidBuilder.build();

// Output:
// Running android tests
// Linting the android code
// Assembling the android build
// Deploying android build to server

const iosBuilder = new IosBuilder();
iosBuilder.build();

// Output:
// Running ios tests
// Linting the ios code
// Assembling the ios build
// Deploying ios build to server
```

</div>
</details>

<br>
<br>

---

<br>

<div align="center">

# 🤝 کمک کردن به این پروژه!

</div>

- این پروژه رو fork کنید و به زبون‌های برنامه نویسی دیگه توسعه بدید!
- این ریپو رو برای دوستاتون بفرستید!
- اشتباهاتی که وجود داره رو با issue و یا pull request فیکس کنید!
- مثال‌ها رو بهبود ببخشید و با issue و یا pull request به اشتراک بسازید!
- با ⭐ به پروژه از من و این ریپو حمایت کنید و باعث دیده شدنش بشید!

</div>
