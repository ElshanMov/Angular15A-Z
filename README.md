# Angular15A-Z

## Angular Nədir?

Angular, Google tərəfindən ərsəyə gətirilən JavaScript təməlli **SPA** (Single Page Application) layihə yarada biləcəyimiz framework'dür. Hər framework'ün development edə bilmək üçün özünəməxsus konsepsiyası olur. Bu repoda özünə görə qaydaları, davranışları olan Angular texnologiyasına A-dan Z-yə yer veriləcəkdir.

## Framework Nədir?

Framework hər hansısa bir proqramlaşdırma dilini istifadə edərək, müəyyən qaydaları özündə ehtiva edən texnologiyadır (məsələn ASP .Net Core).

## SPA Nədir?

"SPA" Tək Səhifəli Tətbiq. Bu, istifadəçinin müraciət etdiyi səhifələri hər dəfə serverdən başdan yüklənməyini tələb etməyən, bir web səhifəsi içində işləyən web layihə design'nıdır. Səhifənin başdan yüklənməyi yerinə, layihə AJAX istifadə edərək serverdən data alaraq səhifənin dinamik olaraq yeniləyir. SPA'lar əsasən JS təməlli frameworklərdir (Angular, React, Vue.js). Səhifəni bir HTML faylında tutaraq, SPA daha problemsiz və sürətli istifadəçi təcrübəsi təqdim edir çünki, serverin layihə kodunu və dataları bir dəfə brauzerə göndərməsi kifayətdir. Bundan fərqli olaraq ASP .Net MVC də səhifələri fərqli view'larda yazırıq və fərqli-fərqli action'lardan istək alırıq. Səhifələr arasında keçid etdikdə səhifə ən başdan yenidən yüklənir.

Xülasə, SPA'lar istifadəçilər üçün daha sürətli və rahat təcrübə yaşadır, serverlərin yükünü azaldır və səhifə keçidlərini minimuma endirərək daha sürətli və problemsiz web layihələr yaratmağımıza kömək edir.

# Lesson1 - Angular Introduction and Workspace

Angular ilə çalışdıqda **Angular CLI** köməkçimiz olacaq. Bu bizə manuel olmadan Angular strukturlarını yaratmağımıza imkan verəcək. Angular CLI ilə işləmək üçün əvvəlcə Node.js-i yükləmək lazımdır çünki, CLI node.js runtime-da işləyir.

Angular CLI'ı yükləmək üçün lazım olan command:
`npm install -g @angular/cli`
-g (global) => yazmaq isdənilən folder'dan **ng** command'larını əlçatan etməyi təmin edir.

### ng commands :

[`ng version` (angular versiyasına baxmaq) / `ng new` (Angular layihəsi yaratmaq) / `ng generate` (service,component,module və s. kimi strukturları yaratmaq) / `ng serve` (layihəni tab'da gösdərir (default 4200) ) / `ng build` (layihəni build edir) ]

**Qeyd : Angularda OOP paradigması ilə kod yazmaq üçün TypeScript istifadə edəcəyik.**
**Qeyd : Anguların işləmə məntiqi MVC pattern'a əsaslanır.**

## Angular WorkSpace

![angular workspace](https://user-images.githubusercontent.com/62793862/220083336-ec5d7461-889e-4146-9b09-3133cb7f9bda.png)

## Lesson2 - Anguların əsas strukturları

### Angularda istifadə olunan strukturlar :

- `Component` - Componentlər layihənin görüntü layer'ni ifadə edən və data modelləri ilə əlaqə quraraq səhifələri istifadəçilərə servis edən strukturlardır (MVC - nin özü :)
- `Directive` - HTML obyektlərinin davranışlarını və görünüşlərini idarə edə bildiyimiz xüsusi etiketdir.
- `Module` - layihədəki strukturları qruplaşdırmağı təmin edir. Module'lar vasitəsilə modulyar proqramlaşdırma edə bilirik yəni layihənin parçalarını (components, services və s.) bir yerə yığaraq vahid şəkildə istifadə oluna bilməsi təmin olunur. Module'lar ilə səhifələrin yüklənməsini daha da optimizasiya etmək üçün **lazy loading** (ehtiyyac olduqda əlaqəli strukturların səhifəyə yüklənməsi ) yanaşmasını implementasiya edə bilirik.
- `Decorator` - TypeScriptin xüsusiyyətidir və Angularda istifadə olunur (`@Components`,`@Injectable`). Decarotorlar class member'lərinə metadata'lar əlavə edir.
- `Templates` - Pure HTML'lər deyillər. Template'lərin içində Angulara xas strukturları implementasiya etmək olur.
- `Guard` - Guard'lar ilə layihə üzərində nəzarət mexanizmasını təmin edirik yəni authorization, authentication (JWT, session, cookie).
- `Pipes` - dataları istifadəçiyə görsətmədən əvvəl formatlaşdırmaq üçün istifadə olunur.
- `Data Binding` - Component və UI arasındakı datanı bir-birinə bağlayan mexanizmadır.
- `Service` > `Dependency Injection` > `Metadatas`

## Lesson3 - Component Nədir?

Angular da component'lər əsasən UI'ın hər hansısa bir hissəsini təmsil edən müəyyən funksionallığa malik strukturdur. Hər component member'ları, xüsusiyyətləri, funksiyaları olan TypeScript class'ından, componentin görünüşünü təsvir edən HTML şablonundan və style'nı təsvir edən CSS faylından ibarətdir.

Component'ləri, hər hansısa bir hissənin necə görünəcəyini, hansı funksionallığa malik olacağını və layihənin yerdə qalan hissəsi ilə necə əlaqəli olacağını ifadə edən strukturlar kimi başa düşə bilərik.

Ümumi olaraq, komponentlər Angular'da mühüm bir konsepti təşkil edir və dinamik, modulyar və idarə edilməsi asan veb tətbiqləri yaratmaqda mərkəzi rol oynayırlar.

### Angular da component:

![Component](https://user-images.githubusercontent.com/62793862/220411141-c5e22fd6-441e-4659-ae6f-e93228db3503.png)

**templateUrl :**
Component'lərdəki HTML'ləri template'lər də yazırıq. Template'lərə HTML'in genişləndirilmiş versiyası kimi baxılmalıdır çünki Angulara xas directive, pipe kimi strukturlardan istifadə edirik.

Qeyd : Template'i external olmadanda yaza bilərik, bunun üçün template keyword'ü ilə string interpolation istifadə etməyimiz kifayətdir:

![template](https://dotnettutorials.net/wp-content/uploads/2018/09/word-image-171.png)

**styleUrls :**
Array olaraq declare olunubdur yəni bir neçə style path'ni qeyd edə bilərik.

**component class :**
Component class'ı içərisində JS, TS, JQeury, DI, business logic yazırıq. Yəni frontend'in proqramatik hissəsi component class'larında yazılır.

**selector :**
Component'in selector dəyəri ilə istinad prosesini edirik (yalnız HTML'lərdə istifadə olunur).

`<app-root></app-root>`

**Qeyd: Component'lər bir-birini selector ilə istinad edə bilməsi üçün ya eyni module'da olmalıdırlar ya da olduqları module'dan export olmalıdırlar. Bir component'in istifadə olunması üçün birbaşa və ya dolayı yolla ana module'da import olmalıdırlar əgər öz module'nan başqa module'da istifadə olunacaqsa export etmək lazımdır.**

![export](https://miro.medium.com/v2/resize:fit:640/format:webp/1*-iIOHD-ZjIIhYzrTTJcQ8w.png)

**Metadata decorator :**
Componentin nələri ehtiva etdiyini ve nece istifadə olunacağını bildirdiyimiz decatordur.
Bu decorotor ilə əlaqəli componentin: selector, template, style məlumatları ilə component'lər arası data transferi, yönləndirmədəki (routing) keçid animationları, component'in kənardan ala biləcəyi dəyişənlər(inputs) və yaxud kənardan emit'lənəcək event'lər(outputs) və s. Declare oluna bilər.

### Component'i yaratmaq üçün olan command :

`ng g/generate c/component [component name]`

Component'lər declare olur, module'lar isə import :)

## Lesson4 - Data Binding Nədir?

Data binding, Angular da component class'ında olan modellər və ya funksiyaların view'larla əlaqə yaratmağını təmin edən strukturlardır.

Data binding əlaqə strukturan görə bir neçə yerə bölünür:

- Text Interpolations
- Property Binding
- Event Binding
- Two-way Binding
- Attribute Binding
- Class Binding
- Style Binding

### Text Interpolations

Template'in içərisində component class'ında olan field/property dəyərini yazdırmaq üçün istifadə olunan binding üsuludur.

![textinterpolation](https://user-images.githubusercontent.com/62793862/220535499-6683f726-0442-4b1b-96f5-b653d70e0a76.png)

Interpolation üsulu ilə binding üçün `{{}}` istifadə olunaraq property dəyərini mətnə və ya attribute'a bind edirik.

### Property Binding

Property binding, template içərisindəki HTML obyektlərinə və ya directive'lərə component class'ında olan dataların property olaraq bind etməsini təmin edən üsuldur. Property'ni bind etmək üçün `[]` istifadə olunur.

![propertybinding](https://user-images.githubusercontent.com/62793862/220537992-e3d53ac0-b2cf-48ee-9c24-8f031935a30c.png)

Property binding ilə selector'la istinad edilən component'lərin içərisindəki _input property'lərə_ də dəyər assign edə bilərik :

![propselector](https://user-images.githubusercontent.com/62793862/220540803-1caa6c83-36d2-4b33-b8e5-a77a6dcb7f12.png)

### Event Binding

Event binding, mouse click'ləyəndə, klaviatura düymələrini basdıqda və ya digər istifadəçi event'larında event trigger etməyimizi təmin edən binding üsuludur. Hər hansısa event'ı component'dəki function'a bind etmək üçün `()` istifadə olunur.

![eventBinding](https://user-images.githubusercontent.com/62793862/220553281-b4b47e05-28ea-4263-b95f-11d5c4e1827a.png)

> on-click şəklindədə event binding edə bilərik:

`<button on-click="btnClick()">Click me</button>`

> event'lara qarşılıq gələn funksiyaları nöktəli vergüllə ayıra bilərik (Multiple event handlers):

`<button on-click="btnClick(); btnClick2()">Click</button>`

> hər-hansısa keyword event'ında aşağıdakı kimi HTML obyektinə bind edə bilərik:

`<input (keydown.shift.a)="aEvent()" value="Aaa">`
`<input (keydown.shift.b)="bEvent()" value="Bbb">`

### Two-way Binding

Two-binding'i əsasən form elementlərində istifadə edirik. Template içərisindəki HTML obyektinin value'su dəyişdikdə əlaqəli obyektə bind edilmiş component class'ı içərisindəki field/property dəyəri də anlıq olaraq dəyişdirilməsini və eyni zamanda tam tərsi vəziyyətində keçərli olmasını təmin edən binding üsuludur.

`[(ngModel)]` directive'i ilə two-way binding prosesini edirik. Bu directive'in istifadə oluna bilinməsi üçün `FormsModule` layihənin ana module'na import edilməlidir.

![image](https://user-images.githubusercontent.com/62793862/220559425-363d007a-ff10-450b-b8ce-a43fe5029570.png)

![two-way](https://user-images.githubusercontent.com/62793862/220559163-938aa4bf-3172-4bef-a8f5-f6884f12aeaf.gif)

**Qeyd :** `[(ngModel)]` directive ilə bind olunmuş HTML obyektində olaraq dəyişiklik olarsa, `(ngModelChange)` event'i ilə hər hansısa bir event'i trigger edib, daxil olunan dəyərin doğruluğunu anlıq olaraq yoxlaya bilərik.

![image](https://user-images.githubusercontent.com/62793862/220559939-de63ffb2-5ff8-48e2-9a7b-4370be07291c.png)

HTML obyektləri üçün istifadə olunan `(change)` eventi'də mövcuddur. Bu event `[(ngModel)]` directive'i olmadan dəyişikliklərə event fırlatmaq üçündür. Yəni `(ngModelChange)`, `[(ngModel)]` directive'i ilə birlikdə istifadə olunarkən `(change)` event’ı isə tək istifadə edilməkdədir.

### Attribute Binding:

HTML obyektlərinin attribute'larının dəyərlərini component class'ında verilməsini təmin edən binding üsuludur.

---

import { Component } from '@angular/core';

@Component({

selector: 'app-root',

template:

<button [disabled]="disabled">Push<button>
,

styleUrls: ['./app.component.scss']

})

export class AppComponent {

disabled:boolean=true;

}

---

![image](https://user-images.githubusercontent.com/62793862/220562316-c9edb06e-be89-4b43-b60c-7995e5c5745b.png)

### Style and Class Binding:

HTML obyektinin style və ya class dəyərlərini component class'ı ilə bind edə bildiyimiz data binding üsuludur.

![image](https://user-images.githubusercontent.com/62793862/220565299-6e632ff9-06be-40f1-8762-1b8005a537d6.png)

Angular da **Change Detection** Alqoritimi:

Template'də event trigger olduqda və ya istifadəçin etdiyi bir şey nəticəsində modelin value'su dəyişərsə, component class'nı məlumatlandırmaq və Template ilə sinxronizasiya təmin etmək üçün **Change Detection** alqoritmi istifadə olunur.

## Lesson - 5 Interpolation Syntax Nədir?

Angular'da component class'ı içərisindəki hər hansısa field, property dəyərini `{{...}}-interpolation syntax` operatoru vasitəsilə HTML içərisində istifadə olunmasına Text Interpolation deyilir.

_Interpolation, One-Way data binding'dir._

### Interpolation'da nələri istifadə etmək olmaz :

Interpolation ilə sadəcə property və ya field dəyərini template'də əks etdirmək üçün istifadə edirik. Buna görə də layihənin state`ni dəyişdirəcək hər hansısa prosesi icra etmək mümkün deyil.

Layihənin state'ni dəyişməyinə səbəb olacaq keywordlər Interpolation ilə istifadə oluna bilməz:

> Assign operatorları `=, +=, -=` > `new`, `typeof`, `instanceof` və s. keyword'ləri
> `:` operatoru
> `++,--` - Increment, Decrement operatorları
> Bitwise operatorları

**Qeyd: Interpolation'da iki dəyişən ilə arifmetik proses, konkatenasiya, template referansı istifadə edə bilərik və ya hər hansısa bir funksiyanı call edə bilərik.**

**Qeyd: Interpolation'da Script/HTML kodları işə salmaq mümkün deyil. Angular, Interpolation ilə DOM'a əlavə edəcəyimiz kontenti hər şeydən əvvəl sterizasiya edərək _Cross-Site Scripting Security Bugs(XSS)_ xətalarına qarşı tədbir alır. Interpolation ilə gələn Script və HTML kodları mətn olaraq oxunur**

### ngNonBindable:

Interpolation operatorunun compile edilməsini istəmiriksə `ngNonBindable` keyword'nu istifadə edə bilərik.

`<p ngNonBindable>{{text}} world</p>`

Angular da Interpolation ilə pipes - `{{text | uppercase}}`, nullable operator-`(person?.name)`, non-null assertion(iddia)-`(person!.name)` kimi strukturları istifadə edə bilirik.

## Lesson - 6 Directives (ngFor, ngSwitch, ngIf, ngClass, ngStyle)

### Directive Nədir?

Directive'lər, HTML elementlərinə əlavə xüsusiyyətlər və davranışlar əlavə etmək üçün istifadə olunan xüsusi etiketlərdir. Directive'lərə DOM obyektlərinə manipulyasiya etməyimizi təmin edən strukturlarda deyə bilərik. Angular'da davranışlarına görə fərqli olan hazır directive'lər mövcuddur, bundan əlavə **custom directive**'lərdə yarada bilərik.

HTML elementinə, directive ilə nəzərdə tutulan davranışı mənimsətmək üçün directive'in selector'nu yazmağımız kifayətdir.

`template:<div *ngIf=" flag==true ">....</div>`

### Built-in (Hazır) directive'lər Hansılardır?

- ngFor
- ngSwitch
- ngIf
- ngClass
- ngStyle
- ngModel
- ngNonBindable

Əsasən istifadə olunan directive'lər bunlardır amma başqa built-in directive'lərdə mövcuddur.

### ngFor Directive

HTML obyektləri üzərində iterasiya proseslərini həyata keçirmək üçün istifadə edirik.

![ngFor](https://user-images.githubusercontent.com/62793862/221155816-1efbd861-da6a-4b1b-a649-321ed0369f6c.png)

ngFor directive ilə **index** dəyərinidə ala bilirik.

`template: <div *ngFor="let name of names;index as i">{{name}} - {{i}}</div>`

Və ya _index_, _first_, _last_, _even_ və _odd_ keyword'ləri ilə ngFor directive'ni istifadə edə bilərik.

![indexetc](https://user-images.githubusercontent.com/62793862/221171794-19d54201-7b48-40cd-882b-dfc948305d27.png)

### ngIf Directive

Müəyyən şərtə görə HTML obyektlərinin visibility'ni dəyişmək üçün istifadə olunan directive'dir.

![ngIf](https://user-images.githubusercontent.com/62793862/221174649-af5e1c20-c5bb-4bc3-a756-e544f1619a97.png)

**if/else** məntiqində istifadə etmək üçün `ng-template` istifadə etməliyik.

![ngTemplate](https://user-images.githubusercontent.com/62793862/221175362-07c7933b-2401-45ba-bc54-900493db23c1.png)

ngIf directive'ində else/if məntiqində davranış yoxdur. Buna görə aşağıdakı məntiqdən istifadə edə bilərik:

![elseif](https://user-images.githubusercontent.com/62793862/221182369-886c51d0-71b3-41b5-9bc2-aee7723d727b.png)

### ngSwitch Directive

ngIf kimi bu directive'də müəyyən şərtə görə HTML obyektlərinin visibility'ni dəyişmək üçün istifadə olunan directive'dir.

![ngSwitch](https://user-images.githubusercontent.com/62793862/221183579-3a8e0e20-be5b-471f-ac29-e1f633bc288f.png)

**Qeyd:** Görüldüyü kimi `ngSwitch` directive'i, ngSwitchCase və ngSwitchDefault directive'ləri ilə birlikdə istifadə olunur.

### ngClass Directive

HTML etiketlərinin _class_ attribut dəyərini dinamik olaraq idarə edəbilməliyimizi təmin edən directive'dir.

![ngClass](https://user-images.githubusercontent.com/62793862/221185646-143daeae-4aef-4c65-bcfc-dc344f3ca6ee.png)

### ngStyle Directive

HTML etiketlərinin _style_ attribut dəyərini dinamik olaraq idarə edəbilməliyimizi təmin edən directive'dir.

![ngStyle](https://user-images.githubusercontent.com/62793862/221184726-3bc68cec-54a9-41ab-8016-69118c8cd11f.png)

### ngModel & ngNonBindable Directive

`ngModel` direvtive'i ilə **two-way** binding prosesini həyata keçiririk.

`ngNonBindable` directive'i ilə **text interpolation** xüsusiyyətinin təsirsiz olmasını həyata keçiririk.

## Lesson - 7 Custom Directive necə yaradılır?

directives folder'i altında example adında custom directive yaratmaq üçün yazacağımız command:

`ng g d directives/example`

![directive](https://user-images.githubusercontent.com/62793862/221235132-d8d33547-7150-4fbb-a2a2-124367046e70.png)

Directive yaradılan zaman ana module'a declare edilməlidir. Directive'in directive ola bilməsi üçün `@Directive` decorator'u tərəfindən işarələnməlidir.

### Directive'in class və ya attribute olaraq istifadəsi

![customDirectiveSelectorName](https://user-images.githubusercontent.com/62793862/221240789-1688d6ef-cbfa-4b41-bb33-4f9a8ed109d9.png)

### Custom directive ilə elementi əldə etmək və parametr qəbul edərək manipulyasiya prosesi aparmaq.

**Qeyd:** JQuery paketi istifadə olunduğu üçün `declare var $:any` yazaraq component class'ında JQuery istifadə edə bilərik.

![directiveInput](https://user-images.githubusercontent.com/62793862/221248458-348d9d49-cfdc-4501-b4a8-6b134b62c71d.png)

**RESULT:**

https://user-images.githubusercontent.com/62793862/221250598-f9331218-c56b-4137-b508-592fce939aa2.mp4

### HostListener decorator'u

Yaradılan directive'in hansı event ilə işləyəcəyini təyin etdiyimiz decorator'dur.

https://user-images.githubusercontent.com/62793862/221254255-774821c1-a95b-4317-8324-9fb06dda4c7e.mp4

### HostBinding decorator'u

HostBinding ilə directive'in yazıldığı DOM obyektinin hər hansısa bir xüsusiyyətinə bind olaraq manipulyasiya edirik.

![hostBinding](https://user-images.githubusercontent.com/62793862/221270789-39aff54e-fb83-4245-a8a2-04cfc2e28d55.png)

## Lesson - 8 Structural Directives

HTML obyektlərini və DOM struktunu manipulyasiya edərək səhifə üzərində dəyişikliklər etməyimizi təmin edən directive tipi/növüdür.

Structural directive'lərin əsas fərqləndirici xüsusiyyəti style'ı yox, birbaşa DOM-un anatomiyasına təsir edir (elementin görünüb-görünməməsi-`*ngIf`, elementin repeat olunması-`*ngFor`).
Structural directive'lə \* simvolu ilə çağrılır.

Structural directive'lərdə istifadə olunan `TemplateRef` və `ViewContainerRef` referansları bilinməlidir. DOM-un manipulyasiyası zamanı directive'in istifadə olunduğu template'i **TemplateRef**, template'in kontentini ehtiva edən isə **ViewContainerRef** referansıdır (HTML-ə elementləri əlavə etmək, çıxartmağa yarayır).

### Custom structural directive yaratmaq

**Custom If**

![customIf](https://user-images.githubusercontent.com/62793862/221418632-f43b8da2-b5a6-45cc-a65a-89d3f8402526.png "Custom If")

<br/>

**Custom For**

![ngFor](https://user-images.githubusercontent.com/62793862/221419215-0c225fdc-8ca3-442f-9087-dcffe58f9e6c.png "Custom For")

<br/>

![ngForA](https://user-images.githubusercontent.com/62793862/221420168-f5ed45a1-0914-473e-8a17-ac94a7ccb6d8.png "Custom For (implicit keyword'u istifadə etdikdə HTML`də declare edərək birbaşa istifadə etmək olur.)")

## Lesson - 9 Pipe

Angular'da pipe, dataların formatlaşdırılması üçün istifadə olunan elementlərdir. Template faylarında istifadə olunaraq data'ları manipulyasiya etməyimizi təmin edir. Məsələn, tarix data'sını müəyyən bir formatda göstərilməsini, ədədin pul şəklində ifadə olunmasını istəyiriksə pipe'lardan istifadə edə bilərik. Bu kimi ehtiyacları data'nın orjinallığına təsir etmədən sadəcə görünən hissədə manipulyasiya etmək istəyiriksə pipe'larla həll edə bilərik.

**Angular'da bir çox built-in pipe'lar mövcuddur:**

- DatePipe - Tarix data'larını formatlaşdırır.
- UpperCasePipe/LowerCasePipe - Mətn tipli dəyərlərin bütün hərflərini böyük/kiçik hərflərə convert edir.
- DecimalPipe - Ədəd tipli dəyərləri formatlaşdırır.
- CurrencyPipe - Ədəd tipli dəyərləri pul vahidlərinə formatlaşdırır.
- PercentPipe - Ədəd tipli dəyərləri faizə formatlaşdırır.
- SlicePipe - Array'lardəki data'lara müəyyən aralıqlara bölməyimizi təmin edir.
- JsonPipe - Obyekti JSON formatına convert edir.
- KelValuePipe - Key, Value formatındakı datanın həm key'ini həm də value'sunu istifadə etməyimizi təmin edir.

Angular'dakı built-in pipe'lardan savayı custom pipe'larda yarada bilərik. Məsələn hər hansısa mətni tərsinə çevirən pipe, array içindəki data'ları istəyimizə uyğun filtirləmək kimi pipe'ları yarada bilərik.

```ts
import { Component } from "@angular/core";
@Component({
  selector: "app-root",
  template: `
    {{ name | slice : 1 : 3 }}
    <br />
    {{ name | uppercase }}
  `,
})
export class AppComponent {
  name = "elshan";
}
```

slice pipe'nın nəticəsi: **ame** | uppercase pipe'nın nəticəsi : **ELSHAN**

[Angular'dakı built-in pipe'lar və istifadəsi](https://angular.io/api?type=pipe)

### Custom pipe yaratmaq

Custom pipe yaratmaq üçün yazacağımız command: `ng g p ...name...`

```ts I'm A tab
import { Pipe, PipeTransform } from "@angular/core";

@Pipe({
  //pipe-ı bu ad ilə çağıracayıq
  name: "custom",
})
export class CustomPipe implements PipeTransform {
  //Pipe'in istifadə olunduğu dəyəri manipulyasiya/transform etməyimizi təmin edən funksiyadır
  transform(value: string, a: number, b: number): unknown {
    return value.slice(a, b);
  }
}
```

```ts I'm B tab
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  template: `
    {{ name | slice : 1 : 3 }}<br />
    {{ "Angularda custom pipe istifadə edirik" | custom : 10 : 20 }}
  `,
})
export class AppComponent {
  name = "pipes";
}
```

**slice pipe'nın nəticəsi:** ip
**custom pipe'nın nəticəsi:** custom pip

### Pipe'ların template faylarınndan əlavə fərqli yerlərdə istifadəsi

Pipe'ı template'dən fərqli olaraq hər hansısa bir class'da istifadə etmək istəyiriksə, AppModule'da providers'ə əlavə etməliyik. Arxa tərəfdə providers'ə əlavə etmiyimiz pipe singleton olarak IoC Containerə əlavə olunur və biz həmin pipe'ı servis mahiyyətində instance olaraq istifadə edə bilirik.

```ts I'm A tab
import { CurrencyPipe, DatePipe } from "@angular/common";
import { NgModule } from "@angular/core";
import { BrowserModule } from "@angular/platform-browser";

import { AppComponent } from "./app.component";
import { CustomPipe } from "./pipes/custom.pipe";

@NgModule({
  declarations: [AppComponent, CustomPipe],
  imports: [BrowserModule],
  providers: [CurrencyPipe],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

```ts I'm B tab
import { CurrencyPipe } from "@angular/common";
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  template: `<h1>Salam</h1>`,
})
export class AppComponent {
  constructor(private currency: CurrencyPipe) {
    console.log(currency.transform(20));
  }
}
```

Kod blokunun nəticəsi:
![image](https://user-images.githubusercontent.com/62793862/224978896-7426a76f-2be7-49d9-af34-2e1d554bc561.png)

**Qeyd:** Currency pipe'i default olaraq dollar simvolunu gösdərir. Biz bu default dəyərə müdaxilə etmək istəyiriksə AppModule'dakı providers'də istədiyimiz default dəyəri verə bilərik.

```ts
@NgModule({
  declarations: [AppComponent, CustomPipe],
  imports: [BrowserModule],
  providers: [{ provide: DEFAULT_CURRENCY_CODE, useValue: "₼" }, CurrencyPipe],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

Currency pipe'nın default dəyəri dəyişdirildikdən sonra kodun nəticəsi
![image](https://user-images.githubusercontent.com/62793862/224980463-68203783-1970-4b93-afe5-38a30389668c.png)

## Lesson - 10 Input/Output Communication | Parent to Child & Child to Parent

Angular'da Component Communication, component'lər arasında data və event paylaşma prosesini ifadə edən anlayışdır. Angular, componentlər arasında data paylaşmaq üçün bir neçə üsul mövcuddur.

1. Input və Output decorators: Componentlər arasında data qəbul etmək və ya data göndərmək üçün `@Input` və `@Output` decorator'larından istifadə edə bilərik. Parent component'dən Child component'ə **(PtC)** data göndərmək üçün **@Input** decorator'undan, Child'dan Parent'a **(CtP)** göndərmək üçün isə **@Output** decorator'undan istifadə edirik.

2. Services: Servislər, component'lər arasında data göndərmək üsullarından biridir. Component, service çağıra bilər və service, data'nı alıb başqa component'ə göndərə bilər.

3. Event Binding: Component, başqa component'də baş verən event'ı tutmaq üçün event binding istifadə edə bilər. Beləliklə, Bir component, başqa bir component'də baş verən event'ı tuta bilər və lazım olan prosesi apara bilərik.

4. RxJS: RxJS, component'lər arasında data axınını idarə etmək üçün istifadə olunan library'dir. Angular'da component'lər arasında olan əlaqələri idarə etmək üçün çox istifadə olunur.

Component Communication üçün hələlik **PtC** və **CtP** communication'larına baxacayıq.
