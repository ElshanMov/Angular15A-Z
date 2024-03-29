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

Angular'da component'lər arasında data əlaqəsi qurmaq üçün Input və Output decorator'larını istifadə edirlər. Input decorator'u, bir component'ə data girişini təmin edir, Output decorator'u isə bir component'dən data çıxışını təmin edir.

### Input Decorator

Input decorator'u, component'ə kənardan data girişini təmin edir.

Misal olaraq, şagird component'i olsun və ad, soyad, nömrə kimi məlumatları gösdərməlidir. Bu component'ə kənardan gələcək şagird məlumatlarını ötürmək üçün Input decorator'u istifadə oluna bilər.

```ts I'm A tab
import { Component, Input } from "@angular/core";

@Component({
  selector: "app-student",
  template: `
    <div>
      <h2>{{ name }}</h2>
      <p>{{ surname }}</p>
      <p>{{ number }}</p>
    </div>
  `,
})
export class StudentComponent {
  @Input() name: string;
  @Input() surname: string;
  @Input() number: number;
}
```

Bu component, name, surname, number field'larına Input decorator'u tətbiq edir. Bu field'lar, component'ə kənardan gələcək şagird məlumatlarını saxlayacaq.

```ts I'm B tab
import { Component } from "@angular/core";

@Component({
  selector: "app-root",
  template: `
    <app-student name="John" surname="Doe" number="1234"></app-student>
  `,
})
export class AppComponent {}
```

Parent-component, child-component'i çağırır və şagird məlumatlarını Input field'ları vasitəsilə child-component'ə göndərir.

### Output Decorator

Output decorator'u, bir component'dən kənara data çıxışını təmin edir. Component, Output decorator'u ilə bildirilən event'ları trigger edərək dataları kənara göndərir.

Misal olaraq, sayğaç component'imiz olsun. Bu component, buton'a click olduqda sayğacı artırsın və artışı event vasitəsilə kənara bildirsin.

```ts I'm A tab
import { Component, EventEmitter, Output } from "@angular/core";

@Component({
  selector: "app-counter",
  template: `
    <div>
      <h2>{{ count }}</h2>
      <button (click)="increment()">Increment</button>
    </div>
  `,
})
export class CounterComponent {
  @Output() countChange = new EventEmitter<number>();

  count = 0;

  increment() {
    this.count++;
    this.countChange.emit(this.count);
  }
}
```

Bu component, `count` field'na və `countChange` event'na Output decorator'nu tətbiq edir. Bu event, sayğacdakı artımları kənara bildirir.

```ts I'm B Tab
@Component({
  selector: "app-root",
  template: `
    <app-counter (countChange)="onCountChange($event)"></app-counter>
    <p>Count: {{ count }}</p>
  `,
})
export class AppComponent {
  count = 0;

  onCountChange(count: number) {
    this.count = count;
  }
}
```

Parent component(AppComponent), Child component'i çağırır və `countChange` event'ni dinləyir. `onCountChange` funksiyası, hər dəfə trigger olanda `count` field'nı güncəlləyir və ekranda gösdərir.

## Lesson - 11 Component Life Cycle Hook Nədir?

Angular'da component'in yaradıldığı andan etibarən silindiyi/məhv edildiyi ana qədər olan müddət də müəyyən yerlərdə işləməsi üçün olan metodlar mövcuddur. Bu metodlar: layihənin istifadəsi zamanı, component'in data güncəlləməsi, DOM ilə əlaqəyə keçməsi və ya track edilən data'lar da olan dəyişikliklər kimi vəziyətlər də işə düşür, yəni hər metod component'in fərqli mərhələrin də işləyir və buna görə də fərqli vəzifələri yerinə yetirirlər.

Bu metodlar əsasən aşağıdakı ardıcıllıqda işləyir:

> ngOnChanges => ngOnInit => ngDoCheck => ngAfterContentInit => ngAfterContentChecked => ngAfterViewInit => ngAfterViewChecked => ngOnDestroy

- ngOnChanges: Component'də Input field'larında dəyişiklik olduqda işə düşür və yeni dəyərləri vermək üçün istifadə oluna bilər (OnChanges interface ilə implement oluna bilər).
- ngOnInit : Component ilk dəfə yaradılanda işə düşür (OnInit interface ilə implement oluna bilər).
- ngDoCheck : Angular, component'in güncəllənməsi vəziyyətində tez-tez bu metodu işə salır (DoCheck interface ilə implement oluna bilər). Həmçinin DoCheck'in change detection dövründə işlədiyini bilməyimizdə fayda var.
- ngAfterContentInit : Component'in content'i (<ng-content></ng-content>) ilkdəfə yaradılanda işə düşür (AfterContentInit interfaci ilə implement oluna bilər).
- ngAfterContentChecked : Component'in content'i güncəlləndikdə işə düşür (AfterContentChecked interface ilə implement oluna bilər).
- ngAfterViewInit : Component'in view'u ilk dəfə yaradıldığnda, təni template tam olaraq handle olduq da işə düşür. (AfterViewInit interface'i ilə implement oluna bilər).
- ngAfterViewChecked : Component'in view'u güncəlləndikdə işə düşür (AfterViewChecked interface ilə implement oluna bilər).
- ngOnDestroy : Component'in silinməsi/məhv olunması zamanı işə düşür (OnDestroy ilə implement oluna bilər).

## Lesson - 12 Angular Forms Yanaşmaları və Əsas Anlayışları Nələrdir?

Web Form, istifadəçidən data alaraq serverə göndərməyimizi təmin edən HTML elementidir. Web form'lar, istifadəçilərdən data girməsini təmin etməkdən başqa, girilən datanı təsdiqləmə, data formatını müəyyənləşdirmək, xəta mesajlarını göstərmək kimi prosesləri apardığımız strukturdur.
Angular kimi JavaScript təməlli web layihə framework'ləri, form proseslərini daha təkmilləşmiş və mürəkkəb bir şəkildə idarə etməyimizi təmin edən tool'lar və library'lər təmin edir.

Angular'da, **Template-Driven Form** və **Model-Driven/Reactive Form** olmaqla iki fərqli form yanaşması mövcuddur.

### Template-Driven Form Yanaşması

Template-Driven Form yanaşması, əsasən sürətli form yaratmaq istəyərkən və ya kiçik form işləri üçün istifadə olunur. TDF, HTML form'ları üzərində birbaşa işləyir və form məntiqi template(şablon) tərəfində idarə olunur. TDF yanaşmasını istifadə edərkən form tag'inə `ngForm`, hər bir form elementinə isə `ngModel` directive'i verilir.

```ts I'm A Tab
import { Component, OnInit, ViewChild } from "@angular/core";
import { NgForm } from "@angular/forms";
@Component({
  selector: "app-root",
  template: `<form #frm="ngForm" (ngSubmit)="onSubmit(frm.value)">
    <input type="text" name="name" placeholder="Name" ngModel />
    <br />
    <input type="text" name="surname" placeholder="Surname" ngModel />
    <br />
    <select name="job" ngModel>
      <option value="0">Teacher</option>
      <option value="1">Student</option>
      <option value="2">Software Developer</option>
      <option value="3">Chef</option>
    </select>
    <button>Send</button>
  </form>`,
})
export class AppComponent {
  @ViewChild("frm", { static: true }) frm!: NgForm;

  //Form'dakı dataların əldə olunması:
  onSubmit(data: { name: string; surname: string; job: string }) {
    console.log(data);
    var value = this.frm.form.get("name")?.value;
    console.log(value);
  }
}
```

**Qeyd:** Template-Driven yanaşmasını istifadə etmək üçün app.module'a `FormsModule` import edilməlidir.

### Model-Driven/Reactive Form Yanaşması

Template-Driven Form'lara nəzərən daha mürəkkəb form prosesləri üçün istifadə olunan yanaşmadır. Model-Driven yanaşması, TypeScript siniflərinnən istifadə olunaraq form məntiqini idarə edir. Form məntiqi kod tərəfində yazılır və form idarəsi daha mürəkkəb ssenarilər üçün daha uyğundur. Kod tərəfdə yaradılan form obyekti HTML'dəki əlaqəli form etiketlərinə bind olunur. Model-Driven Form'lar həmçinin Reactive Forms olaraq da adlandırılır çünki, form elementlərindəki dəyişikliklər əlaqəli obyekt tərəfindən reactive(dinamik) şəkildə track olunur.

```ts
import { Component, OnInit } from "@angular/core";
import { FormControl, FormGroup } from "@angular/forms";
@Component({
  selector: "app-root",
  template: `<form [formGroup]="frm" (ngSubmit)="onSubmit(frm.value)">
    <input type="text" placeholder="Name" formControlName="name" />
    <br />
    <input type="text" placeholder="Surname" formControlName="surname" />
    <br />
    <select formControlName="job">
      <option value="0">Teacher</option>
      <option value="1">Student</option>
      <option value="2">Software Developer</option>
      <option value="3">Chef</option>
    </select>
    <button>Send</button>
  </form>`,
})
export class AppComponent implements OnInit {
  frm!: FormGroup;

  ngOnInit(): void {
    this.frm = new FormGroup({
      name: new FormControl(),
      surname: new FormControl(),
      job: new FormControl(),
    });
  }

  onSubmit(data: { name: string; surname: string; job: string }) {
    console.log(data);
  }
}
```

**Qeyd:** Reactive forms yanaşmasını istifadə etmək üçün app.module'a `ReactiveFormsModule` import edilməlidir.

### Angular Form Anlayışları

Angular Form'larında hansı yanaşmadan istifadə etməyimizdən asılı olmayaraq 4 əsas anlayış mövcuddur.

1. **FormGroup** : Əlaqəli form sahələrini/formun özünü təmsil edən və bir qrup FormControl obyekti ehtiva edən obyektir. Bir form'da birdən çox FormGroup ola bilməz.
2. **FormArray** : Form içərisində dinamik olaraq yaradılan control'ləri edən array obyektidir. Form'da ola biləcək birdən çox təkrarlanan sahələrdə(Likedin skills) istifadə etmək üçün istifadə olunur.
3. **FormControl** : Form elementinin dəyərini almaq, təsdiqləmə və dəyişiklik vəziyyətini təmsil edən form control'dır.
4. **FormBuilder** : FormGroup, FormControl və FormArray obyektlərini yaratmağımızı sadələşdirən servisdir. İçərisindəki hazır funksiyalar sayəsində form'u sürətli yarada bilməyimizi və konfiqurasiya etməyimizi təmin edir.

```ts
import { Component } from "@angular/core";
import { FormArray, FormBuilder, FormGroup } from "@angular/forms";
@Component({
  selector: "app-root",
  template: `<form [formGroup]="frm" (ngSubmit)="onSubmit(frm.value)">
    <input type="text" placeholder="Name" formControlName="name" />
    <br />
    <input type="text" placeholder="Surname" formControlName="surname" />
    <br />
    <select formControlName="job">
      <option value="0">Teacher</option>
      <option value="1">Student</option>
      <option value="2">Software Developer</option>
      <option value="3">Chef</option>
    </select>

    <div formArrayName="tels">
      <div *ngFor="let tel of tels.controls; let i = index">
        <div [formGroupName]="i">
          {{ i }}. Name :
          <input type="text" formControlName="telName" placeholder="tel name" />
          {{ i }}. Tel :
          <input
            type="text"
            formControlName="telValue"
            placeholder="tel value"
          />
          <button (click)="deleteTel(i)" style="color:red">X</button>
        </div>
      </div>
      <a (click)="addTel()">Add Tel</a>
    </div>

    <button>Send</button>
  </form>`,
})
export class AppComponent {
  frm!: FormGroup;

  constructor(private formBuilder: FormBuilder) {
    this.frm = formBuilder.group({
      name: [""],
      surname: [""],
      job: [""],
      tels: formBuilder.array([]),
    });
  }
  get tels() {
    return this.frm.controls["tels"] as FormArray;
  }

  addTel() {
    const tel = this.formBuilder.group({
      telName: [""],
      telValue: [""],
    });
    this.tels.push(tel);
  }

  deleteTel(telIndex: number) {
    this.tels.removeAt(telIndex);
  }

  onSubmit(data: { name: string; surname: string; job: string; tels: [] }) {
    console.log(data);
  }
}
```

_Result:_

https://user-images.githubusercontent.com/62793862/231404247-c40c9558-1c8f-4d01-8238-edfe60faa85c.mp4

**Qeyd** : Bu anlayışların referansları ilə işləmək Reactive forms yanaşmasında aparılır amma TDF yanaşmasında da arxa tərəfdə bu referanslar işləyir.

## Lesson - 13 Template Driven Forms Yanaşması

TDF, form'dakı bütün proseslərin və validation'ların template üzərində directive'lər və attribute'lar istifadə olunaraq aparıldığı yanaşmadır.
TDF da bütün proseslərin template üzərində aparıldığı üçün component class'ında çox az kod yazılır.

Template-Driven Forms yanaşmasında istifadə olunan əsas directive'lər `ngForm` və `ngModel` - dir.

- ngForm - Form'un qurulmasının təmin edən əsas directive'dir.
- ngModel - Form içərisində istifadə olunacaq control'lərin işarətlənəcəyi directive'dir. Həmçinin bu directive Two Way Databinding mexanizmasından istifadə edir.

### Template-Driven Forms yanaşması ilə form yaratmağın detalları:

- TDF yanaşması ilə form yaratma üçün əvvəlcə lazım olan form directive'lərini və obyektləri özündə ehtiva edən `FormsModule` module'unu əlaqəli module'a import etməliyik.

- Hansı form'u TDF olaraq istifadə edəcəyiksə ona `ngForm` directive'i ilə işarətləməliyik. Bu directive form'un idarə olunmasını, validation proseslərini və form data'larının manipulyasiya olunmasını təmin edir. `ngForm` directive'i arxa tərəfdə FormGroup obyekti yaradaraq onu təmsil edir.

- Form içərisində istifadə olunacaq control'ları `ngModel` directive'i ilə işarətlənməlidir.

- Form doldurulduğu zaman component class'ına data'ların göndərilə bilinməsi üçün `ngSubmit` event'ından istifadə edirik.

**ngForm Directive Təfərrüatları:**

- `value` - FormGroup içərisində ki, FormControl obyektinin dəyərlərini verir.

- `valid` - Form valid olarsa _true_, əks halda _false_ dəyərini verir.

- `touched` - İstifadəçi form üzərində ən az bir sahəyə dəyər daxil etdisə _true_ dəyərini verir.

- `Submitted` - Form submit olarsa _true_ dəyərini verir.

```ts
import { Component, OnInit, ViewChild } from "@angular/core";
import { NgForm } from "@angular/forms";
@Component({
  selector: "app-root",
  template: `<form #frm="ngForm" (ngSubmit)="onSubmit(frm.value)">
    <input type="text" name="name" placeholder="Name" ngModel />
    <br />
    <input type="text" name="surname" placeholder="Surname" ngModel />
    <br />
    <select name="job" ngModel>
      <option value="0">Teacher</option>
      <option value="1">Student</option>
      <option value="2">Software Developer</option>
      <option value="3">Chef</option>
    </select>
    <button>Send</button>
  </form>`,
})
export class AppComponent {
  //Form'u component class'ında referans etmək üçün ViewChild decorator'nu aşağıdakı kimi istifadə etməliyik.
  @ViewChild("frm", { static: true }) frm!: NgForm;

  onSubmit(data) {
    console.log(`Value : ${this.frm.value}`);
    console.log(`Valid : ${this.frm.valid}`);
    console.log(`Touched : ${this.frm.touched}`);
    console.log(`Submitted : ${this.frm.submitted}`);

    console.log(data);
  }
}
```

**FormControl Təfərrüatları:**

- `value` - Əlaqəli control'un dəyərini verir.

- `valid` - Control'un dəyəri keçərlidirsə _true_, əks halda _false_ dəyərini verir.

- `invalid` - Control'un dəyəri keçərli deyilsə _true_, əks halda _false_ dəyərini verir.

- `touched` - elementə hər-hansısa bir dəyər daxil olduqda _true_ dəyirini qaytarır.

**Qeyd: TDF'da yuxarıdakı property'lərin istifadəsi üçün template reference variable (#fname) istifadə olunmalıdır**

```ts
<input type="text" name="firstname" #fname="ngModel" ngModel>

<!-- Form kontrol elemanının değerini ve geçerlilik durumunu kullanma -->
<p>Value: {{fname.value}}</p>
<p>Valid: {{fname.valid}}</p>
<p>Errors: {{fname.errors | json}}</p>
```

### ngModelGroup Directive'i Nədir?

Angular'da bir neçə form control'unu qruplamaq üçün istifadə olunan directive'dir.

```ts
import { Component, ViewChild } from "@angular/core";
import { NgForm } from "@angular/forms";
@Component({
  selector: "app-root",
  template: `<form #frm="ngForm" (ngSubmit)="onSubmit(frm.value)">
    <div ngModelGroup="name">
      <input type="text" name="first" placeholder="FirstName" ngModel />
      <br />
      <input type="text" name="middle" placeholder="MiddleName" ngModel />
      <br />
      <input type="text" name="last" placeholder="LastName" ngModel />
    </div>
    <input type="text" name="surname" placeholder="Surname" ngModel />
    <br />
    <select name="job" ngModel>
      <option value="0">Teacher</option>
      <option value="1">Student</option>
      <option value="2">Software Developer</option>
      <option value="3">Chef</option>
    </select>
    <button>Send</button>
  </form>`,
})
export class AppComponent {
  @ViewChild("frm", { static: true }) frm!: NgForm;

  onSubmit(data: any) {
    console.log(data.name.last);
    console.log(data.surname);
  }
}
```

### TDF-da Form control'larına başlanğıc dəyər mənimsətmək:

Bu proses üçün `setValue` funksiyasından istifadə olunur.

```ts
import { Component, ViewChild } from "@angular/core";
import { NgForm } from "@angular/forms";

@Component({
  selector: "app-my-form",
  template: `
    <form #myForm="ngForm">
      <input [(ngModel)]="firstName" name="firstName" />
      <input [(ngModel)]="lastName" name="lastName" />
      <input [(ngModel)]="email" name="email" />
      <button type="submit">Send</button>
    </form>
  `,
})
export class MyFormComponent {
  @ViewChild("myForm", { static: true }) form: NgForm;

  firstName: string;
  lastName: string;
  email: string;

  constructor() {
    this.firstName = "John";
    this.lastName = "Doe";
    this.email = "john.doe@example.com";

    this.form.setValue({
      firstName: this.firstName,
      lastName: this.lastName,
      email: this.email,
    });

    this.form.controls["lastName"].setValue("Mov");
  }
}
```

**Form'un bir hissəsinə dəyər mənimsətmək:**
Bunun üçün `patchValue` funksiyasından istifadə edirik.

```ts
this.form.control.patchValue({
  surname: "Mov",
  email: "elshan.mov.772@gmail.com",
});
```

**Form dəyərlərini reset'ləmək:**

```ts
this.form.reset();
this.form.resetForm();
this.form.onReset();
```

## Lesson - 14 Reactive Forms Yanaşması

Reactive Forms, component class'ında form'un strukturunun object olaraq(FormGroup) tutulduğu form yanaşmasıdır. Yəni form strukturunda istifadə olunan FormGroup, FormArray və FormControl kimi bütün obyektləri özümüzün yaradırıq və konfiqurasiya edirik. Bunlarla yanaşı form'un validation qaydaları ilə birlikdə əlavə prosesləri də form obyekti üzərindən həyata keçiririk.

### Reactive forms yanaşmasın da istifadə olunan əsas directive'lər:

- `formGroup` - Form'un yaradılmasını təmin edən əsas directive'dir. Form elementlərinin component class'ındakı model ilə əlaqələnməsini təmin edir.

- `formControlName` - FormGroup obyekti içərisindəki hərhansısa bir FormControl'ü form elementlərindən birinə bağlamaq və əlaqələndirmək üçün istifadə olunan directive'dir.

### Reactive Forms yanaşması ilə form yaratmağın detalları:

- Reactive forms yanaşması ilə form yaratma üçün əvvəlcə lazım olan form directive'lərini və obyektləri özündə ehtiva edən `ReactiveFormsModule` module'unu əlaqəli module'a import etməliyik.

- Daha sonra yaradılacaq form'un modelini yaradırıq və lazım olan FormControl'ları yazırıq. Bunun üçün `FormBuilder` obyektinnən istifadə edə bilərik.

- Davamın da isə HTML hissəsində form'u yaradırıq və 'form' etiketinə `formGroup` directive'i ilə yaradılan model'ə, form control'larını isə modeldəki əlaqəli FormControl'larına `formControlName` directive'i ilə bağlayırıq(binding).

- Son olaraq, istifadəçi tərəfindən doldurulan modelin göndərilməsi üçün `ngSubmit` event'inə funksiya yazaraq data'nı əldə edirik.

```ts
@Component({
  selector: "app-my-form",
  template: `
    <form [formGroup]="frm" (onSubmit)="onSubmit(frm.value)">
      <input type="text" formControlName="name" />
      <input type="text" formControlName="surname" />
      <input type="text" formControlName="email" />
      <input type="text" formControlName="tel" />
      <button type="submit">Send</button>
    </form>
  `,
})
export class MyFormComponent {
  frm!: FormGroup;

  constructor(private formBuilder: FormBuilder) {
    this.frm = formBuilder.group({
      name: [""],
      surname: ["mammadov"], //default dəyər
      email: [""],
      tel: [""],
    });
  }
  onSubmit(data: any) {
    console.log(data);
  }
}
```

### formGroupName Directive'i

Template-Driven Forms yanaşmasındakı, `ngModelGroup` directive'nin Reactive Forms'dakı qarşılığıdır.

```ts
@Component({
  selector: "app-my-form",
  template: `
    <form [formGroup]="frm" (onSubmit)="onSubmit(frm.value)">
      <input type="text" formControlName="name" /> <br />
      <input type="text" formControlName="surname" /> <br />
      <input type="text" formControlName="email" /> <br />
      <input type="text" formControlName="tel" />
      <div formGroupName="address">
        <input type="text" name="Country" formControlName="country" /> <br />
        <input type="text" name="City" formControlName="city" /> <br />
        <input type="text" name="Address" formControlName="address" /> <br />
      </div>
      <button type="submit">Send</button>
    </form>
  `,
})
export class MyFormComponent {
  frm!: FormGroup;

  constructor(private formBuilder: FormBuilder) {
    this.frm = formBuilder.group({
      name: ["elshan"],
      surname: ["mammadov"],
      email: ["elshan.mov.772@gmail.com"],
      tel: ["123"],
      address: formBuilder.group({
        country: ["", Validators.required], //Validation
        city: [""],
        address: [
          "",
          [
            //Array şəklində validation yazmaq
            Validators.required,
            Validators.max(100),
          ],
        ],
      }),
    });
  }
  onSubmit(data: any) {
    console.log(data);
  }
}
```

### `onlySelf` parametri:

Angular'da default olaraq hər hansısa bir form elementinin dəyərində dəyişiklik olduqda əlaqəli form validation vəziyyətlərinin hamısını pilləli şəkildə hamısını yoxlayacaq. Bunu ləğv etmək üçün `onlySelf` parametrini istifadə edərək bütün form'u yox, onlySelf'in yazıldığı control'u yoxlayacaq.

```ts
this.frm.controls["name"].serValue("Elshan", { onlySelf: true }); //form valid olmayacaq. Template də dəyişiklik olarsa valid olacaq.
```

### `valueChanges` və `statusChanges` event'ları:

- `valueChanges` - Form'dakı control'lardan birinin dəyəri dəyişərsə işə düşür.

```ts
this.frm.valueChanges.subscribe({
  next: (data) => {
    console.log(data);
  },
});

this.frm.get("name").valueChanges.subscribe({
  next: (data) => {
    console.log(data);
  },
});
```

- `statusChanges` - Form'dakı control'lardan birinin dəyəri dəyişərsə işə düşür.

```ts
this.frm.statusChanges.subscribe({
  next: (data) => {
    console.log(data);
  },
});

this.frm.get("name").statusChanges.subscribe({
  next: (data) => {
    console.log(data);
  },
});
```

## Lesson - 15 Changing the Status / Angular Form'da state dəyişdirmə funksiyaları:

Changing the Status anlayışı, Angular'dakı form strukturunun state'ni programmatic şəkildə dəyişdirməyimizi təmin edən funksiyalar toplusunu ifadə edir. Bu funksiyalar ilə form'un və form'dakı control'ların state'ni programmatic olaraq və yaxud istifadəçi interfeysi ilə dəyişdirə bilərik.

### İstifadə oluan funksiyalar:

1. `markAsTouched` - Bu funksiya hər-hansısa bir form'da və yaxud əlaqəli form içərisindəki control'da proses aparılarsa form'un və əlaqəli control'un `touched` property'si **true** olaraq dəyişəcəkdir. Yəni əlaqəli form'a və yaxud form control'a toxunulduğu programmatic olaraq ifadə edilmiş olacaq.

```ts
this.frm.get("name").markAsTouched(); //form touched: true
this.frm.markAsTouched(); //'name' control touched: true
```

**Qeyd:** Əgər bu funksiyada `onlySelf` parametri true dəyərini versək, harda istifadə etsək sadəcə o strukturun `touched` property'sinə təsir edəcək.

```ts
this.frm.get("name").markAsTouched({ onlySelf: true }); // form touched: false
// `name` control touched: true
```

**Qeyd:** onlySelf parametrni digər funksiyalarda da istifadə edə bilərik.

2. `markAllAsTouched` - Bu funksiya markAsTouched funksiyasında olduğu kimi control'un və o control'un altındakı bütün control'ların touched property'sinin dəyərini true olaraq dəyişəcəkdir.

```ts
`<div formGroupName="address">
  <input type="text" name="Country" formControlName="country" /> <br />
  <input type="text" name="City" formControlName="city" /> <br />
  <input type="text" name="Address" formControlName="address" /> <br />
</div>`;

this.frm.get("address").markAsTouched(); //Address form control'una markAsTouched funksiyası ilə programmatic olaraq müdaxilə etsək, sadəcə address control'u ilə form bundan təsirlənəcək.
//form touched: true
// `address` control touched: true
// `country` control touched: false

this.frm.get("address").markAllAsTouched(); //Address form control'una markAllAsTouched funksiyası ilə programmatic olaraq müdaxilə etsək,  address control'u ilə altındakı bütün control'lar bundan təsirlənəcək lakin form bundan təsirlənməyəcək.
//form touched: false
// `address` control touched: true
// `country` control touched: true
```

3. `markAsUntouched` - Bu funksiya ilə form və yaxud from control'nun touched property'si **false** olacaq. Əlaqəli strukturun toxunulmadığı aid programmatic toxunuşlar edilərkən üstünlük verilir.

```ts
this.frm.get("name").markAsUntouched(); // form touched: true
// `name` control touched: false

this.frm.markAsUntouched(); // form touched: false
//'name' control touched: false
```

4. `markAsDirty` - Bu funksiya ilə əlaqəli form'un və yaxud form control'nun `dirty` property'sinin dəyəri programmatic olaraq dəyişdirilə bilinməkdədir.

```ts
this.frm.markAdDirty(); //form dirty: true
this.frm.get("name").markAsDirty(); //'name' control dirty: true
```

5. `markAsPristine` - Bu funksiya ilə əlaqəli form'un və yaxud control'nun `pristine` dəyərini true olaraq dəyişdirməyimizi təmin etməkdədir. Beləliklə, əlaqəli form'a heç toxulunmadığı, yəni form'da heç bir iş görülməyib mahiyətində iş görə bilərik.

```ts
this.frm.get("name").markAsPristine(); //form pristine: true
this.frm.markAdDirty(); //'name' control pristine: true
```

**Qeyd:** Angular'da `pristine` property'si, form control'nun başlanğıcdakı(ilk yükləndiyi və ya sıfırlandığı) vəziyyətini təmsil edən boolean dəyərdir. `pristine` property'si, form control'nun istifadəçidən dəyər daxil etdiyi dəyəri dəyişdirdiyi anda **false** dəyəri alır və istifadəçinin form'u təmizləmə və ya sıfırlama prosesi apardığın da **true** dəyərini alır.

6. `disbale` - İstifadə olunduğu form'un və yaxud form control'un deaktiv olmasını təmin edir.
7. `enable` - İstifadə olunduğu form'un və yaxud form control'un aktivləşdirməsini təmin edir.

```ts
this.frm.get("name").disable();
this.frm.get("name").enable();
```

## Lesson - 16 Validation
