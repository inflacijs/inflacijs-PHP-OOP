# OOP PHP

## OOP - Object Oriented Programing

### Objekt orientēta programmēšana ir programmēšanas veids, kuru raksturo tas, ka dati tiek apvienoti kopējās struktūrās(klasēs un objektos), kur dati ieņem primāro lomu, un tikai pēctam tiek organizētas darbības(funkcijas). Atšķirībā no funkcionālās programēšanas, kur primāro lomu ieņem funkcijas un tikai pēctam dati.

___

## OOP priekšrocības

* Paredz mazākas izmaksas izstrādei.
* Nodrošina tīrāku strukturū programmai, to lasot ir vieglāk saprast un izsekot katram solim.
* Palīdz PHP kodā nodrošināt DRY( Don't Repeat Yourself) principu, un palīdz kodu vieglāk lasī, uzturēt, testēt un labot(debugging).
* Palīdz iveidot aplikācijas  ar īsāku izstrādes laiku. OOP valodām parasti ir bagātīgas bibliotēkas un freimvorki. Un bieži vien projekta laikā izstrādāti kodi, var būt izmantojami vēlāk citos projektos.
* Tā ir arī samērā droša, par cik dati ir paslēpti un nav pieejami no ārējām funkcijām.

## OOP mīnusi

* Lēnākas programmas. OOP parasti ir lēnākas par programmām, kuras ir bāzētas uz procedūrprogramēšanas.
* Lielāks programmas izmērs nekā procedūrprogramēšanā.
* Grūtāk apgūstama. OOP princips dažiem cilvēkiem var izrādīties grūtāk apgūstams un var aizņemt vairāk laika.
* Nav pielietojama visiem risinājumiem. Citos risinājumos labāk tomēr izvēlēties funkcionālo, loģisko vai procedūr programēšanu, lai sasniegtu labākus rezultātus.

____

## Populārākas OOP valodas

* Java
* C++
* C#
* Python
* PHP
* JavaScript
* Ruby

____
## OOP ieviešana PHP programmēšanas valodā

### Kad 1995 gadā izlaida pirmo PHP versiju, tad OOP tajā nebija iekļauta. 1999. gadā izlaižo PHP 3.0 versiju, pamazām sāka tajā iekļaut OOP programēšanas principus. Galu galā 2004. gadā izlaižot PHP 5.0, tajā bija jau pilnvērtīgas OOP iespējas.

____

## Klases(Class), objekti(object), properties(īpašības), methods(metodes).

### Tehniski objektorientēto programmēšanu raksturo klases un objekti.

![class](https://tutorials.supunkavinda.blog/static/images/php-oop-class-blueprint.png)


### Tātad klase ir ir kā mājas rasējums. No viena rasējuma var uzcelt vairākas mājas. Tāpat arī no vienas klases var uztaisīt vairākus objektus.



![class](https://tutorials.supunkavinda.blog/static/images/php-oop-object-houses.png)

### Katrai mājai ir sava krāsa, grīdas flīzes un aprīkojums. Tāpat arī dažādiem objektiem var būt dažādi properties jeb īpašības.

## Kas ir Properties? 

## Properties ir objekta mainīgie. Tie glabā vērtības, kas tiek saistītas ar objektu. 

![class](https://tutorials.supunkavinda.blog/static/images/php-oop-properties.png)

### Properties var būt pievienotas, mainītas, novāktas. Citas var būt vienkārši tikai lasāmas.

## Kas ir Methods ?

### Metodes ir darbības, kas var tikt piešķirtas objektam. Mainīt mājas krāsu ir dabība, kas ir piešķirta šim mājas objektam.

![class](https://tutorials.supunkavinda.blog/static/images/php-oop-method.png)






___

## OOP piemēri

### Pieņemsim, ka mums ir klase ar nosaukumu **Fruit**. Fruit klasei ir īpašības: name, color, height. Mēs varam definēt mainīgos $name $color, $height un tie tad arī glabās šīs īpašības.

### Kad individuāli objekti (ābols, banāns, apelsīns) ir izveidoti, tie manto visas īpašības(properties) un metodes no klases. Bet katram objektam būs savas īpašību vērtības(value).

## Klases definēšana
### Klase tiek definēta izmanotojot atslēgasvārdu class, kam seko klases nosaukums un šādas iekavas **{}**. Visas klases īpašības un metodes  ir jāliek iekšā šajās iekavās.

```PHP
<?php
    class Fruit {
        // Kodu rakstam te
    }
?>
```

### Tālāk mūs definējam klasi, kura satur divas īpašības ($name un $color) un divas metodes set_name() un get_name(), kuras definē $name un atgriež $name.



```PHP
<?php
class Fruit {
  // Īpašības(properties)
  public $name;
  public $color;

  // Metodes(methods)
  function set_name($name) {
    $this->name = $name;
  }
  function get_name() {
    return $this->name;
  }
}

$banana = New Fruit;
$banana->set_name('Banana");
?>
```
___
## Constructor - __construct funkcija
### Konstruktors ļauj  definēt objekta īpašības, objekta veidošanas brīdī.
### Ja tu izveido __construct() funkciju, PHP automātiski izsauks šo funkciju objekta veidošanas brīdī.

### Piemārā zemāk mēs redzam, ka klasē *Fruit* ir izveidots konstruktors ar diviem parametriem $name un $color, līdz ar to, tad tie arī būs obligāti jaunas instances izveidošanas brīdī. Šo īpašību(properties) definēšana jaunās instances izveidošanas brīdī, mums ļauj neveidot funkcijas set_name() un set_color(), kas ietaupa vietu kodā.

### Objekts jeb jauna klases instance  tiek izveidota izmantojot atslēgasvārdu *new*, tad seko klases nosaukums *Fruit* un pēctam iekavās ir norādīts objekta nosaukums un krāsa. Atgriežoties pie koda iepriekšējajā sekcijā mēs redzam, ka pateicoties tam, ka netiek izmantots __constructor, jaunu klases instanci var izveidot pat bez iekavām *new Fruit*

```PHP
<?php
class Fruit {
  public $name;
  public $color;

  function __construct($name, $color) {
    $this->name = $name;
    $this->color = $color;
  }
  function get_name() {
    return $this->name;
  }
  function get_color() {
    return $this->color;
  }
}

$apple = new Fruit("Apple", "red");
echo $apple->get_name();
echo "<br>";
echo $apple->get_color();
?>
```

## Destructor - __destructor

### Destruktors ir specfiska klases iekšējā funkcija, kas automātiski tiek izsaukta tieši pirms objekta likvidēšanas. 
#### Ja tu izveido __destruct() funkciju, PHP automātiski izsauc šo funkciju skripta beigās(skripta beigas uzskatāmas tad, kad tiek aizvērts PHP skripts ar šiem simboliem - "?>"). Līdz ar to objekts pēctam vairs nav pieejams. Ja vēlies objektu inīcināt skripta darbības laikā, tad ir jāizmanto metode unset($obj).

```PHP

<?php
class Fruit {
  public $name;
  public $color;

  function __construct($name, $color) {
    $this->name = $name;
    $this->color = $color;
  }
  function __destruct() {
    echo "The fruit is {$this->name} and the color is {$this->color}.";
  }
}

$apple = new Fruit("Apple", "red");
?>
```
___

## Access Modifiers jeb **Visibility**

![interfaces](https://tutorials.supunkavinda.blog/static/images/php-oop-visibility.jpg)

#### Piekļuves modifikatori kontrolē to no kurienes var piekļūt metodēm un īpašībām. 

* **public** - metodes un īpašības ir pieejamas no visurienes. Pēc noklusējuma ir public.
* **protected** - metodes un īpašības ir pieejamas klases ietvaros un arī klasēs, kuras ir atvasinātās (extends) no konkrētās klases.
* **private** - metodes un īpašības ir pieejamas tikai klases ietvaros.

```PHP
<?php
class Fruit {
  public $name;
  private $color;
  protected $weight;

  public function set_name($n) {  // a public function (default)
    $this->name = $n;
  }
  protected function set_color($n) { // a protected function
    $this->color = $n;
  }
  private function set_weight($n) { // a private function
    $this->weight = $n;
  }
}

$mango = new Fruit();

$mango->set_name('Mango'); // OK
$mango->name; // Mango
$mango->set_color('Yellow'); // ERROR
$mango->color // Error
$mango->set_weight('300'); // ERROR
$mango->weight; // error
?>

```
___________________

## Mantojamība(inheritance)

![interfaces](https://tutorials.supunkavinda.blog/static/images/php-oop-inheritance-2.png)

### Mantojamība ir tad, kad viena klase tiek atvasināta no citas klases. Tā pārņem īpašības un metodes no citas vai pat dažreiz no vairākām klasēm. Atvasinātā klase manto visas **public** un **protected** metodes un īpašības. Klases mantojamība tiek definēta ar vārdu **extends**.

```PHP
<?php
class Fruit {
  public $name;
  public $color;
  public function __construct($name, $color) {
    $this->name = $name;
    $this->color = $color;
  }
  protected function intro() {
    echo "The fruit is {$this->name} and the color is {$this->color}.";
  }
}

class Strawberry extends Fruit {
  public function message() {
    echo "Am I a fruit or a berry? ";
  }
}

// Try to call all three methods from outside class
$strawberry = new Strawberry("Strawberry", "red");  // OK. __construct() is public
$strawberry->message(); // OK. message() is public
$strawberry->intro(); // ERROR. intro() is protected
?>
```

### Mantotās metodes un īpašibas var tikt pārrakstītas. To var izdarīt atvasinātajā klasē vienkārši definējot metodes vai īpašības ar tādu pašu nosaukumu.

## Final

### Atslēgas vārds **final** tiek izmantots, lai aizsargātu klases īpašības un metodes no mantošanas vai pārrakstīšanas.

```PHP

<?php
final class Fruit {
  // some code
}

// will result in error
class Strawberry extends Fruit {
  // some code
}
?>
```
___

## Class constants(konstances)
### Konstances nevar tikt mainītas. Tām saglabājās sākotnējā piešķirtā vērtība. 
### Konstances var būt noderīgas tad, ja ir nepieciešams defināt klasē kādus konstantus datus. 
### Tās deklarē ar vārdu **const** , kuram seko konstances nosaukums, kuru rekomendē rakstīt ar lieliem burtiem.
### Mēs varam piekļūt konstancēm no klases ārpuses izmantojot klases vārdu, kuram seko **::**(scope resolution operator) un konstances nosaukums.

```PHP
<?php
class Goodbye {
  const LEAVING_MESSAGE = "Sveiki, jūs tikko apmeklējāt www.otrapuse.lv";
}

echo Goodbye::LEAVING_MESSAGE;
?>
```

### Vai arī varam tai piekļūt no klases iekšienes izmantojot vārdu **self** un **::**, kuriem seko konstances nosaukums.

```PHP
<?php
class Goodbye {
  const LEAVING_MESSAGE = "Sveiki, jūs tikko apmeklējāt www.otrapuse.lv";
  public function byebye() {
    echo self::LEAVING_MESSAGE;
  }
}

$goodbye = new Goodbye();
$goodbye->byebye();
?>
```

## Abstraktās klases un metodes(Abstract classes nad methods)

![interfaces](https://tutorials.supunkavinda.blog/static/images/php-oop-abstract.png)

### Abstraktās klases un metodes ir tad, kad vecāku klasē(parent class) metodi tikai nosauc, bet bērnu klase definē funkciju ar tādu pašu nosaukumu, kurā ievieto jau kādu darbību.
### Abstrakta klase ir klase, kura satur vismaz vienu abstraktu metodi. Abstrakta metode ir metode, kas ir deklarēta, bet kurā nav iekļauts kods.
### Gan abstrakta klase, gan metode tiek definēta ar vārdu **abstract**. 
```PHP
<?php
abstract class ParentClass {
  abstract public function someMethod1();
  abstract public function someMethod2($name, $color);
  abstract public function someMethod3() : string;
}
?>
```
### Tātad, lai bērna klase mantotu no abstraktas klases ir jāpieturās pie šādiem notiekumiem:
* Bērna klases metodei jābūt definētai ar tādu pašu nosaukumu kā vecāku abstraktajā klasē un tad tā pārdeklarē vecāku abstraktās klases metodi.
* Bērna klases metodei jābūt definētai ar tādu pašu vai arī mazāk ierobežotu pieejas modifikatoru. piem. Ja abstraktajai klasei ir **protected** pieejas modifikators, tad bērna klasei jābūt **protected** vai **public**, bet ne **private**.
* Nepieieciešamo argumentu skaitam ir jābūt tādam pašam, tomēr bērna klasei var būt arī kādi neobligātie(optional) argumenti.

```PHP
<?php
// Vecāku klase
abstract class Car {
  public $name;
  public function __construct($name) {
    $this->name = $name;
  }
  abstract public function intro() : string;
}

// Bērnu klases
class Audi extends Car {
  public function intro() : string {
    return "Choose German quality! I'm an $this->name!";
  }
}

class Volvo extends Car {
  public function intro() : string {
    return "Proud to be Swedish! I'm a $this->name!";
  }
}

class Citroen extends Car {
  public function intro() : string {
    return "French extravagance! I'm a $this->name!";
  }
}

// Objektu veidošanu no bērnu klasēm
$audi = new Audi("Audi");
echo $audi->intro();
echo "<br>";

$volvo = new Volvo("Volvo");
echo $volvo->intro();
echo "<br>";

$citroen = new Citroen("Citroen");
echo $citroen->intro();
?>
```

### Skaidrojums augstākesošajam kodam - 
### Audi, Volvo, Citroen klases ir atvasinātas no Car klases. Tas nozīmē to, ka Audi, Volvo un citroen klases var izmantot publisko **$name** īpašību, kā arī publisko __constructor metodi no Car klases, dēļ mantojamības.
### Bet intro() ir abstrakta metode, kurai jābūt definētai visās bērnu klasēs un tai ir jāatgriež strings.

____

## Interfaces

### Interfaces ļauj tev precizēt kādas metodes klasē vajadzētu ieviest

![interfaces](https://tutorials.supunkavinda.blog/static/images/php-oop-interface.png)

### Interfaces darbojas ļoti līdzīgi abstraktajām klasēm. Starp tām ir maza atšķirība.

## Kāpēc izmantot **interface** ?

### Ja vēlies klasei piespiedu kārtā likt izmantot kādas metodes, kuras satur *interface*. Piemēram :

```PHP

interface LoginInterface {
  public function loginFirst();
}

class Paypal implements LoginInterface {
  public function loginFirst() {

  }

  public function payNow(){

  }

}


```

## Deklarēšana 
### Interfaces tiek deklarētas ar vārdu **Iinterface**.
## Tikai abstraktas metodes
### Interface var saturēt tikai abstraktas metodes(metodes bez body), tikai deklarācijas. Un visām metodēm ir jābūt **public**.
## Vārds **implements** .

### Atšķirībā no abstrakt klases(tur izmanto vārdu **extends**), lai iekļautu klasē interface, jums ir jāizmanto vārds **implements**.
```PHP
class MyClass implements MyInterface { /* ... */ }
```
### Implementējot klasē **Interface**, visām abstraktajām metodēm ir jābūt deklarētām bērna klasē, savādāk metīs erroru.

```PHP

<?php
Interface Person {
	public function __construct($name);
	public function greet() : string;
}

class Programmer implements Person {
	public $name;
	public function __construct($name) {
		$this -> name = $name;
	}
	public function greet() : string {
		return "Hello World from " . $this -> name;
	}
}
$programmer = new Programmer('John');
echo $programmer -> greet();
```


___

## Traits 

### PHP atbalsta tikai 1 mantojamību. Bērna klase var mantot metodes un īpašības tikai no 1 vecāka, nevis no vairākiem. Kas notiek, ja bērna klasei vajaga mantot metodes no vairākām klasēm ? 
### OOP traits šo problēmu atrisina.
### Traits var saturēt metodes un abstraktas metodes, kuras var tikt izmantotas no vairākām klasēm. Metodēm arī var tikt piešķirts jebkurš piekļuves modifikātors(public, private vai protected).
### Traits tiek deklarēts ar vārdu **trait**

```PHP
<?php
trait TraitName {
  // kods
}
?>
```
### Lai trait izmantotu kādā klasē, lieto vārdu **use**.

```PHP
<?php
class MyClass {
  use TraitName;
}
?>
```
### Apskatīsim piemēru.

```PHP
<?php
trait Message1 {
public function msg1() {
    echo "OOP is fun! ";
  }
}

class Welcome {
  use Message1;
}

$obj = new Welcome();
$obj->msg1();
?>
```
### Piemēra skaidrojums - tiek deklarēts traits ar nosaukumu **message1**. Pēctam mēs izveidojam klasi ar nosaukumu **Welcome**. Pēctam klase izmanto *trait* un visas meodes, kuras ir *trait*'ā būs pieejamas klasē.
### Ja citām klasēm ir nepieciešams izmantot msg1() funkciju, vienkārši izmanto message1 *trait* tajās klasēs. Tas samazina koda atkārtošanos, jo nav nepieciešams deklarēt vienu un to pašu metodi atkal un atkal.
### Tāpat var arī izmantot vairākus **trait**.

```PHP
<?php
trait Message1 {
  public function msg1() {
    echo "OOP ir kruta! ";
  }
}

trait Message2 {
  public function msg2() {
    echo "OOP novērš koda atkārtošanos!";
  }
}

class Welcome {
  use message1;
}

class Welcome2 {
  use message1, message2;
}

$obj = new Welcome();
$obj->msg1();
echo "<br>";

$obj2 = new Welcome2();
$obj2->msg1();
$obj2->msg2();
?>
```
## Static methods(statiskās metodes)

### Statiskās metodes var tikt izsauktas pa taisno, bez jaunas klases instances izveidošanas.
### Statiskās metodes tiek deklarētas ar vārdu **static**.
```PHP
<?php
class ClassName {
  public static function staticMethod() {
    echo "Hello World!";
  }
}
?>
```
### Lai piekļutu statiskai metodei izmanto klases nosaukumu, dubulto kolu **::** un metodes nosaukumu.
```PHP
ClassName::staticMethod();
```
### Apskatīsim kādu piemēru:

```PHP
<?php
class Greeting {
  public static function welcome() {
    echo "Hello World!";
  }
}

// Call static method
greeting::welcome();
?>
```

### Augstāk mēs redzam, ka ir deklarēta statiskā metode welcome(). Pēctam mēs izsaucam statisko metodi.

## Vairāk par **static methods**.

### Klasei var būt gan statiskās metodes, gan parastās. Statiskā metodei var būt pieeja no parastās metodas tajā pašā klasē. Izmantojot vārdu **self** un dubultkolu.

```PHP
<?php
class Greeting {
  public static function welcome() {
    echo "Hello World!";
  }

  public function __construct() {
    self::welcome();
  }
}

new Greeting(); // Hello World!
?>
```

### Statiskās metodes var tikt izsauktas no metodēm citās klasēs. Lai tas notiktu, statiskajai metodei ir jābūt publiskai(public).

```PHP
<?php
class Greeting {
  public static function welcome() {
    echo "Hello World!";
  }
}

class SomeOtherClass {
  public function message() {
    greeting::welcome();
  }
}
?>
```

### Lai izsauktu statisku metodi bērna klasē, izmanto vārdu **parent**. Vecāku klasē statiskajai metodei jābūt vai nu *public* vai *protected*. 

```PHP

<?php
class Domain {
  protected static function getWebsiteName() {
    return "otrapuse.lv";
  }
}

class DomainW3 extends Domain {
  public $websiteName;
  public function __construct() {
    $this->websiteName = parent::getWebsiteName();
  }
}

$domainW3 = new DomainW3;
echo $domainW3->websiteName;
?>
```
_____

## Static Properties(statiskās īpašības)

### Statiskās īpašības strādā tāpat kā statiskās metodes.
### Statiskās īpašības var tikt izsauktas pa taisno, bez jaunas klases instances izveidošanas.
### Statiskās īpašības tiek deklarētas ar vārdu **static**.

```PHP
<?php
class ClassName {
  public static $staticProp = "otrapuse.lv";
}
?>
```
### Lai piekļutu statiskai īpašībai izmanto klases nosaukumu, dubulto kolu **::** un īpašības nosaukumu.
```PHP
ClassName::staticProp;
```
### Apskatīsim kādu piemēru.
```PHP
<?php
class Pi {
  public static $value = 3.14159;
}

// Get static property
echo Pi::$value;
?>
```

### Augstāk mēs redzam, ka ir deklarēta statiskā īpašība *value* . Pēctam mēs izsaucam statisko īpašību.


____
## Namespaces

### Vienkāršais izskaidrojums - Divus cilvēkus sauc par **Roberts** (tā mēdz gadīites). Mēs viņus varam atšķirt pateicoties uzvārdiem. Tāpat arī divām klasēm var gadīites vienādi nosaukumi. Tieši tādēļ mums palīgā nāk **namesapaces**. Klases mēs varam atšķirt pateicoties **namespaces**.

### Ko **namespaces** dara ? 

* Namespacaces var novērst klašu nosaukumu pārklāšanos.
* Namespaces var padarīt jūsu kodu vairāk organizētu.

## **use**

### Lai iekļautu vēlamajā klasē kādu klasi ar *namespace*, izmantojam vārdu **Use**.

## Apskatīsim kādu piemēru

```
/src
  /Pizzas
    /Calzone(pārlocītās)
      calzoneSpeciale.php
      calzoneSpicy.php
    Margarita.php
    Funggi.php
    Bergamo.php
    Venezia.php

```

###   **Pizzas/Margarita.php**

```PHP
<?php
namespace Pizza;

class Margarita {
  public $topping = 'Mozarella'
  
  public function getTopping()
  {
    return $this->topping;
  }
}
```

### **Pizzas/Calzone/speciale.php**

```PHP

namespace Pizzas\Calzone;

use Pizzas\Margarita;

class calzoneSpeciale {	
  public $size;
  public $topping = ['cheese', 'mashrooms', 'shrimps']
	public function __construct($size) {
		$this->size = $size;
	}
	public function getSize() {
		return $this->size;
  }
  
	public function addExtraMozarella() {
		
		$this->topping[] = Margarita::getTopping();)
	}
	
}
```














