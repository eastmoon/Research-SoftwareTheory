## Interactive architecture

### MVC，Model View Controller

於1970年提出的互動架構，其設計概念在於：

**『將資料(Model)、視圖(View)、控制(Controller)三者分割。』**

其主要元件(Component)描述如下：

+ Model
模組用於儲存資料，經由控制取得內容後，顯示於視圖。

+ View
視圖用於呈現得到的資料。

+ Controller
控制接收用戶的行為，並更新模組、傳遞命令並操作視圖。

##### § 小結

MVC是非常悠久的互動架構，最初設計始於1970，雖與現今需求相比，當時的軟體架構樣式實做上並不能完全符合，但其設計概念至今仍有其必要性。

其中最常爭議與修改的部分是在Controller，主因是現今的控制來源多樣，因此控制的設計是否應附屬於模組之中則是常有的議題。

至今MVC的設計並沒有完全統一，各軟體公司雖有自身的MVC架構，但溝通方式不一定完全相同。

##### § 參考

+ [MVC wiki](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller)
+ [什麼是MVC架構](http://phoebelin0606.pixnet.net/blog/post/374094436)
+ [MVP架构模式详解](http://www.jianshu.com/p/4b754ea48a40)

### MVP，Model View Presenter

於1990年提出的互動架構，其概念是MVC的延伸，而設計重點在於：

**『資料分解為互動、商業資料，呈現者會將視圖、模組間不必要的資料抽出保存，將必要的資料傳遞給對方。』**

其主要元件(Component)描述如下：

+ Model
模組用於儲存資料，並提供介面存取資料。

+ View
視圖用於顯示資料，並傳遞使用者命令給呈現者。

+ Presenter
呈現者可操作模組、視圖；其從知識庫(對應的模組)取得資料，並格式化為視圖可用的資料。

##### § 小結

MVP的設計常用於Web-based的軟體，因其設計重點在於資料的規劃，將暫時性的互動資料抽出後，模組內容更加的單純。

然而其架構的操作是基於事件，亦即使用者的操作行為或來自於介面的自發行為(計時器)，但這設計移除了如遠端控制、共用命令等，來源或邏集複雜的控制行為。

因此相對於大型軟體，Web-based的單頁應用程式(SPA)則適合採用此架構；但需注意，若過度將功能導入單頁內，反而會使得此頁難以維護，且若要多頁共用亦需要額外設計。
> MVP的架構類似PAC(Presentation–abstraction–control)，但不同的是PAC重視於控制的分離，使其最後結構類似樹狀，在解釋上更加接近元件(Component)化的架構樣式。

##### § 參考

+ [MVP wiki](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93presenter)

### Interactive architecture pattern summary

MV(X)系列的互動架構，不論是原始的MVC，延伸的MVP、MVVM、HMVC，乃至於變形的DV、VIPER。

其中核心概念皆是視圖(View)與模組(Model)分離，然而對於如何控制(Controller)兩者關係，就成了各種架構間的差異。

常見的差異性：

1. 商業邏輯是否皆存於控制？
2. 模組是否毫無邏輯？
3. 視圖的互動邏輯是否存於控制？
4. 邏輯的構成是否互相依賴，導致架構不可測試？
5. 視圖如何取得模組的資料？

存在於MVC的議題中，很多透過實務面的成果，也已得到較完善的結構；但這些實務設計，最大爭議還是在這樣子的定義是否符合了MV(X)架構；但這種說法僅是學術理論的完美主義問題；若對於概念的解釋，放到較為寬鬆的部分，實際問題也僅止於簡單的模組化定義。

+ MVC的優點在於集中管理的控制。
+ MVP、MVVM的優點在於控制局部化，減輕控制的壓力。

在多數文件中，選擇一個架構方案是重要選擇，但擇一而為僅能適應特定題目；就如同『一個樣式不能解決所有問題』，同樣的『一個架構不能函蓋所有議題』。

##### § 參考

+ [MVC與MVP](https://cg2010studio.com/2016/06/02/mvc%E8%88%87mvp/)
+ [iOS 架構模式 – 簡述 MVC, MVP, MVVM 和 VIPER](http://inder.com.tw/ios-architecture-patterns-mvc-mvp-mvvm-viper/)
