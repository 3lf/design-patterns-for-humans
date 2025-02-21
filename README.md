<div dir="rtl">

![Design Patterns For Humans](images/poster.png)

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

| دسته بندی                   | دیزاین پترن   |
|----------------------------|-----------------------|
| **Creational Design Patterns** |                     |
|                            | [🏠 Simple Factory](#-simple-factory)     |
|                            | [🏭 Factory Method](#-factory-method)     |
|                            | [🔨 Abstract Factory](#-abstract-factory)   |
|                            | [👷 Builder](#-builder)            |
|                            | [🐑 Prototype](#-prototype)          |
|                            | [💍 Singleton](#-singleton)          |
| **Structural Design Patterns** |                   |
|                            | [🔌 Adapter](#-adapter)            |
|                            | [🌉 Bridge](#-bridge)             |
|                            | [🌿 Composite](#-composite)          |
|                            | [☕ Decorator](#-decorator)           |
|                            | [📦 Facade](#-facade)             |
|                            | [🍃 Flyweight](#-flyweight)          |
|                            | [🎱 Proxy](#-proxy)              |
| **Behavioral Design Patterns** |                  |
|                            | [🔗 Chain of Responsibility](#-chain-of-responsibility) |
|                            | [👮 Command](#-command)            |
|                            | [➿ Iterator](#-iterator)            |
|                            | [👽 Mediator](#-mediator)           |
|                            | [💾 Memento](#-memento)            |
|                            | [😎 Observer](#-observer)           |
|                            | [🏃 Visitor](#-visitor)            |
|                            | [💡 Strategy](#-strategy)           |
|                            | [💢 State](#-state)              |
|                            | [📒 Template Method](#-template-method)    |



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

---

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

توی این مثال میخوایم از اون مثال ساخت درب استفاده کنیم.

پس اول ما اینترفیس مربوط به درب رو میسازیم و بعدش یک کلاس factory برای ساخت درب میسازیم.

<details>
<summary>Python</summary>

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


class DoorFactory:
    @staticmethod
    def makeDoor(width, height):
        return WoodenDoor(width, height)


----------------------------
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
    getWidth(): void {
    }

    getHeight(): void {
    }
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

----------------------------

let door = DoorFactory.makeDoor(10, 10);
console.log(door.getHeight());
console.log(door.getWidth());
```

</div>

</details>

<details>
<summary >#C</summary>

<div dir="ltr">

```C#
public interface IDoor
{
    int GetHeight();
    int GetWidth();
}

public class WoodenDoor : IDoor
{
    private int Height { get; set; }
    private int Width { get; set; }

    public WoodenDoor(int height, int width)
    {
        this.Height = height;
        this.Width = width;
    }

    public int GetHeight()
    {
        return this.Height;
    }
    public int GetWidth()
    {
        return this.Width;
    }
}

public static class DoorFactory
{
    public static IDoor MakeDoor(int height, int width)
    {
        return new WoodenDoor(height, width);
    }
}


----------------------------

var door = DoorFactory.MakeDoor(80, 30);
Console.WriteLine($"Height of Door : {door.GetHeight()}");
Console.WriteLine($"Width of Door : {door.GetWidth()}");
```

</div>

</details>

<details>
<summary >PHP</summary>

<div dir="ltr">

```PHP
interface DoorInterface {
    public function getHeight();
    public function getWidth();
}

class WoodenDoor implements DoorInterface {
    private $height;
    private $width;

    public function __construct($height, $width) {
        $this->height = $height;
        $this->width = $width;
    }

    public function getHeight() {
        return $this->height;
    }
    public function getWidth() {
        return $this->width;
    }
}

class DoorFactory {
    public static function makeDoor($height, $width) {
        return new woodenDoor($height, $width);
    }
}

$door = DoorFactory::makeDoor(80, 30);
echo "Height of Door : " . $door->getHeight() . "\n";
echo "Width of Door : " . $door->getWidth() . "\n";

```

</div>

</details>

<details>
<summary >Go</summary>

<div dir="ltr">

```go
package main

import "fmt"

type Door interface {
	getHeight() int
	getWidth() int
}

type WoodenDoor struct {
	height int
	width  int
}

func NewWoodenDoor(height, width int) *WoodenDoor {
	return &WoodenDoor{height: height, width: width}
}

func (w *WoodenDoor) getHeight() int {
	return w.height
}

func (w *WoodenDoor) getWidth() int {
	return w.width
}

type DoorFactory struct{}

func (df *DoorFactory) makeDoor(height, width int) Door {
	return NewWoodenDoor(height, width)
}

func main() {
	doorFactory := &DoorFactory{}
	door := doorFactory.makeDoor(80, 30)
	fmt.Printf("Height of Door : %d\n", door.getHeight())
	fmt.Printf("Width of Door : %d\n", door.getWidth())
}

```

</div>

</details>


<details>
  <summary>Java</summary>

<div dir="ltr">

```java
public class Door { 
    private int width;
    private int height;
    
    public Door(int width, int height) {
        this.width = width;
        this.height = height;
    }
    
    public int getHeight() {
        return height;
    }
    public void setHeight(int height) {
        this.height = height;
    }
    public int getWidth() {
        return width;
    }
    public void setWidth(int width) {
        this.width = width;
    }
}

public class WoodenDoor extends Door {
    
    WoodenDoor(int width, int height) {
        super(width, height);
    }
}

public class DoorFactory {
    public static WoodenDoor makeDoor(int width, int height) {
        return new WoodenDoor(width, height);
    }
}

----------------------------

Door door = DoorFactory.makeDoor(10, 10);
System.out.println(door.getHeight());
System.out.println(door.getWidth());
```
</div>
</details>


<br>

---

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

بیاین از مثال مدیر استخدام برای درک بهتر استفاده کنیم.

پس اول یک اینترفیس برای مصاحبه کننده‌ها میسازیم و چند پیاده‌سازی هم برای اون ایجاد می‌کنیم.

بعد از اون `HiringManager` رو پیاده سازی میکنیم

در نهایت هر فرزند میتونه ازش ارث بری کنه و متد `makeInterviewer` خودش رو داشته باشه:

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class Interviewer:
    def askQuestions(self):
        pass


class Developer(Interviewer):
    def askQuestions(self):
        print('Asking about design patterns')


class CommunityExecutive(Interviewer):
    def askQuestions(self):
        print('Asking about community building')


class HiringManager:
    def makeInterviewer(self):
        pass

    def takeInterview(self):
        interviewer = self.makeInterviewer()
        interviewer.askQuestions()


class DevelopmentManager(HiringManager):
    def makeInterviewer(self):
        return Developer()


class MarketingManager(HiringManager):
    def makeInterviewer(self):
        return CommunityExecutive()


----------------------------

devManager = DevelopmentManager()
devManager.takeInterview()

marketingManager = MarketingManager()
marketingManager.takeInterview()
```

</div>

</details>

<details>
<summary>Typescript</summary>

<div dir="ltr">

```typescript
interface Interviewer {
    askQuestions(): void;
}

class Developer implements Interviewer {
    askQuestions(): void {
        console.log("Asking about design patterns");
    }
}

class CommunityExecutive implements Interviewer {
    askQuestions(): void {
        console.log("Asking about community building");
    }
}

abstract class HiringManager {
    abstract makeInterviewer(): Interviewer;

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

<details>
<summary >#C</summary>

<div dir="ltr">

```C#

interface IInterviewer
{
    void AskQuestions();
}

class Developer : IInterviewer
{
    public void AskQuestions()
    {
        Console.WriteLine("Asking about design patterns!");
    }
}

class CommunityExecutive : IInterviewer
{
    public void AskQuestions()
    {
        Console.WriteLine("Asking about community building!");
    }
}

abstract class HiringManager
{
    // Factory method
    abstract protected IInterviewer MakeInterviewer();
    public void TakeInterview()
    {
        var interviewer = this.MakeInterviewer();
        interviewer.AskQuestions();
    }
}

class DevelopmentManager : HiringManager
{
    protected override IInterviewer MakeInterviewer()
    {
        return new Developer();
    }
}

class MarketingManager : HiringManager
{
    protected override IInterviewer MakeInterviewer()
    {
        return new CommunityExecutive();
    }
}


----------------------------

var devManager = new DevelopmentManager();
devManager.TakeInterview(); //Output : Asking about design patterns!

var marketingManager = new MarketingManager();
marketingManager.TakeInterview();//Output : Asking about community building!

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```PHP
interface InterviewerInterface
{
    public function askQuestions();
}

class Developer implements InterviewerInterface
{
    public function askQuestions()
    {
        echo "Asking about design patterns!";
    }
}

class CommunityExecutive implements InterviewerInterface
{
    public function askQuestions()
    {
        echo "Asking about community building!";
    }
}

abstract class HiringManager
{
    // Factory method
    abstract protected function makeInterviewer(): InterviewerInterface;

    public function takeInterview()
    {
        $interviewer = $this->makeInterviewer();
        $interviewer->askQuestions();
    }
}

class DevelopmentManager extends HiringManager
{
    protected function makeInterviewer(): InterviewerInterface
    {
        return new Developer();
    }
}

class MarketingManager extends HiringManager
{
    protected function makeInterviewer(): InterviewerInterface
    {
        return new CommunityExecutive();
    }
}


// Usage
$devManager = new DevelopmentManager();
$devManager->takeInterview(); // Output: Asking about design patterns!

$marketingManager = new MarketingManager();
$marketingManager->takeInterview(); // Output: Asking about community building!

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import "fmt"

type Interviewer interface {
	AskQuestions()
}

type Developer struct{}

func (d *Developer) AskQuestions() {
	fmt.Println("Asking about design patterns!")
}

type CommunityExecutive struct{}

func (ce *CommunityExecutive) AskQuestions() {
	fmt.Println("Asking about community building!")
}

type HiringManager interface {
	MakeInterviewer() Interviewer
	TakeInterview()
}

type DevelopmentManager struct{}

func (dm *DevelopmentManager) MakeInterviewer() Interviewer {
	return &Developer{}
}

func (dm *DevelopmentManager) TakeInterview() {
	interviewer := dm.MakeInterviewer()
	interviewer.AskQuestions()
}

type MarketingManager struct{}

func (mm *MarketingManager) MakeInterviewer() Interviewer {
	return &CommunityExecutive{}
}

func (mm *MarketingManager) TakeInterview() {
	interviewer := mm.MakeInterviewer()
	interviewer.AskQuestions()
}

func main() {
	devManager := &DevelopmentManager{}
	devManager.TakeInterview() // Output : Asking about design patterns!

	marketingManager := &MarketingManager{}
	marketingManager.TakeInterview() // Output : Asking about community building!
}

```

</div>

</details>


<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface Interviewer {
  void askQuestions();
}

class Developer implements Interviewer {

  @Override
  public void askQuestions() {
    System.out.println("Asking about design patterns");
  }
}

class CommunityExecutive implements Interviewer {

  @Override
  public void askQuestions() {
    System.out.println("Asking about community building");
  }
}

abstract class HiringManager {
  abstract Interviewer makeInterviewer();
  public void takeInterview() {
    Interviewer interviewer = this.makeInterviewer();
    interviewer.askQuestions();
  }
}

class DevelopmentManager extends HiringManager {
  public Developer makeInterviewer() {
    return new Developer();
  }
}

class MarketingManager extends HiringManager {
  public CommunityExecutive makeInterviewer() {
    return new CommunityExecutive();
  }
}

----------------------------

DevelopmentManager devManager = new DevelopmentManager();
devManager.takeInterview();

MarketingManager marketingManager = new MarketingManager();
marketingManager.takeInterview();
```
</div>
</details>


<br>

**چه موقع باید ازش استفاده کنیم؟**

اساساً زمانی ازین الگو استفاده میشه که چندین کلاس با ریشه مشترک داریم (یعنی چندین کلاس یک کلاس parent رو پیاده‌سازی
می‌کنند) و با توجه به شرایط تصمیم میگیریم از یکی از اون‌ها استفاده کنیم.

<br>

---

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

خب همون مثال ساخت خونه و نیاز به درب‌های مختلف رو ترجمه میکنیم.

اول باید اینترفیس درب رو بسازیم و چند پیاده‌سازی ازش ایجاد کنیم.

در مرحله بعد برای هر درب متخصص مربوطه رو ایجاد می‌کنیم.

و در مرحله آخر سراغ پیاده‌سازی دیزاین پترن‌مون میریم.

برای مثال کلاس `WoodenDoorFactory` زمانی استفاده میشه که نیاز به درب چوبی داریم و کارش اینه که برای ایجاد ابجکت درب (که
اینجا
درب چوبی هست) از کلاس `WoodenDoor` و برای ایجاد ابجکت متخصص (که اینجا نجار هست) از `Carpenter` استفاده کنه.

این موضوع برای درب آهنی و ... هم بطور مشابه پیاده‌سازی میشه.

<details>
<summary>Python</summary>

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


class DoorFittingExpert:
    def getDescription(self):
        pass


class Welder(DoorFittingExpert):
    def getDescription(self):
        print('I can only fit iron doors')


class Carpenter(DoorFittingExpert):
    def getDescription(self):
        print('I can only fit wooden doors')


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


----------------------------

woodenFactory = WoodenDoorFactory()

door = woodenFactory.makeDoor()
expert = woodenFactory.makeFittingExpert()

door.getDescription()
expert.getDescription()

----------------------------

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

</details>

<details>
<summary>Typescript</summary>

<div dir="ltr">

```typescript
interface Door {
    getDescription(): void;
}

class WoodenDoor implements Door {
    getDescription(): void {
        console.log("I am a wooden door");
    }
}

class IronDoor implements Door {
    getDescription(): void {
        console.log("I am an iron door");
    }
}

interface DoorFittingExpert {
    getDescription(): void;
}

class Welder implements DoorFittingExpert {
    getDescription(): void {
        console.log("I can only fit iron doors");
    }
}

class Carpenter implements DoorFittingExpert {
    getDescription(): void {
        console.log("I can only fit wooden doors");
    }
}

abstract class DoorFactory {
    abstract makeDoor(): Door;

    abstract makeFittingExpert(): DoorFittingExpert;
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
----------------------------

let woodenFactory = new WoodenDoorFactory();

let door = woodenFactory.makeDoor();
let expert = woodenFactory.makeFittingExpert();

door.getDescription();
expert.getDescription();

----------------------------

let ironFactory = new IronDoorFactory();

door = ironFactory.makeDoor();
expert = ironFactory.makeFittingExpert();

door.getDescription();
expert.getDescription();

```

</div>

**همونطور که میبیند، می‌تونیم بطور مشابه با هر دو نوع درب برخورد کنیم و ازین موضوع مطمئن باشیم که متخصص اشتباه برای یک
درب
انتخاب نمی‌کنیم.**

</details>

<details>
<summary >#C</summary>

<div dir="ltr">

```C#

interface IDoor {

  void GetDescription();

}
class WoodenDoor : IDoor
{
  public void GetDescription()
  {
    Console.WriteLine("I am a wooden door");
  }
}

class IronDoor : IDoor
{
  public void GetDescription()
  {
    Console.WriteLine("I am a iron door");
  }
}

interface IDoorFittingExpert
{
  void GetDescription();
}

class Welder : IDoorFittingExpert
{
  public void GetDescription()
  {
    Console.WriteLine("I can only fit iron doors");
  }
}

class Carpenter : IDoorFittingExpert
{
  public void GetDescription()
  {
    Console.WriteLine("I can only fit wooden doors");
  }
}

interface IDoorFactory {
  IDoor MakeDoor();
  IDoorFittingExpert MakeFittingExpert();
}

// Wooden factory to return carpenter and wooden door
class WoodenDoorFactory : IDoorFactory
{
  public IDoor MakeDoor()
  {
    return new WoodenDoor();
  }

  public IDoorFittingExpert MakeFittingExpert()
  {
    return new Carpenter();
  }
}

// Iron door factory to get iron door and the relevant fitting expert
class IronDoorFactory : IDoorFactory
{
  public IDoor MakeDoor()
  {
    return new IronDoor();
  }

  public IDoorFittingExpert MakeFittingExpert()
  {
    return new Welder();
  }
}
----------------------------
var woodenDoorFactory = new WoodenDoorFactory();

var woodenDoor = woodenDoorFactory.MakeDoor();
var woodenDoorFittingExpert = woodenDoorFactory.MakeFittingExpert();

woodenDoor.GetDescription(); //Output : I am a wooden door
woodenDoorFittingExpert.GetDescription();//Output : I can only fit woooden doors

----------------------------

var ironDoorFactory = new IronDoorFactory();

var ironDoor = ironDoorFactory.MakeDoor();
var ironDoorFittingExpert = ironDoorFactory.MakeFittingExpert();

ironDoor.GetDescription();//Output : I am a iron door
ironDoorFittingExpert.GetDescription();//Output : I can only fit iron doors

```

</div>

**همونطور که میبیند، می‌تونیم بطور مشابه با هر دو نوع درب برخورد کنیم و ازین موضوع مطمئن باشیم که متخصص اشتباه برای یک
درب
انتخاب نمی‌کنیم.**

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```PHP

interface DoorInterface {
  public function getDescription();
}

class WoodenDoor implements DoorInterface {
  public function getDescription() {
    echo "I am a wooden door";
  }
}

class IronDoor implements DoorInterface {
  public function getDescription() {
    echo "I am an iron door";
  }
}

interface DoorFittingExpertInterface {
  public function getDescription();
}

class Welder implements DoorFittingExpertInterface {
  public function getDescription() {
    echo "I can only fit iron doors";
  }
}

class Carpenter implements DoorFittingExpertInterface {
  public function getDescription() {
    echo "I can only fit wooden doors";
  }
}

interface DoorFactoryInterface {
  public function makeDoor(): DoorInterface;
  public function makeFittingExpert(): DoorFittingExpertInterface;
}

// Wooden factory to return carpenter and wooden door
class WoodenDoorFactory implements DoorFactoryInterface {
  public function makeDoor(): DoorInterface {
    return new WoodenDoor();
  }

  public function makeFittingExpert(): DoorFittingExpertInterface {
    return new Carpenter();
  }
}

// Iron door factory to get iron door and the relevant fitting expert
class IronDoorFactory implements DoorFactoryInterface {
  public function makeDoor(): DoorInterface {
    return new IronDoor();
  }

  public function makeFittingExpert(): DoorFittingExpertInterface {
    return new Welder();
  }
}


// Usage
$woodenDoorFactory = new WoodenDoorFactory();

$woodenDoor = $woodenDoorFactory->makeDoor();
$woodenDoorFittingExpert = $woodenDoorFactory->makeFittingExpert();

$woodenDoor->getDescription(); // Output: I am a wooden door
$woodenDoorFittingExpert->getDescription(); // Output: I can only fit wooden doors


$ironDoorFactory = new IronDoorFactory();

$ironDoor = $ironDoorFactory->makeDoor();
$ironDoorFittingExpert = $ironDoorFactory->makeFittingExpert();

$ironDoor->getDescription(); // Output: I am an iron door
$ironDoorFittingExpert->getDescription(); // Output: I can only fit iron doors

```

</div>

**همونطور که میبیند، می‌تونیم به‌طور مشابه با هر دو نوع درب برخورد کنیم و ازین موضوع مطمئن باشیم که متخصص اشتباه برای یک
درب
انتخاب نمی‌کنیم.**

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go

package main

import "fmt"

type IDoor interface {
	GetDescription()
}

type WoodenDoor struct{}

func (w *WoodenDoor) GetDescription() {
	fmt.Println("I am a wooden door")
}

type IronDoor struct{}

func (i *IronDoor) GetDescription() {
	fmt.Println("I am an iron door")
}

type IDoorFittingExpert interface {
	GetDescription()
}

type Carpenter struct{}

func (c *Carpenter) GetDescription() {
	fmt.Println("I can only fit wooden doors")
}

type Welder struct{}

func (w *Welder) GetDescription() {
	fmt.Println("I can only fit iron doors")
}

type IDoorFactory interface {
	MakeDoor() IDoor
	MakeFittingExpert() IDoorFittingExpert
}

type WoodenDoorFactory struct{}

func (w *WoodenDoorFactory) MakeDoor() IDoor {
	return &WoodenDoor{}
}

func (w *WoodenDoorFactory) MakeFittingExpert() IDoorFittingExpert {
	return &Carpenter{}
}

type IronDoorFactory struct{}

func (i *IronDoorFactory) MakeDoor() IDoor {
	return &IronDoor{}
}

func (i *IronDoorFactory) MakeFittingExpert() IDoorFittingExpert {
	return &Welder{}
}

func main() {
	woodenDoorFactory := &WoodenDoorFactory{}

	woodenDoor := woodenDoorFactory.MakeDoor()
	woodenDoorFittingExpert := woodenDoorFactory.MakeFittingExpert()

	woodenDoor.GetDescription()           // Output: I am a wooden door
	woodenDoorFittingExpert.GetDescription() // Output: I can only fit wooden doors

	ironDoorFactory := &IronDoorFactory{}

	ironDoor := ironDoorFactory.MakeDoor()
	ironDoorFittingExpert := ironDoorFactory.MakeFittingExpert()

	ironDoor.GetDescription()           // Output: I am an iron door
	ironDoorFittingExpert.GetDescription() // Output: I can only fit iron doors
}

```

</div>

**همونطور که میبیند، می‌تونیم به‌طور مشابه با هر دو نوع درب برخورد کنیم و ازین موضوع مطمئن باشیم که متخصص اشتباه برای یک
درب
انتخاب نمی‌کنیم.**

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface Door {
    void getDescription();
}

class WoodenDoor implements Door {
    @Override
    public void getDescription() {
        System.out.println("I am a wooden door");
    }
}

class IronDoor implements Door {
    @Override
    public void getDescription() {
        System.out.println("I am an iron door");
    }
}

interface DoorFittingExpert {
    void getDescription();
}

class Welder implements DoorFittingExpert {
    @Override
    public void getDescription() {
        System.out.println("I can only fit iron doors");
    }
}

class Carpenter implements DoorFittingExpert {
    @Override
    public void getDescription() {
        System.out.println("I can only fit wooden doors");
    }
}

interface DoorFactory {
    Door makeDoor();
    DoorFittingExpert makeFittingExpert();
}

class WoodenDoorFactory implements DoorFactory {
    @Override
    public WoodenDoor makeDoor() {
        return new WoodenDoor();
    }

    @Override
    public Carpenter makeFittingExpert() {
        return new Carpenter();
    }
}

class IronDoorFactory implements DoorFactory {
    public IronDoor makeDoor() {
        return new IronDoor();
    }

    public Welder makeFittingExpert() {
        return new Welder();
    }
}

-----

IronDoorFactory ironDoorFactory = new IronDoorFactory();
IronDoor ironDoor = ironDoorFactory.MakeDoor();
IronDoorFittingExpert ironDoorFittingExpert = ironDoorFactory.MakeFittingExpert();

ironDoor.GetDescription(); //Output : I am a iron door
ironDoorFittingExpert.GetDescription(); //Output : I can only fit iron doors
```
</div>

**همونطور که میبیند، می‌تونیم به‌طور مشابه با هر دو نوع درب برخورد کنیم و ازین موضوع مطمئن باشیم که متخصص اشتباه برای یک
درب
انتخاب نمی‌کنیم.**

</details>

<br>

**چه موقع باید ازش استفاده کنیم؟**

زمانی که وابستگی‌های منطقی نه چندان ساده برای ایجاد وجود داره، میتونیم ازین دیزاین پترن استفاده کنیم.

<br>

---

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
<summary>Python</summary>
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
constructor(size: any, cheese: boolean = true, pepperoni:boolean = true, tomato: boolean = false, lettuce: boolean = true) {}

```

</div>
</details>

<details>
<summary >#C</summary>

<div dir="ltr">

```C#

public Burger(int size, bool cheese, bool pepperoni, bool lettuce, bool tomato)

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```PHP

public function __construct(int $size, bool $cheese, bool $pepperoni, bool $lettuce, bool $tomato)

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go

func Burger(size int, cheese bool, pepperoni bool, lettuce bool, tomato bool)

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
public Burger(int size, boolean cheese, boolean pepperoni, boolean lettuce, boolean tomato)
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

در این بخش هم میخوام مثال برگر رو براتون ترجمه کنم.

اولین مرحله اینه که یک کلاس برگر معمولی داشته باشیم

در ادامه کلاس Builder رو براش ایجاد میکنیم.

<details>
<summary>Python</summary>

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


----------------------------

burger = BurgerBuilder(10).addPepperoni().addLettuce().addTomato().build()

print(vars(burger))
```

</div>

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

    constructor(builder: BurgerBuilder) {
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

----------------------------

let burger = new BurgerBuilder(10)
    .addPepperoni()
    .addLettuce()
    .addTomato()
    .build();

console.log(Object.keys(burger));
```

</div>
</details>

<details>
<summary >#C</summary>

<div dir="ltr">

```C#
class Burger
{
  private int mSize;
  private bool mCheese;
  private bool mPepperoni;
  private bool mLettuce;
  private bool mTomato;

  public Burger(BurgerBuilder builder)
  {
    this.mSize = builder.Size;
    this.mCheese = builder.Cheese;
    this.mPepperoni = builder.Pepperoni;
    this.mLettuce = builder.Lettuce;
    this.mTomato = builder.Tomato;
  }

  public string GetDescription()
  {
    var sb = new StringBuilder();
    sb.Append($"This is {this.mSize} inch Burger. ");
    return sb.ToString();
  }
}

class BurgerBuilder {
  public int Size;
  public bool Cheese;
  public bool Pepperoni;
  public bool Lettuce;
  public bool Tomato;

  public BurgerBuilder(int size)
  {
    this.Size = size;
  }

  public BurgerBuilder AddCheese()
  {
    this.Cheese = true;
    return this;
  }

  public BurgerBuilder AddPepperoni()
  {
    this.Pepperoni = true;
    return this;
  }

  public BurgerBuilder AddLettuce()
  {
    this.Lettuce = true;
    return this;
  }

  public BurgerBuilder AddTomato()
  {
    this.Tomato = true;
    return this;
  }

  public Burger Build()
  {
    return new Burger(this);
  }
}

----------------------------

var burger = new BurgerBuilder(4).AddCheese()
                                .AddPepperoni()
                                .AddLettuce()
                                .AddTomato()
                                .Build();
Console.WriteLine(burger.GetDescription());

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```PHP
class Burger {
    private $size;
    private $cheese = false;
    private $pepperoni = false;
    private $lettuce = false;
    private $tomato = false;

    public function __construct($builder) {
        $this->size = $builder->size;
        $this->cheese = $builder->cheese;
        $this->pepperoni = $builder->pepperoni;
        $this->lettuce = $builder->lettuce;
        $this->tomato = $builder->tomato;
    }
}

class BurgerBuilder {
    public $size;
    public $cheese = false;
    public $pepperoni = false;
    public $lettuce = false;
    public $tomato = false;

    public function __construct($size) {
        $this->size = $size;
    }

    public function addPepperoni() {
        $this->pepperoni = true;
        return $this;
    }

    public function addLettuce() {
        $this->lettuce = true;
        return $this;
    }

    public function addCheese() {
        $this->cheese = true;
        return $this;
    }

    public function addTomato() {
        $this->tomato = true;
        return $this;
    }

    public function build() {
        return new Burger($this);
    }
}

$burger = (new BurgerBuilder(10))
            ->addCheese()
            ->addPepperoni()
            ->addLettuce()
            ->addTomato()
            ->build();
            
var_dump(get_object_vars($burger));

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import (
"fmt"
"strings"
)

type Burger struct {
Size int
Cheese bool
Pepperoni bool
Lettuce bool
Tomato bool
}

func NewBurger(builder *BurgerBuilder) *Burger {
return &Burger{
Size: builder.Size,
Cheese: builder.Cheese,
Pepperoni: builder.Pepperoni,
Lettuce: builder.Lettuce,
Tomato: builder.Tomato,
}
}

func (b *Burger) GetDescription() string {
var sb strings.Builder
sb.WriteString(fmt.Sprintf("This is %d inch Burger. ", b.Size))
return sb.String()
}

type BurgerBuilder struct {
Size int
Cheese bool
Pepperoni bool
Lettuce bool
Tomato bool
}

func NewBurgerBuilder(size int) *BurgerBuilder {
return &BurgerBuilder{Size: size}
}

func (b *BurgerBuilder) AddCheese() *BurgerBuilder {
b.Cheese = true
return b
}

func (b *BurgerBuilder) AddPepperoni() *BurgerBuilder {
b.Pepperoni = true
return b
}

func (b *BurgerBuilder) AddLettuce() *BurgerBuilder {
b.Lettuce = true
return b
}

func (b *BurgerBuilder) AddTomato() *BurgerBuilder {
b.Tomato = true
return b
}

func (b *BurgerBuilder) Build() *Burger {
return NewBurger(b)
}

func main() {
burger := NewBurgerBuilder(4).AddCheese().AddPepperoni().AddLettuce().AddTomato().Build()
fmt.Println(burger.GetDescription())
}




```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
class Burger {
    private int size;
    private boolean cheese;
    private boolean pepperoni;
    private boolean lettuce;
    private boolean tomato;

    public Burger(BurgerBuilder builder) {
        this.size = builder.size;
        this.cheese = builder.cheese;
        this.pepperoni = builder.pepperoni;
        this.lettuce = builder.lettuce;
        this.tomato = builder.tomato;
    }
    public String getDescription() {
        var sb = new StringBuilder();
        sb.append("This is " + this.size + " inch Burger.");
        return sb.toString();
    }
    public static BurgerBuilder builder() {
        return new BurgerBuilder();
    }
}

class BurgerBuilder {
    public int size;
    public boolean cheese;
    public boolean pepperoni;
    public boolean lettuce;
    public boolean tomato;
    
    public Burger build() {
        return new Burger(this);
    }
    public BurgerBuilder size(int size) {
        this.size = size;
        return this;
    }
    public BurgerBuilder cheese(boolean cheese) {
        this.cheese = cheese;
        return this;
    }
    public BurgerBuilder pepperoni(boolean pepperoni) {
        this.pepperoni = pepperoni;
        return this;
    }
    public BurgerBuilder lettuce(boolean lettuce) {
        this.lettuce = lettuce;
        return this;
    }
    public BurgerBuilder tomato(boolean tomato) {
        this.tomato = tomato;
        return this;
    }
}

----------------------------

Burger burger = Burger.builder()
        .size(10)
        .cheese(true)
        .pepperoni(true)
        .lettuce(false)
        .tomato(false)
        .build();

System.out.println(burger.getDescription());
```
</div>
</details>

<br>

**چه موقع باید ازش استفاده کنیم؟**

همونطور که قبل تر اشاره کردم این دیزاین پترن رو معمولا برای ساخت ابجکت‌های پیچیده یا ابجکت‌هایی که نیاز به شخصی سازی
زیادی دارن استفاده میکنیم.

<br>

---

<div align="center">

## 🐑 Prototype

</div>

یک مثال از دنیای واقعی:

> چیزی درمورد دالی شنیدین
>
؟ ([اگه نه اینجارو بخونید](<https://fa.wikipedia.org/wiki/%D8%AF%D8%A7%D9%84%DB%8C_(%DA%AF%D9%88%D8%B3%D9%81%D9%86%D8%AF)>))
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

فرض کنید کلاس SomeComponent رو به صورتی که در کد میبینید داریم.

باید دو کلاس copy و deep کپی ایجاد کنیم.

<details>
<summary>Python</summary>

پایتون magic method‌هایی برای این مساله در نظر گرفته که ماهم از همون دو تابع معروف copy و deep copy استفاده میکنیم:

<div dir="ltr">

```python
class SomeComponent:
    def __init__(self, some_int, some_list_of_objects, some_circular_ref):
        self.some_int = some_int
        self.some_list_of_objects = some_list_of_objects
        self.some_circular_ref = some_circular_ref

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
        let someListOfObjects = Object.assign([], this.someListOfObjects);
        let someCircularRef = Object.assign({}, this.someCircularRef);
        let newComponent = new SomeComponent(
            this.someInt, someListOfObjects, someCircularRef
        );
        Object.assign(newComponent, this);
        return newComponent;
    }

    deepCopy(memo: object = {}) {
        let someListOfObjects = JSON.parse(JSON.stringify(this.someListOfObjects));
        let someCircularRef = JSON.parse(JSON.stringify(this.someCircularRef));
        let newComponent = new SomeComponent(
            this.someInt, someListOfObjects, someCircularRef
        );
        newComponent = JSON.parse(JSON.stringify(this));
        return newComponent;
    }
}

------------------------------

let component = new SomeComponent(1, [1,2,3], {x : 1});
let copyComponent = component.copy();

console.log(copyComponent.someListOfObjects);   // [ 1, 2, 3 ]
console.log(copyComponent.someCircularRef);     // { x: 1 }

component.someListOfObjects.push(4);
component.someCircularRef.y = 6;

console.log(copyComponent.someListOfObjects)    // [ 1, 2, 3, 4 ]
console.log(copyComponent.someCircularRef)      // { x: 1, y: 6 }

------------------------------
let component2 = new SomeComponent(1, [1,2,3], {x : 1});
let copyComponent2 = component2.deepCopy();

console.log(copyComponent2.someListOfObjects);   // [ 1, 2, 3 ]
console.log(copyComponent2.someCircularRef);     // { x: 1 }

component2.someListOfObjects.push(4);
component2.someCircularRef.y = 6;

console.log(copyComponent2.someListOfObjects);   // [ 1, 2, 3 ]
console.log(copyComponent2.someCircularRef);     // { x: 1 }
```

</div>
</details>

<details>
<summary >#C</summary>

<div dir="ltr">

```C#

public class SomeComponent
{
    public int someInt;
    public string? someString;

    public SomeComponent ShallowCopy()
    {
        return (SomeComponent)this.MemberwiseClone();
    }

    public SomeComponent DeepCopy()
    {
        SomeComponent clone = (SomeComponent)this.MemberwiseClone();
        clone.someInt = someInt;
        clone.someString = someString;
        return clone;
    }
}

----------------------------

SomeComponent c1 = new SomeComponent();
c1.someInt = 1;
c1.someString = "someString1";

// Perform a shallow copy of c1 and assign it to c2.
SomeComponent c2 = c1.ShallowCopy();

// Make a deep copy of c1 and assign it to c3.
SomeComponent c3 = c1.DeepCopy();

Console.WriteLine(c1.someInt + ":" + c1.someString); // 1:someString1
Console.WriteLine(c2.someInt + ":" + c2.someString); // 1:someString1
Console.WriteLine(c3.someInt + ":" + c3.someString); // 1:someString1

c1.someInt = 2;
c1.someString = "someString2";

Console.WriteLine(c1.someInt + ":" + c1.someString); // 2:someString2
Console.WriteLine(c2.someInt + ":" + c2.someString); // 1:someString1
Console.WriteLine(c3.someInt + ":" + c3.someString); // 1:someString1

```

</div>



<br>

برای deepCopy میتونیم از json Deserialize استفاده کنیم :


<div dir="ltr">

```C#

public abstract class Person
{
    public abstract string Name { get; set; }

    public abstract Person Clone(bool deepClone);
}

public class Manager : Person
{
    public override string Name { get; set; }

    public Manager(string name)
    {
        Name = name;

    }

    public override Person Clone( bool deepClone=false)
    {      
       if (deepClone)
        {
            var objectAsJson = JsonConvert.SerializeObject(this);
            return JsonConvert.DeserializeObject<Manager>(objectAsJson);

        }
        return (Person)MemberwiseClone();
    }
}

public class Employee : Person
{ 
    public Manager Manager { get; set; }
    public override string Name { get; set; }
    public Employee(string name, Manager manager)
    {

        Name = name;
        Manager = manager;
    }
    public override Person Clone(bool deepClone = false)
    {
           if (deepClone)
        {
            var objectAsJson = JsonConvert.SerializeObject(this);
            return JsonConvert.DeserializeObject<Employee>(objectAsJson);

        }
        return (Person)MemberwiseClone() ;
    }

}

var manager = new Manager("Cindey");
var managerClone = (Manager)manager.Clone(true);

var employee = new Employee("kevin", managerClone);
var employeeClone = (Employee)employee.Clone(true);
```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```PHP

class SomeComponent
{
    public int $someInt;
    public ?string $someString;

    public function __clone()
    {
        // no need to manually copy fields, PHP's __clone does it automatically for primitive types
    }

    public function shallowCopy(): SomeComponent
    {
        return clone $this;
    }

    public function deepCopy(): SomeComponent
    {
        $clone = clone $this;
        $clone->someInt = $this->someInt;
        $clone->someString = $this->someString;
        return $clone;
    }
}

$c1 = new SomeComponent();
$c1->someInt = 1;
$c1->someString = "someString1";

// Perform a shallow copy of c1 and assign it to c2.
$c2 = $c1->shallowCopy();

// Make a deep copy of c1 and assign it to c3.
$c3 = $c1->deepCopy();

echo $c1->someInt . ":" . $c1->someString . "\n"; // 1:someString1
echo $c2->someInt . ":" . $c2->someString . "\n"; // 1:someString1
echo $c3->someInt . ":" . $c3->someString . "\n"; // 1:someString1

$c1->someInt = 2;
$c1->someString = "someString2";

echo $c1->someInt . ":" . $c1->someString . "\n"; // 2:someString2
echo $c2->someInt . ":" . $c2->someString . "\n"; // 1:someString1
echo $c3->someInt . ":" . $c3->someString . "\n"; // 1:someString1

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import (
    "encoding/json"
    "fmt"
)

type Person interface {
    GetName() string
    SetName(name string)
    Clone(deepClone bool) Person
}

type Manager struct {
    Name string `json:"name"`
}

func NewManager(name string) *Manager {
    return &Manager{
        Name: name,
    }
}

func (m *Manager) GetName() string {
    return m.Name
}

func (m *Manager) SetName(name string) {
    m.Name = name
}

func (m *Manager) Clone(deepClone bool) Person {
    if deepClone {
        objectAsJson, _ := json.Marshal(m)
        clone := &Manager{}
        json.Unmarshal(objectAsJson, clone)
        return clone
    }
    return &Manager{
        Name: m.Name,
    }
}

type Employee struct {
    Name    string   `json:"name"`
    Manager *Manager `json:"manager"`
}

func NewEmployee(name string, manager *Manager) *Employee {
    return &Employee{
        Name:    name,
        Manager: manager,
    }
}

func (e *Employee) GetName() string {
    return e.Name
}

func (e *Employee) SetName(name string) {
    e.Name = name
}

func (e *Employee) Clone(deepClone bool) Person {
    if deepClone {
        objectAsJson, _ := json.Marshal(e)
        clone := &Employee{}
        json.Unmarshal(objectAsJson, clone)
        return clone
    }
    return &Employee{
        Name:    e.Name,
        Manager: e.Manager.Clone(false).(*Manager),
    }
}

func main() {
    manager := NewManager("Cindey")
    managerClone := manager.Clone(true).(*Manager)
    fmt.Println(managerClone.GetName())

    employee := NewEmployee("kevin", managerClone)
    employeeClone := employee.Clone(true).(*Employee)
    fmt.Println(employeeClone.GetName(), employeeClone.Manager.GetName())
}

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface Cloneable {
    Object clone();
}
class SomeComponent implements Cloneable {
    private int someInt;
    private String someString;

    public int getSomeInt() {return someInt;}
    public void setSomeInt(int someInt) {this.someInt = someInt;}
    public String getSomeString() {return someString;}
    public void setSomeString(String someString) {this.someString = someString;}

    public SomeComponent copy() {
        return this;
    }

    public SomeComponent deepCopy() {
        return this.clone();
    }

    @Override
    public SomeComponent clone() {
        SomeComponent cloned = new SomeComponent();
        cloned.setSomeInt(this.someInt);
        cloned.setSomeString(this.someString);
        return cloned;
    }
}

----------------------------

SomeComponent mainComponent = new SomeComponent();
mainComponent.setSomeInt(1);
mainComponent.setSomeString("main");

SomeComponent copyComponent = mainComponent.copy();
SomeComponent clonedComponent = mainComponent.deepCopy();

copyComponent.setSomeString("copy");
clonedComponent.setSomeString("clone");

System.out.println(mainComponent.getSomeString().equals(copyComponent.getSomeString()));    // True
System.out.println(mainComponent.getSomeString().equals(clonedComponent.getSomeString()));  // False
```

</div>

</details>

<br>

**تفاوت Shadow Copy و Deep Copy ؟**
<br>
توی Shadow Copy، یک متغیر ساخته می‌شود و به مکانی توی حافظه، که مقدار متغیر قبلی توش قرار گرفته، اشاره می‌کنه. پس اگر
شما مقدار
متغیر اول رو تغییر بدین، متغیر دوم هم تغییر می‌کنه. و همین‌طور اگر مقدار متغیر دوم رو تغییر بدین، مقدار متغیر اول هم
تغییر می‌کنه.

ولی توی deep copy، یک متغیر ساخته می‌شه و مقدار متغیر قبلی توی اون کپی می‌شه. در نتیجه تغییر ابجکت اول یا ابجکت کپی
تغییری توی اون یکی به وجود نمیاره.

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

بطور کلی برای ساخت singleton باید تابع سازنده private بشه، cloning و متود‌های copy بسته بشن و تابع استاتیکی برای ساخت
ابجکت تعریف بشه.

ولی توی پایتون راه حل ساده تری وجود داره که اون استفاده از metaclass هاست:

<details>
<summary>Python</summary>

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

----------------------------

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

<details>
<summary >#C</summary>

<div dir="ltr">

```C#

public class President
{
  static President instance;
  // Private constructor
  private President()
  {
    //Hiding the Constructor
  }

  // Public constructor
  public static President GetInstance()
  {
    if (instance == null) {
      instance = new President();
    }
    return instance;
  }
}

----------------------------

President a = President.GetInstance();
President b = President.GetInstance();

Console.WriteLine(a == b); //Output : true

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```PHP

class President
{
  private static $instance;

  private function __construct()
  {
    // Hiding the Constructor
  }

  public static function getInstance()
  {
    if (self::$instance == null) {
      self::$instance = new President();
    }
    return self::$instance;
  }
}

$a = President::getInstance();
$b = President::getInstance();

var_dump($a === $b); // Output: bool(true)

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
type President struct {}

var instance *President

func GetInstance() *President {
  if instance == nil {
    instance = &President{}
  }
  return instance
}

-----------------------

a := GetInstance()
b := GetInstance()
fmt.Println(a == b) // Output: true


```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
class President {
    private static President instance;
    // Private constructor
    private President() {
        // Hiding the Constructor
    }

    public static President getInstance() {
        if (instance == null) {
            instance = new President();
        }
        return instance;
    }
}

----------------------------

President a = President.getInstance();
President b = President.getInstance();

System.out.println(a == b); // True
```

</div>

</details>

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

<br>

---

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

فرض کنید یک شکارچی به شیر‌ها حمله میکنه و اون‌ها غرش میکنن.

خب اول باید یک اینترفیس `lion` (شیر) بسازیم که شیر‌های مختلف ازش استفاده کنن.

در مرحله بعد شکارچی وقتی شکار انجام بده اون شیر غرش (roar) انجام میده.

حالا فرض کنید یک موجودیت جدید مثل `WildDog` (سگ وحشی) به برنامه اضافه شده.

خب سگ غرش انجام نمیده بجای اون `bark` (پارس کردن) انجام میده.

خب اینجا `WildDog` (سگ وحشی) با تابع `hunt` شکارچی ناسازگار میشه. (چون در زمان شکار تابع roar رو صدا میزنیم و سگ شکاری این تابع رو
نداره!)

برای حلش به این صورت میتونیم براش آداپتور تعریف کنیم:

<details>
<summary>Python</summary>

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


class Hunter:
    def hunt(self, lion):
        lion.roar()


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


----------------------------

wildDog = WildDog()
wildDogAdapter = WildDogAdapter(wildDog)

hunter = Hunter()
hunter.hunt(wildDogAdapter)
```

</div>
در واقع مثال واقعی و قابل حس نیست ولی مفهوم رو به خوبی منتقل می‌کنه.

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
class Lion {
    roar(): void {
    }
}

class AfricanLion extends Lion {
    roar(): void {
    }
}

class AsianLion extends Lion {
    roar(): void {
    }
}

class Hunter {
    hunt(lion: Lion): void {
        lion.roar();
    }
}

class WildDog {
    static bark(): void {
    }
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

----------------------------

const wildDog = new WildDog();
const wildDogAdapter = new WildDogAdapter(wildDog);

const hunter = new Hunter();
hunter.hunt(wildDogAdapter);
```

</div>
</details>

<details>
<summary>Javascript</summary>
<div dir="ltr">

```javascript
class Lion {
    roar() {
        console.log("Lion roars!");
    }
}

class AfricanLion extends Lion {
    roar() {
        console.log("African Lion roars!");
    }
}

class AsianLion extends Lion {
    roar() {
        console.log("Asian Lion roars!");
    }
}

class Hunter {
    hunt(lion) {
        lion.roar();
    }
}

class WildDog {
    static bark() {
        console.log("Wild Dog barks!");
    }
}

class WildDogAdapter extends Lion {
    constructor(dog) {
        super();
        this.dog = dog;
    }

    roar() {
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

<details>
<summary >#C</summary>

<div dir="ltr">

```C#
interface ILion
{
  void Roar();
}

class AfricanLion : ILion
{
  public void Roar()
  {

  }
}

class AsiaLion : ILion
{
  public void Roar()
  {

  }
}

class Hunter
{
  public void Hunt(ILion lion)
  {

  }
}

// This needs to be added to the game
class WildDog
{
  public void bark()
  {
  }
}

// Adapter around wild dog to make it compatible with our game
class WildDogAdapter : ILion
{
  private WildDog mDog;
  public WildDogAdapter(WildDog dog)
  {
    this.mDog = dog;
  }
  public void Roar()
  {
    mDog.bark();
  }
}

----------------------------

var wildDog = new WildDog();
var wildDogAdapter = new WildDogAdapter(wildDog);

var hunter = new Hunter();
hunter.Hunt(wildDogAdapter);

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```PHP

interface Lion {
    public function roar();
}

class AfricanLion implements Lion {
    public function roar() {
        // implementation specific to AfricanLion
    }
}

class AsianLion implements Lion {
    public function roar() {
        // implementation specific to AsianLion
    }
}

class Hunter {
    public function hunt(Lion $lion) {
        $lion->roar();
    }
}

class WildDog {
    public static function bark() {
        // implementation specific to WildDog
    }
}

// Adapter around wild dog to make it compatible with our game
class WildDogAdapter implements Lion
{
    private $mDog;
    public function __construct(WildDog $dog)
    {
        $this->mDog = $dog;
    }
    public function roar()
    {
        $this->mDog->bark();
    }
}

$wildDog = new WildDog();
$wildDogAdapter = new WildDogAdapter($wildDog);

$hunter = new Hunter();
$hunter->hunt($wildDogAdapter);

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go

package main

import "fmt"

type ILion interface {
Roar()
}

type AfricanLion struct{}

func (a AfricanLion) Roar() {}

type AsiaLion struct{}

func (a AsiaLion) Roar() {}

type Hunter struct{}

func (h Hunter) Hunt(lion ILion) {}

type WildDog struct{}

func (w WildDog) bark() {}

type WildDogAdapter struct {
dog WildDog
}

func (w WildDogAdapter) Roar() {
w.dog.bark()
}

func main() {
wildDog := WildDog{}
wildDogAdapter := WildDogAdapter{wildDog}

hunter := Hunter{}
hunter.Hunt(wildDogAdapter)

fmt.Println("Done")
}

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface Lion {
    
    void roar();
}

class AfricanLion implements Lion {

    @Override
    public void roar() {
        System.out.println("African lion roaring.");
    }
}

class AsianLion implements Lion {

    @Override
    public void roar() {
        System.out.println("Asian lion roaring.");
    }
}

class Hunter {
    
    public void Hunt(Lion lion) {
        System.out.println("Attacking and listening...🦻");
        lion.roar();
    }
}

class WildDog {
    
    public void bark() {
        System.out.println("Wild dog barking");
    }
}

// Adapter around wild dog to make it compatible
class WildDogAdapter implements Lion {
    private WildDog wildDog;

    public WildDogAdapter(WildDog wildDog) {
        this.wildDog = wildDog;
    }
    public void roar() {
        wildDog.bark();
    }
}

----------------------------

WildDog wildDog = new WildDog();
WildDogAdapter wildDogAdapter = new WildDogAdapter(wildDog);

Hunter hunter = new Hunter();
hunter.Hunt(wildDogAdapter);
```

</div>

</details>

<br>

---

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

![With and without the bridge pattern](images/without_bridge.png)

به زبون ساده:

> این الگوی طراحی درمورد **ترجیح دادن** `ترکیب` **نسبت به** `ارث‌بری` صحبت میکنه.

ویکی پدیا:

<div dir="ltr">

> The bridge pattern is a design pattern used in software engineering that is meant to "decouple an abstraction from its
> implementation so that the two can vary independently"

</div>

**مثال برنامه نویسی**

بیاید همون مثال سایت و قالب که بالاتر درموردش صحبت کردیم رو پیاده‌سازی کنیم.

در مرحله اول کلاس `WebPage` و پیاده‌سازی‌هایی از اون رو داریم.

برای قالب هم، باید کلاس و پیاده سازی‌های مختلفی بنویسیم:

<details>
<summary>Python</summary>

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


----------------------------

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
<div dir="ltr">

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

----------------------------

const darkTheme = new DarkTheme();

const about = new About(darkTheme);
const careers = new Careers(darkTheme);

console.log(about.getContent());
console.log(careers.getContent());
```

</div>

</details>

<details>
<summary>Javascript</summary>
<div dir="ltr">

```javascript


class WebPage {
    constructor(theme) {
        this._theme = theme;
    }

    getContent() {
        return "";
    }
}

class About extends WebPage {
    getContent() {
        return `About page in ${this._theme.getColor()}`;
    }
}

class Careers extends WebPage {
    getContent() {
        return `Careers page in ${this._theme.getColor()}`;
    }
}

class Theme {
    getColor() {
        return "";
    }
}

class DarkTheme extends Theme {
    getColor() {
        return "Dark Black";
    }
}

class LightTheme extends Theme {
    getColor() {
        return "Off White";
    }
}

class AquaTheme extends Theme {
    getColor() {
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

<details>
<summary >#C</summary>

<div dir="ltr">

```C#

interface IWebPage
{
  string GetContent();
}

class About : IWebPage
{
  protected ITheme theme;

  public About(ITheme theme)
  {
    this.theme = theme;
  }

  public string GetContent()
  {
    return $"About page in {theme.GetColor()}";
  }
}

class Careers : IWebPage
{
  protected ITheme theme;

  public Careers(ITheme theme)
  {
    this.theme = theme;
  }

  public string GetContent()
  {
    return $"Careers page in {theme.GetColor()}";
  }
}


interface ITheme
{
  string GetColor();
}

class DarkTheme : ITheme
{
  public string GetColor()
  {
    return "Dark Black";
  }
}

class LightTheme : ITheme
{
  public string GetColor()
  {
    return "Off White";
  }
}

class AquaTheme : ITheme
{
  public string GetColor()
  {
    return "Light blue";
  }
}

----------------------------

var darkTheme = new DarkTheme();
var lightTheme = new LightTheme();

var about= new About(darkTheme);
var careers = new Careers(lightTheme);

Console.WriteLine(about.GetContent()); //Output: About page in Dark Black
Console.WriteLine(careers.GetContent()); //Output: Careers page in Off White

```

</div>

</details>

<details>
<summary>PHP</summary>
<div dir="ltr">

```PHP
interface WebPageInterface {
  public function getContent();
}

class About implements WebPageInterface {
  protected $theme;

  public function __construct(ThemeInterface $theme) {
    $this->theme = $theme;
  }

  public function getContent() {
    return "About page in " . $this->theme->getColor();
  }
}

class Careers implements WebPageInterface {
  protected $theme;

  public function __construct(ThemeInterface $theme) {
    $this->theme = $theme;
  }

  public function getContent() {
    return "Careers page in " . $this->theme->getColor();
  }
}

interface ThemeInterface {
  public function getColor();
}

class DarkTheme implements ThemeInterface {
  public function getColor() {
    return "Dark Black";
  }
}

class LightTheme implements ThemeInterface {
  public function getColor() {
    return "Off White";
  }
}

class AquaTheme implements ThemeInterface {
  public function getColor() {
    return "Light Blue";
  }
}

$darkTheme = new DarkTheme();
$lightTheme = new LightTheme();

$about = new About($darkTheme);
$careers = new Careers($lightTheme);

echo $about->getColor() . "\n"; //Output: About page in Dark Black
echo $careers->getColor() . "\n"; //Output: Careers page in Off White

```

</div>

</details>

<details>
<summary>Go</summary>
<div dir="ltr">

```go
package main

import "fmt"

type IWebPage interface {
GetContent() string
}

type About struct {
theme ITheme
}

func NewAbout(theme ITheme) *About {
return &About{theme: theme}
}

func (a *About) GetContent() string {
return fmt.Sprintf("About page in %s", a.theme.GetColor())
}

type Careers struct {
theme ITheme
}

func NewCareers(theme ITheme) *Careers {
return &Careers{theme: theme}
}

func (c *Careers) GetContent() string {
return fmt.Sprintf("Careers page in %s", c.theme.GetColor())
}

type ITheme interface {
GetColor() string
}

type DarkTheme struct{}

func (d *DarkTheme) GetColor() string {
return "Dark Black"
}

type LightTheme struct{}

func (l *LightTheme) GetColor() string {
return "Off White"
}

type AquaTheme struct{}

func (a *AquaTheme) GetColor() string {
return "Light blue"
}

func main() {
darkTheme := &DarkTheme{}
lightTheme := &LightTheme{}

about := NewAbout(darkTheme)
careers := NewCareers(lightTheme)

fmt.Println(about.GetContent())   // Output: About page in Dark Black
fmt.Println(careers.GetContent()) // Output: Careers page in Off White
}
```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface WebPage {
    String getContent();
}

interface Theme {
    String getColor();
}

class About implements WebPage {
    private Theme theme;

    public About(Theme theme) {
        this.theme = theme;
    }

    public String getContent() {
        return "About page in " + theme.getColor();
    }
}

class Careers implements WebPage {
    private Theme theme;

    public Careers(Theme theme) {
        this.theme = theme;
    }

    public String getContent(){
        return "Careers page in "+ theme.getColor();
    }
}

class DarkTheme implements Theme {
    public String getColor() {
        return "Dark theme";
    }
}

class LightTheme implements Theme {
    public String getColor() {
        return "Light theme";
    }
}

----------------------------
    
DarkTheme darkTheme = new DarkTheme();
LightTheme lightTheme = new LightTheme();

About about= new About(darkTheme);
Careers careers = new Careers(lightTheme);

System.out.println(about.getContent());     // About page in Dark theme
System.out.println(careers.getContent());   // Careers page in Light theme
```

</div>

</details>

<br>

---

<div align="center">

## 🌿 Composite

</div>

یک مثال از دنیای واقعی:

> فرض کنید شما یک کلاس ارسال مرسوله طراحی میکنید:
> 
> ![Composite](images/Composite.png)
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

بطور کلی توی دیزاین پترن composite ما دو مدل دیتا داریم:

یک: اینکه Composite که میتونه برای خودش زیرمجموعه داشته باشه. (هرچند خودش هم وظایفی داشته باشه)

دو: Leaf که در واقع زیر مجموعه نداره و فقط یک سری وظیفه داره.

خب اول بیایم یک اینترفیس پایه برای کامپوننت‌هامون بسازیم و در ادامه هم اینترفیس‌های Composite و Leaf رو بسازیم:

<details>

<summary>Python</summary>

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


----------------------------

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

----------------------------

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

<details>

<summary>Javascript</summary>

<div dir="ltr">

```javascript
class Leaf {
    operation() {
        return "Leaf";
    }
}

class Composite {
    constructor() {
        this.children = [];
    }

    add(component) {
        this.children.push(component);
    }

    remove(component) {
        const index = this.children.indexOf(component);
        if (index !== -1) {
            this.children.splice(index, 1);
        }
    }

    operation() {
        const results = [];
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
// Output: RESULT: Branch(Branch(Leaf+Leaf)+Branch(Leaf))
```

</div>

</details>

<details>
<summary >#C</summary>

<div dir="ltr">

```C#

interface IEmployee
{
  float GetSalary();
  string GetRole();
  string GetName();
}


class Developer : IEmployee
{
  private string mName;
  private float mSalary;

  public Developer(string name, float salary)
  {
    this.mName = name;
    this.mSalary = salary;
  }

  public float GetSalary()
  {
    return this.mSalary;
  }

  public string GetRole()
  {
    return "Developer";
  }

  public string GetName()
  {
    return this.mName;
  }
}

class Designer : IEmployee
{
  private string mName;
  private float mSalary;

  public Designer(string name, float salary)
  {
    this.mName = name;
    this.mSalary = salary;
  }

  public float GetSalary()
  {
    return this.mSalary;
  }

  public string GetRole()
  {
    return "Designer";
  }

  public string GetName()
  {
    return this.mName;
  }
}


class Organization
{
  protected List<IEmployee> employees;

  public Organization()
  {
    employees = new List<IEmployee>();
  }

  public void AddEmployee(IEmployee employee)
  {
    employees.Add(employee);
  }

  public float GetNetSalaries()
  {
    float netSalary = 0;

    foreach (var e in employees) {
      netSalary += e.GetSalary();
    }
    return netSalary;
  }
}

----------------------------

//Arrange Employees, Organization and add employees
var developer = new Developer("John", 5000);
var designer = new Designer("Arya", 5000);

var organization = new Organization();
organization.AddEmployee(developer);
organization.AddEmployee(designer);

Console.WriteLine($"Net Salary of Employees in Organization is {organization.GetNetSalaries():c}");
//Ouptut: Net Salary of Employees in Organization is $10000.00

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```PHP
interface EmployeeInterface {
  function getSalary(): float;
  function getRole(): string;
  function getName(): string;
}

class Developer implements EmployeeInterface {
  private string $name;
  private float $salary;

  public function __construct(string $name, float $salary) {
    $this->name = $name;
    $this->salary = $salary;
  }

  public function getSalary(): float {
    return $this->salary;
  }

  public function getRole(): string {
    return "Developer";
  }

  public function getName(): string {
    return $this->name;
  }
}

class Designer implements EmployeeInterface {
  private string $name;
  private float $salary;

  public function __construct(string $name, float $salary) {
    $this->name = $name;
    $this->salary = $salary;
  }

  public function getSalary(): float {
    return $this->salary;
  }

  public function getRole(): string {
    return "Designer";
  }

  public function getName(): string {
    return $this->name;
  }
}

class Organization {
  protected array $employees;

  public function __construct() {
    $this->employees = array();
  }

  public function addEmployee(EmployeeInterface $employee): void {
    $this->employees[] = $employee;
  }

  public function getNetSalaries(): float {
    $netSalary = 0;
    foreach ($this->employees as $e) {
      $netSalary += $e->getSalary();
    }
    return $netSalary;
  }
}

// Arrange Employees, Organization, and add employees
$developer = new Developer("John", 5000);
$designer = new Designer("Aria", 5000);

$organization = new Organization();
$organization->addEmployee($developer);
$organization->addEmployee($designer);

echo "Net Salary of Employees in Organization is " . number_format($organization->getNetSalaries(), 2, '.', ',') . PHP_EOL;
// Output: Net Salary of Employees in Organization is $10,000.00

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import "fmt"

type IEmployee interface {
    GetSalary() float32
    GetRole() string
    GetName() string
}

type Developer struct {
    Name   string
    Salary float32
}

func (d *Developer) GetSalary() float32 {
    return d.Salary
}

func (d *Developer) GetRole() string {
    return "Developer"
}

func (d *Developer) GetName() string {
    return d.Name
}

type Designer struct {
    Name   string
    Salary float32
}

func (d *Designer) GetSalary() float32 {
    return d.Salary
}

func (d *Designer) GetRole() string {
    return "Designer"
}

func (d *Designer) GetName() string {
    return d.Name
}

type Organization struct {
    employees []IEmployee
}

func (o *Organization) AddEmployee(employee IEmployee) {
    o.employees = append(o.employees, employee)
}

func (o *Organization) GetNetSalaries() float32 {
    netSalary := float32(0)
    for _, e := range o.employees {
        netSalary += e.GetSalary()
    }
    return netSalary
}

func main() {
    //Arrange Employees, Organization and add employees
    developer := &Developer{Name: "John", Salary: 5000}
    designer := &Designer{Name: "Arya", Salary: 5000}

    organization := &Organization{}
    organization.AddEmployee(developer)
    organization.AddEmployee(designer)

    fmt.Printf("Net Salary of Employees in Organization is %v\n", organization.GetNetSalaries())
    //Output: Net Salary of Employees in Organization is 10000
}

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface Employee {

    float getSalary();
    String getRole();
    String getName();
}

class Developer implements Employee {
    private String name;
    private float salary;

    public Developer(String name, float salary) {
        this.name = name;
        this.salary = salary;
    }

    public float getSalary() {
        return this.salary;
    }
    public String getRole() {
        return "Developer";
    }
    public String getName() {
        return this.name;
    }
}

class Designer implements Employee {
    private String name;
    private float salary;

    public Designer(String name, float salary) {
        this.name = name;
        this.salary = salary;
    }

    public float getSalary() {
        return this.salary;
    }
    public String getRole() {
        return "Designer";
    }
    public String getName() {
        return this.name;
    }
}

class Organization {
    protected List<Employee> employees;

    public Organization() {
        employees = new ArrayList<>();
    }

    public void addEmployee(Employee employee) {
        employees.add(employee);
    }

    public float getNetSalaries() {
        float netSalary = 0;

        for(Employee employee : employees) {
            netSalary += employee.getSalary();
        }
        return netSalary;
    }
}

----------------------------

Developer developer = new Developer("John",5000);
Designer designer = new Designer("Arya",5000);

Organization organization = new Organization();
organization.addEmployee(developer);
organization.addEmployee(designer);

System.out.println("Organization employees salary : " + organization.getNetSalaries());
// Organization employees salary : 10000.0
```

</div>

</details>

<br>

---

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

برای مثال قهوه را در نظر بگیرید. اول از همه ما یک قهوه ساده داریم که رابط قهوه را پیاده سازی می کند.

ما می‌خوایم کد رو توسعه‌پذیر کنیم تا در صورت نیاز، گزینه‌ها بتونند اون رو تغییر بدند.

پس بیاید چند دکوریتور براش بسازیم.

همونطور که میبینید خیلی ساده میتونیم هر ابجکت رو به عنوان ورودی تابع بعدی بدیم و اینطوری چندین مرحله افزودنی رو خیلی
راحت به ابجکتمون اضافه کردیم!

<details>
<summary>Python</summary>

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


----------------------------

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

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
abstract class Coffee {
    abstract getCost(): number;

    abstract getDescription(): string;
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

----------------------------

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

<details>
<summary>Javascript</summary>
<div dir="ltr">

```javascript
class Coffee {
    getCost() {
        throw new Error("getCost() must be implemented by subclasses");
    }

    getDescription() {
        throw new Error("getDescription() must be implemented by subclasses");
    }
}

class SimpleCoffee extends Coffee {
    getCost() {
        return 10;
    }

    getDescription() {
        return "Simple Coffee";
    }
}

class MilkCoffee extends Coffee {
    constructor(coffee) {
        super();
        this.coffee = coffee;
    }

    getCost() {
        return this.coffee.getCost() + 2;
    }

    getDescription() {
        return this.coffee.getDescription() + ", milk";
    }
}

class WhipCoffee extends Coffee {
    constructor(coffee) {
        super();
        this.coffee = coffee;
    }

    getCost() {
        return this.coffee.getCost() + 5;
    }

    getDescription() {
        return this.coffee.getDescription() + ", whip";
    }
}

class VanillaCoffee extends Coffee {
    constructor(coffee) {
        super();
        this.coffee = coffee;
    }

    getCost() {
        return this.coffee.getCost() + 3;
    }

    getDescription() {
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

<details>
<summary >#C</summary>

<div dir="ltr">

```C#

interface ICoffee
{
  int GetCost();
  string GetDescription();
}

class SimpleCoffee : ICoffee
{
  public int GetCost()
  {
    return 5;
  }

  public string GetDescription()
  {
    return "Simple Coffee";
  }
}

class MilkCoffee : ICoffee
{
  private readonly ICoffee mCoffee;

  public MilkCoffee(ICoffee coffee)
  {
    mCoffee = coffee ?? throw new ArgumentNullException("coffee", "coffee should not be null");
  }
  public int GetCost()
  {
    return mCoffee.GetCost() + 1;
  }

  public string GetDescription()
  {
    return String.Concat(mCoffee.GetDescription(), ", milk");
  }
}

class WhipCoffee : ICoffee
{
  private readonly ICoffee mCoffee;

  public WhipCoffee(ICoffee coffee)
  {
    mCoffee = coffee ?? throw new ArgumentNullException("coffee", "coffee should not be null");
  }
  public int GetCost()
  {
    return mCoffee.GetCost() + 1;
  }

  public string GetDescription()
  {
    return String.Concat(mCoffee.GetDescription(), ", whip");
  }
}

class VanillaCoffee : ICoffee
{
  private readonly ICoffee mCoffee;

  public VanillaCoffee(ICoffee coffee)
  {
    mCoffee = coffee ?? throw new ArgumentNullException("coffee", "coffee should not be null");
  }
  public int GetCost()
  {
    return mCoffee.GetCost() + 1;
  }

  public string GetDescription()
  {
    return String.Concat(mCoffee.GetDescription(), ", vanilla");
  }
}


----------------------------

var myCoffee = new SimpleCoffee();
Console.WriteLine($"{myCoffee.GetCost():c}"); // $ 5.00
Console.WriteLine(myCoffee.GetDescription()); // Simple Coffee

var milkCoffee = new MilkCoffee(myCoffee);
Console.WriteLine($"{milkCoffee.GetCost():c}"); // $ 6.00
Console.WriteLine(milkCoffee.GetDescription()); // Simple Coffee, milk

var whipCoffee = new WhipCoffee(milkCoffee);
Console.WriteLine($"{whipCoffee.GetCost():c}"); // $ 7.00
Console.WriteLine(whipCoffee.GetDescription()); // Simple Coffee, milk, whip

var vanillaCoffee = new VanillaCoffee(whipCoffee);
Console.WriteLine($"{vanillaCoffee.GetCost():c}"); // $ 8.00
Console.WriteLine(vanillaCoffee.GetDescription()); // Simple Coffee, milk, whip, vanilla

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```PHP
interface CoffeeInterface {
  public function getCost();
  public function getDescription();
}

class SimpleCoffee implements CoffeeInterface {
  public function getCost() {
    return 5;
  }

  public function getDescription() {
    return "Simple Coffee";
  }
}

class MilkCoffee implements CoffeeInterface {
  private $coffee;

  public function __construct(CoffeeInterface $coffee) {
    $this->coffee = $coffee ?? throw new Exception("coffee should not be null");
  }

  public function getCost() {
    return $this->coffee->getCost() + 1;
  }

  public function getDescription() {
    return $this->coffee->getDescription() . ", milk";
  }
}

class WhipCoffee implements CoffeeInterface {
  private $coffee;

  public function __construct(CoffeeInterface $coffee) {
    $this->coffee = $coffee ?? throw new Exception("coffee should not be null");
  }

  public function getCost() {
    return $this->coffee->getCost() + 1;
  }

  public function getDescription() {
    return $this->coffee->getDescription() . ", whip";
  }
}

class VanillaCoffee implements CoffeeInterface {
  private $coffee;

  public function __construct(CoffeeInterface $coffee) {
    $this->coffee = $coffee ?? throw new Exception("coffee should not be null");
  }

  public function getCost() {
    return $this->coffee->getCost() + 1;
  }

  public function getDescription() {
    return $this->coffee->getDescription() . ", vanilla";
  }
}

$myCoffee = new SimpleCoffee();
echo "$" . number_format($myCoffee->getCost(), 2) . "\n"; // $5.00
echo $myCoffee->getDescription() . "\n"; // Simple Coffee

$milkCoffee = new MilkCoffee($myCoffee);
echo "$" . number_format($milkCoffee->getCost(), 2) . "\n"; // $6.00
echo $milkCoffee->getDescription() . "\n"; // Simple Coffee, milk

$whipCoffee = new WhipCoffee($milkCoffee);
echo "$" . number_format($whipCoffee->getCost(), 2) . "\n"; // $7.00
echo $whipCoffee->getDescription() . "\n"; // Simple Coffee, milk, whip

$vanillaCoffee = new VanillaCoffee($whipCoffee);
echo "$" . number_format($vanillaCoffee->getCost(), 2) . "\n"; // $8.00
echo $vanillaCoffee->getDescription() . "\n"; // Simple Coffee, milk, whip, vanilla

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import (
	"fmt"
)

type ICoffee interface {
	GetCost() int
	GetDescription() string
}

type SimpleCoffee struct{}

func (c *SimpleCoffee) GetCost() int {
	return 5
}

func (c *SimpleCoffee) GetDescription() string {
	return "Simple Coffee"
}

type MilkCoffee struct {
	coffee ICoffee
}

func NewMilkCoffee(coffee ICoffee) *MilkCoffee {
	if coffee == nil {
		panic("coffee should not be nil")
	}
	return &MilkCoffee{coffee: coffee}
}

func (c *MilkCoffee) GetCost() int {
	return c.coffee.GetCost() + 1
}

func (c *MilkCoffee) GetDescription() string {
	return fmt.Sprintf("%s, milk", c.coffee.GetDescription())
}

type WhipCoffee struct {
	coffee ICoffee
}

func NewWhipCoffee(coffee ICoffee) *WhipCoffee {
	if coffee == nil {
		panic("coffee should not be nil")
	}
	return &WhipCoffee{coffee: coffee}
}

func (c *WhipCoffee) GetCost() int {
	return c.coffee.GetCost() + 1
}

func (c *WhipCoffee) GetDescription() string {
	return fmt.Sprintf("%s, whip", c.coffee.GetDescription())
}

type VanillaCoffee struct {
	coffee ICoffee
}

func NewVanillaCoffee(coffee ICoffee) *VanillaCoffee {
	if coffee == nil {
		panic("coffee should not be nil")
	}
	return &VanillaCoffee{coffee: coffee}
}

func (c *VanillaCoffee) GetCost() int {
	return c.coffee.GetCost() + 1
}

func (c *VanillaCoffee) GetDescription() string {
	return fmt.Sprintf("%s, vanilla", c.coffee.GetDescription())
}

func main() {
	myCoffee := &SimpleCoffee{}
	fmt.Printf("%s\n", myCoffee.GetCost())
	fmt.Printf("%s\n", myCoffee.GetDescription())

	milkCoffee := NewMilkCoffee(myCoffee)
	fmt.Printf("%s\n", milkCoffee.GetCost())
	fmt.Printf("%s\n", milkCoffee.GetDescription())

	whipCoffee := NewWhipCoffee(milkCoffee)
	fmt.Printf("%s\n", whipCoffee.GetCost())
	fmt.Printf("%s\n", whipCoffee.GetDescription())

	vanillaCoffee := NewVanillaCoffee(whipCoffee)
	fmt.Printf("%s\n", vanillaCoffee.GetCost())
	fmt.Printf("%s\n", vanillaCoffee.GetDescription())
}


```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface Coffee {
    
    int getCost();
    String getDescription();
}

class SimpleCoffee implements Coffee {
    
    public int getCost() {
        return 5;
    }

    public String getDescription() {
        return "Simple Coffee";
    }
}

class MilkCoffee implements Coffee {
    private final Coffee coffee;

    public MilkCoffee(Coffee coffee) {
        if(coffee == null)
            throw new IllegalArgumentException("coffee should not be null");
        this.coffee = coffee;
    }

    public int getCost() {
        return coffee.getCost() + 1;
    }

    public String getDescription() {
        return coffee.getDescription() + ", Milk";
    }
}

class WhipCoffee implements Coffee {
    private final Coffee coffee;

    public WhipCoffee(Coffee coffee) {
        if(coffee == null)
            throw new IllegalArgumentException("coffee should not be null");
        this.coffee = coffee;
    }

    public int getCost() {
        return coffee.getCost() + 1;
    }

    public String getDescription() {
        return coffee.getDescription() + ", Whip";
    }
}

class VanillaCoffee implements Coffee {
    private final Coffee coffee;

    public VanillaCoffee(Coffee coffee) {
        if(coffee == null)
            throw new IllegalArgumentException("coffee should not be null");
        this.coffee = coffee;
    }

    public int getCost() {
        return coffee.getCost() + 1;
    }

    public String getDescription() {
        return coffee.getDescription() + ", Vanilla";
    }
}

----------------------------

SimpleCoffee simpleCoffee = new SimpleCoffee();
System.out.println("$" + simpleCoffee.getCost()); // $5
System.out.println(simpleCoffee.getDescription()); // Simple Coffee

MilkCoffee milkCoffee = new MilkCoffee(simpleCoffee);
System.out.println("$" + milkCoffee.getCost()); // $6
System.out.println(milkCoffee.getDescription()); // Simple Coffee, Milk

WhipCoffee whipCoffee = new WhipCoffee(milkCoffee);
System.out.println("$" + whipCoffee.getCost()); // $7
System.out.println(whipCoffee.getDescription()); // Simple Coffee, Milk, Whip

VanillaCoffee vanillaCoffee = new VanillaCoffee(whipCoffee);
System.out.println("$" + vanillaCoffee.getCost()); // $8
System.out.println(vanillaCoffee.getDescription()); // Simple Coffee, Milk, Whip, Vanilla
```

</div>

</details>

<br>

---

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

بیاین همون مثال مربوط به کامپیوتر رو پیاده‌سازی کنیم!

اول باید کلاس کامپیوتر رو بسازیم.

کلاس Facade به این صورت پیاده‌سازی میشه که یک ابجکت رو به عنوان ورودی دریافت میکنه و با هر تابع خودش یک سری عملیات رو
روی اون ابجکت اعمال میکنه.

<details>

<summary>Python</summary>

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


----------------------------

computer = ComputerFacade(Computer())
computer.turnOn()
computer.turnOff()

'''
Output will be
==============
Ouch!
Beep Beep!
Loading...
Ready to be used...
Bup bup bup buzzz!
Haaah!
Zzzzz
'''
```

</div>

</details>

<details>

<summary>TypeScript</summary>

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

----------------------------

    let
computer = new ComputerFacade(new Computer());
computer.turnOn();
computer.turnOff();
```

</div>

</details>

<details>

<summary>JavaScript</summary>

<div dir="ltr">

```javascript

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
    constructor(computer) {
        this.computer = computer;
    }

    set computer(computer) {
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

const computer = new ComputerFacade(new Computer());
computer.turnOn();
computer.turnOff();
```

</div>

</details>

<details>
<summary >#C</summary>

<div dir="ltr">

```C#

class Computer
{
  public void GetElectricShock()
  {
    Console.Write("Ouch!");
  }

  public void MakeSound()
  {
    Console.Write("Beep beep!");
  }

  public void ShowLoadingScreen()
  {
    Console.Write("Loading..");
  }

  public void Bam()
  {
    Console.Write("Ready to be used!");
  }

  public void CloseEverything()
  {
    Console.Write("Bup bup bup buzzzz!");
  }

  public void Sooth()
  {
    Console.Write("Zzzzz");
  }

  public void PullCurrent()
  {
    Console.Write("Haaah!");
  }
}


class ComputerFacade
{
  private readonly Computer mComputer;

  public ComputerFacade(Computer computer)
  {
    this.mComputer = computer ?? throw new ArgumentNullException("computer", "computer cannot be null");
  }

  public void TurnOn()
  {
    mComputer.GetElectricShock();
    mComputer.MakeSound();
    mComputer.ShowLoadingScreen();
    mComputer.Bam();
  }

  public void TurnOff()
  {
    mComputer.CloseEverything();
    mComputer.PullCurrent();
    mComputer.Sooth();
  }
}

----------------------------

var computer = new ComputerFacade(new Computer());
computer.TurnOn(); // Ouch! Beep beep! Loading.. Ready to be used!
Console.WriteLine();
computer.TurnOff();  // Bup bup buzzz! Haah! Zzzzz
Console.ReadLine();

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```PHP
class Computer
{
  public function getElectricShock()
  {
    echo "Ouch!";
  }

  public function makeSound()
  {
    echo "Beep beep!";
  }

  public function showLoadingScreen()
  {
    echo "Loading..";
  }

  public function bam()
  {
    echo "Ready to be used!";
  }

  public function closeEverything()
  {
    echo "Bup bup bup buzzzz!";
  }

  public function sooth()
  {
    echo "Zzzzz";
  }

  public function pullCurrent()
  {
    echo "Haaah!";
  }
}

class ComputerFacade
{
  public function __construct(private Computer $computer)
  {
  }

  public function turnOn()
  {
    $this->computer->getElectricShock();
    $this->computer->makeSound();
    $this->computer->showLoadingScreen();
    $this->computer->bam();
  }

  public function turnOff()
  {
    $this->computer->closeEverything();
    $this->computer->pullCurrent();
    $this->computer->sooth();
  }
}

$computerFacade = new ComputerFacade(new Computer());
$computerFacade->turnOn(); // Ouch! Beep beep! Loading.. Ready to be used!
echo PHP_EOL;
$computerFacade->turnOff();  // Bup bup buzzz! Haah! Zzzzz

```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go

package main

import (
    "fmt"
)

type computer struct{}

func (c *computer) getElectricShock() {
    fmt.Print("Ouch!")
}

func (c *computer) makeSound() {
    fmt.Print("Beep beep!")
}

func (c *computer) showLoadingScreen() {
    fmt.Print("Loading..")
}

func (c *computer) bam() {
    fmt.Print("Ready to be used!")
}

func (c *computer) closeEverything() {
    fmt.Print("Bup bup bup buzzzz!")
}

func (c *computer) soothe() {
    fmt.Print("Zzzzz")
}

func (c *computer) pullCurrent() {
    fmt.Print("Haaah!")
}

type computerFacade struct {
    computer *computer
}

func newComputerFacade(c *computer) *computerFacade {
    if c == nil {
        panic("computer cannot be nil")
    }
    return &computerFacade{computer: c}
}

func (cf *computerFacade) turnOn() {
    cf.computer.getElectricShock()
    cf.computer.makeSound()
    cf.computer.showLoadingScreen()
    cf.computer.bam()
}

func (cf *computerFacade) turnOff() {
    cf.computer.closeEverything()
    cf.computer.pullCurrent()
    cf.computer.soothe()
}

func main() {
    c := newComputerFacade(&computer{})
    c.turnOn() // Ouch! Beep beep! Loading.. Ready to be used!
    fmt.Println()
    c.turnOff() // Bup bup buzzz! Haah! Zzzzz
}

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
class Computer {
    public void getElectricShock() {
        System.out.println("Ouch!");
    }

    public void makeSound() {
        System.out.println("Beep beep!");
    }

    public void showLoadingScreen() {
        System.out.println("Loading..");
    }

    public void bam() {
        System.out.println("Ready to be used!");
    }

    public void closeEverything() {
        System.out.println("Bup bup bup buzzzz!");
    }

    public void sooth() {
        System.out.println("Zzzzz");
    }

    public void pullCurrent() {
        System.out.println("Haaah!");
    }
}

class ComputerFacade {
    private Computer computer;

    public ComputerFacade(Computer computer) {
        if (computer == null)
            throw new IllegalArgumentException("computer cannot be null");
        this.computer = computer;
    }

    public void turnOn() {
        computer.getElectricShock();
        computer.makeSound();
        computer.showLoadingScreen();
        computer.bam();
    }

    public void turnOff() {
        computer.closeEverything();
        computer.pullCurrent();
        computer.sooth();
    }
}

----------------------------

ComputerFacade computer = new ComputerFacade(new Computer());
computer.turnOn();      // Ouch! Beep beep! Loading.. Ready to be used!
System.out.println();
computer.turnOff();     // Bup bup buzzz! Haah! Zzzzz
System.out.println();
```

</div>

</details>

<br>

---

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

بیاین مثال غرفه چای رو پیاده سازی کنیم. اول باید انواع چای و چای ساز رو پیاده سازی کنیم.

توی مرحله بعد ما یک کلاس `TeaShop` داریم که وظیفه ثبت سفارش و آماده کردن اون‌هارو به عهده داره.

<details>
<summary>Python</summary>

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


----------------------------

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
class GreenTea {
}

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

----------------------------

    let
teaMaker = new TeaMaker();
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

<details>

<summary>JavaScript</summary>

<div dir="ltr">

```javascript

class GreenTea {
}

class TeaMaker {
    constructor() {
        this.availableTea = {};
    }

    make(preference) {
        if (!(preference in this.availableTea)) {
            this.availableTea[preference] = new GreenTea();
        }

        return this.availableTea[preference];
    }
}

class TeaShop {
    constructor(teaMaker) {
        this.orders = {};
        this.teaMaker = teaMaker;
    }

    takeOrder(teaType, table) {
        this.orders[table] = this.teaMaker.make(teaType);
    }

    serve() {
        for (const table in this.orders) {
            const tea = this.orders[table];
            console.log(`Serving tea to table #${table}`);
        }
    }
}


const teaMaker = new TeaMaker();
const shop = new TeaShop(teaMaker);

shop.takeOrder("less sugar", 1);
shop.takeOrder("more milk", 2);
shop.takeOrder("without sugar", 5);

shop.serve();
// Serving tea to table #1
// Serving tea to table #2
// Serving tea to table #5
```

</div>

</details>

<details>
<summary >#C</summary>

<div dir="ltr">

```C#

// Anything that will be cached is flyweight.
// Types of tea here will be flyweights.
class KarakTea
{
}

// Acts as a factory and saves the tea
class TeaMaker
{
  private Dictionary<string,KarakTea> mAvailableTea = new Dictionary<string,KarakTea>();

  public KarakTea Make(string preference)
  {
    if (!mAvailableTea.ContainsKey(preference))
    {
      mAvailableTea[preference] = new KarakTea();
    }

    return mAvailableTea[preference];
  }
}

class TeaShop
{
  private Dictionary<int,KarakTea> mOrders = new Dictionary<int,KarakTea>();
  private readonly TeaMaker mTeaMaker;

  public TeaShop(TeaMaker teaMaker)
  {
    mTeaMaker = teaMaker ?? throw new ArgumentNullException("teaMaker", "teaMaker cannot be null");
  }

  public void TakeOrder(string teaType, int table)
  {
    mOrders[table] = mTeaMaker.Make(teaType);
  }

  public void Serve()
  {
    foreach(var table  in mOrders.Keys){
      Console.WriteLine($"Serving Tea to table # {table}");
    }
  }
}

----------------------------

var teaMaker = new TeaMaker();
var teaShop = new TeaShop(teaMaker);

teaShop.TakeOrder("less sugar", 1);
teaShop.TakeOrder("more milk", 2);
teaShop.TakeOrder("without sugar", 5);

teaShop.Serve();
// Serving tea to table# 1
// Serving tea to table# 2
// Serving tea to table# 5

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```PHP
// Anything that will be cached is flyweight.
// Types of tea here will be flyweights.
class KarakTea
{
}

// Acts as a factory and saves the tea
class TeaMaker
{
  private array $mAvailableTea = [];

  public function make(string $preference): KarakTea
  {
    if (!array_key_exists($preference, $this->mAvailableTea)) {
      $this->mAvailableTea[$preference] = new KarakTea();
    }

    return $this->mAvailableTea[$preference];
  }
}

class TeaShop
{
  private array $mOrders = [];

  public function __construct(private TeaMaker $teaMaker)
  {
  }

  public function takeOrder(string $teaType, int $table): void
  {
    $this->mOrders[$table] = $this->teaMaker->make($teaType);
  }

  public function serve(): void
  {
    foreach ($this->mOrders as $table => $tea) {
      echo "Serving tea to table # $table\n";
    }
  }
}

$teaMaker = new TeaMaker();
$teaShop = new TeaShop($teaMaker);

$teaShop->takeOrder("less sugar", 1);
$teaShop->takeOrder("more milk", 2);
$teaShop->takeOrder("without sugar", 5);

$teaShop->serve();
// Serving tea to table# 1
// Serving tea to table# 2
// Serving tea to table# 5


```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go

type KarakTea struct {}

type TeaMaker struct {
    mAvailableTea map[string]*KarakTea
}

func (tm *TeaMaker) Make(preference string) *KarakTea {
    if tm.mAvailableTea == nil {
        tm.mAvailableTea = make(map[string]*KarakTea)
    }
    if _, ok := tm.mAvailableTea[preference]; !ok {
        tm.mAvailableTea[preference] = &KarakTea{}
    }
    return tm.mAvailableTea[preference]
}

type TeaShop struct {
    mOrders map[int]*KarakTea
    mTeaMaker *TeaMaker
}

func NewTeaShop(teaMaker *TeaMaker) *TeaShop {
    if teaMaker == nil {
        panic("teaMaker cannot be nil")
    }
    return &TeaShop{
        mOrders: make(map[int]*KarakTea),
        mTeaMaker: teaMaker,
    }
}

func (ts *TeaShop) TakeOrder(teaType string, table int) {
    ts.mOrders[table] = ts.mTeaMaker.Make(teaType)
}

func (ts *TeaShop) Serve() {
    for table := range ts.mOrders {
        fmt.Printf("Serving Tea to table # %d\n", table)
    }
}
---------------------------
teaMaker := &TeaMaker{}
teaShop := NewTeaShop(teaMaker)

teaShop.TakeOrder("less sugar", 1)
teaShop.TakeOrder("more milk", 2)
teaShop.TakeOrder("without sugar", 5)

teaShop.Serve()
// Serving Tea to table # 1
// Serving Tea to table # 2
// Serving Tea to table # 5

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
// Anything that will be cached is flyweight.
// Types of tea here will be flyweights.
class KarakTea {
}

// Acts as a factory and saves the tea
class TeaMaker {
    private Map<String, KarakTea> availableTea = new HashMap<>();

    public KarakTea make(String preference) {
        if (!availableTea.containsKey(preference)) {
            availableTea.put(preference, new KarakTea());
        }
        return availableTea.get(preference);
    }
}

class TeaShop {
    private Map<Integer, KarakTea> orders = new HashMap<>();
    private TeaMaker teaMaker;

    public TeaShop(TeaMaker teaMaker) {
        if(teaMaker == null)
            throw new IllegalArgumentException("teaMaker cannot be null");
        this.teaMaker = teaMaker;
    }

    public void takeOrder(String teaType, int table) {
        orders.put(table, teaMaker.make(teaType));
    }

    public void serve() {
        for(Integer tableNo : orders.keySet()) {
            System.out.println("Serving Tea to table " + tableNo);
        }
    }
}

----------------------------

TeaMaker teaMaker = new TeaMaker();
TeaShop teaShop = new TeaShop(teaMaker);

teaShop.takeOrder("less sugar", 1);
teaShop.takeOrder("more milk", 2);
teaShop.takeOrder("without sugar", 5);

teaShop.serve();
// Serving tea to table 1
// Serving tea to table 2
// Serving tea to table 5
```

</div>

</details>

<br>

---

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

خب بیاید مثال درب رو پیاده سازی کنیم.

اول اینترفیس درب رو میسازیم و بعدش یک مدل درب پیاده سازی میکنیم.
در مرحله بعد هم یک پروکسی برای اضافه کردن امنیت به درب میسازیم.

<details>
<summary>Python</summary>

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


----------------------------

door = SecuredDoor(LabDoor())
door.open('invalid')  # Big no! It ain't possible

door.open('$ecr@t')  # Opening lab door
door.close()  # Closing Lab Door
```

</div>

</details>

<details>
<summary>Typescript</summary>
<div dir="ltr">

```typescript
interface Door {
    open(): void;

    close(): void;
}

class LabDoor implements Door {
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

----------------------------

const door = new SecuredDoor(new LabDoor());
door.open("invalid"); // Big no! It ain't possible
door.open("$ecr@t"); // Opening lab door
door.close(); // Closing Lab Door
```

</div>

</details>

<details>
<summary>Javascript</summary>
<div dir="ltr">

```javascript

class LabDoor {
    open() {
        console.log("Opening lab door");
    }

    close() {
        console.log("Closing the lab door");
    }
}

class SecuredDoor {
    constructor(door) {
        this.door = door;
    }

    open(password) {
        if (this.authenticate(password)) {
            this.door.open();
        } else {
            console.log("Big no! It ain't possible.");
        }
    }

    authenticate(password) {
        return password === "$ecr@t";
    }

    close() {
        this.door.close();
    }
}


const door = new SecuredDoor(new LabDoor());
door.open("invalid"); 
door.open("$ecr@t"); 
door.close(); 
```

</div>

</details>

<details>
<summary >#C</summary>

<div dir="ltr">

```C#

interface IDoor
{
  void Open();
  void Close();
}

class LabDoor : IDoor
{
  public void Close()
  {
    Console.WriteLine("Closing lab door");
  }

  public void Open()
  {
    Console.WriteLine("Opening lab door");
  }
}

class SecuredDoor : IDoor
{
  private IDoor mDoor;

  public SecuredDoor(IDoor door)
  {
    mDoor = door ?? throw new ArgumentNullException("door", "door can not be null");
  }

  public void Open(string password)
  {
    if (Authenticate(password))
    {
      mDoor.Open();
    }
    else
    {
      Console.WriteLine("Big no! It ain't possible.");
    }
  }

  private bool Authenticate(string password)
  {
    return password == "$ecr@t";
  }

  public void Close()
  {
    mDoor.Close();
  }
}

----------------------------

var door = new SecuredDoor(new LabDoor());
door.Open("invalid"); // Big no! It ain't possible.

door.Open("$ecr@t"); // Opening lab door
door.Close(); // Closing lab door

```

</div>

</details>

<details>
<summary>PHP</summary>

<div dir="ltr">

```PHP
interface DoorInterface {
  public function open();
  public function close();
}

class LabDoor implements DoorInterface {
  public function close() {
    echo "Closing lab door\n";
  }

  public function open() {
    echo "Opening lab door\n";
  }
}

class SecuredDoor implements DoorInterface {
  private $door;

  public function __construct(private DoorInterface $door) {
  }

  public function open(string $password) {
    if ($this->authenticate($password)) {
      $this->door->open();
    } else {
      echo "Big no! It ain't possible.\n";
    }
  }

  private function authenticate(string $password): bool {
    return $password === '$ecr@t';
  }

  public function close() {
    $this->door->close();
  }
}

$door = new SecuredDoor(new LabDoor());
$door->open('invalid');  // Big no! It ain't possible

$door->open('$ecr@t');  // Opening lab door
$door->close();  // Closing lab door
```

</div>

</details>

<details>
<summary>Go</summary>

<div dir="ltr">

```go
package main

import "fmt"

type IDoor interface {
    Open()
    Close()
}

type LabDoor struct {}

func (d LabDoor) Close() {
    fmt.Println("Closing lab door")
}

func (d LabDoor) Open() {
    fmt.Println("Opening lab door")
}

type SecuredDoor struct {
    door IDoor
}

func NewSecuredDoor(door IDoor) *SecuredDoor {
    return &SecuredDoor{door: door}
}

func (d *SecuredDoor) Open(password string) {
    if d.Authenticate(password) {
        d.door.Open()
    } else {
        fmt.Println("Big no! It ain't possible.")
    }
}

func (d *SecuredDoor) Authenticate(password string) bool {
    return password == "$ecr@t"
}

func (d *SecuredDoor) Close() {
    d.door.Close()
}

func main() {
    door := NewSecuredDoor(LabDoor{})
    door.Open("invalid") // Big no! It ain't possible.

    door.Open("$ecr@t") // Opening lab door
    door.Close() // Closing lab door
}

```

</div>

</details>

<details>
  <summary>Java</summary>

<div dir="ltr">

```java
interface Door {
    void open();
    void close();
}

class LabDoor implements Door {
    public void close() {
        System.out.println("Closing lab door");
    }

    public void open() {
        System.out.println("Opening lab door");
    }
}

class SecuredDoor implements Door {
    private Door door;

    public SecuredDoor(Door door) {
        if (door == null)
            throw new IllegalArgumentException("door can not be null");
        this.door = door;
    }

    public void open(String password) {
        if (authenticate(password)) {
            door.open();
        } else {
            System.out.println("Big no! It ain't possible.");
        }
    }

    private boolean authenticate(String password) {
        return "$ecr@t".equals(password);
    }
    
    @Override
    public void open() {
        System.out.println("Big no! It ain't possible.");
    }

    @Override
    public void close() {
        door.close();
    }
}

----------------------------

SecuredDoor door = new SecuredDoor(new LabDoor());

door.open("invalid");       // Big no! It ain't possible.
door.open("$ecr@t");        // Opening lab door
door.close();               // Closing lab door
```

</div>

</details>

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

<br>

---

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

میخوایم همون مثال پرداخت رو باهم پیاده سازی کنیم.

خب توی کد بالا یک کلاس مرجع ساختیم که اسمش Account هست. این کلاس یک متد داره که اسمش pay هست. این متد یک مقدار رو میگیره
و سعی میکنه اون مقدار رو از حساب خود پرداخت کنه. اگر موفق نشد، اون مقدار رو به حساب بعدی انتقال میده.

نکته: 
تابع inspect.stack یک تابعیه که میتونه اطلاعاتی از فراخوانی تابع رو برگردونه. مثلا اگر ما از این تابع در یک تابع دیگه
استفاده کنیم، این تابع میتونه اسم تابعی که از اون استفاده شده رو برگردونه.

خب حالا میخوایم یک حساب بانکی، یک حساب پی پال و یک حساب بیت کوین بسازیم.

همونطور که میبینید اومدیم و بعد از ساختن این حساب‌ها اونارو به هم متصل کردیم!

سیستم اول سعی کرده با حساب بانکی پرداخت کنه ولی موجودی کافی نداشت، بعدش سعی کرده با حساب پی پال پرداخت کنه ولی موجودی
کافی نداشت، و در نهایت با حساب بیت کوین پرداخت میکنه!

<details>
<summary>Python</summary>

<div dir="ltr">

```python
class Account:
    _successor = None
    _balance = None

    def setNext(self, account):
        self._successor = account

    def pay(self, amountToPay):

        if self.canPay(amountToPay):
            print("Paid " + str(amountToPay) + " using " + self.caller())
        elif self._successor:
            print("Cannot pay using " + self.caller() + ". Proceeding ..")
            self._successor.pay(amountToPay)
        else:
            raise ValueError("None of the accounts have enough balance")

    def canPay(self, amount):
        return self.balance >= amount
    def caller(self):
        return str(type(self).__name__)


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


# ----------------------------

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
            console.log(‍‍`Paid ${amountToPay} using ${myCaller}`
        )
            ;
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

----------------------------

const bank = new Bank(100);
const paypal = new Paypal(200);
const bitcoin = new Bitcoin(300);

bank.setNext(paypal);
paypal.setNext(bitcoin);

bank.pay(259);

''
'
Output
will
be
=== === === === ==
Cannot
pay
using
bank.Proceeding..Cannot
pay
using
paypal.Proceeding..
:
Paid
259
using
Bitcoin!
''
'
```

</div>
</details>

<details>
<summary>Javascript</summary>
<div dir="ltr">

```javascript

class Account {
    constructor() {
        this._successor = null;
        this._balance = null;
    }

    setNext(account) {
        this._successor = account;
    }

    pay(amountToPay) {
        const myCaller = (new Error().stack).split("at ")[2].split(" ")[0];
        if (this.canPay(amountToPay)) {
            console.log(`Paid ${amountToPay} using ${myCaller}`);
        } else if (this._successor) {
            console.log(`Cannot pay using ${myCaller}. Proceeding ..`);
            this._successor.pay(amountToPay);
        } else {
            throw new Error("None of the accounts have enough balance");
        }
    }

    canPay(amount) {
        return this._balance >= amount;
    }
}

class Bank extends Account {
    constructor(balance) {
        super();
        this._balance = balance;
    }
}

class Paypal extends Account {
    constructor(balance) {
        super();
        this._balance = balance;
    }
}

class Bitcoin extends Account {
    constructor(balance) {
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