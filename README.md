# Angular15A-Z

## Angular Nədir?
Angular, Google tərəfindən ərsəyə gətirilən JavaScript təməlli **SPA** (Single Page Application) layihə yarada biləcəyimiz framework'dür. Hər framework'ün development edə bilmək üçün özünəməxsus konsepsiyası olur. Bu repoda özünə görə qaydaları, davranışları olan Angular texnologiyasına A-dan Z-yə yer veriləcəkdir.

## Framework Nədir?
Framework hər hansısa bir proqramlaşdırma dilini istifadə edərək, müəyyən qaydaları özündə ehtiva edən texnologiyadır (məsələn ASP .Net Core).

## SPA Nədir?
"SPA" Tək Səhifəli Tətbiq. Bu, istifadəçinin müraciət etdiyi səhifələri hər dəfə serverdən başdan yüklənməyini tələb etməyən, bir web səhifəsi içində işləyən web layihə design'nıdır. Səhifənin başdan yüklənməyi yerinə, layihə AJAX istifadə edərək serverdən data alaraq səhifənin dinamik olaraq yeniləyir. SPA'lar əsasən JS təməlli frameworklərdir (Angular, React, Vue.js). Səhifəni bir HTML faylında tutaraq, SPA daha problemsiz və sürətli istifadəçi təcrübəsi təqdim edir çünki, serverin layihə kodunu və dataları bir dəfə brauzerə göndərməsi kifayətdir. Bundan fərqli olaraq ASP .Net MVC də səhifələri fərqli view'larda yazırıq və fərqli-fərqli action'lardan istək alırıq. Səhifələr arasında keçid etdikdə səhifə ən başdan yenidən yüklənir.

Xülasə, SPA'lar istifadəçilər üçün daha sürətli və rahat təcrübə yaşadır, serverlərin yükünü azaldır və səhifə keçidlərini minimuma endirərək daha sürətli və problemsiz web layihələr yaratmağımıza kömək edir.

## Fundamentals
* > Module
* > Component
* > DataBinding
* > Dependency Injection
* > Directive
* > Decorator
* > Service
* > Template
* > Guard
* > Pipe

# Lesson1 - Angular Introduction and Workspace

Angular ilə çalışdıqda **Angular CLI** köməkçimiz olacaq. Bu bizə manuel olmadan Angular strukturlarını yaratmağımıza imkan verəcək. Angular CLI ilə işləmək üçün əvvəlcə Node.js-i yükləmək lazımdır çünki, CLI node.js runtime-da işləyir.

Angular CLI'ı yükləmək üçün lazım olan command:
`npm install -g @angular/cli` -g (global) => yazmaq isdənilən folder'dan **ng** command'larını əlçatan etməyi təmin edir.

[`ng version` (angular versiyasına baxmaq) / `ng new` (Angular layihəsi yaratmaq) / `ng generate` (service,component,module və s. kimi strukturları yaratmaq) / `ng serve` (layihəni tab'da gösdərir (default 4200) ) / `ng build` (layihəni build edir) ]

**Qeyd : Angularda OOP paradigması ilə kod yazmaq üçün TypeScript istifadə edəcəyik.**

## Angular WorkSpace
![angular workspace](https://user-images.githubusercontent.com/62793862/220083336-ec5d7461-889e-4146-9b09-3133cb7f9bda.png)

**Qeyd : Angular işləmə məntiqi MVC pattern'a əsaslanır.**