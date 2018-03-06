---
title: Otomatik (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
f1_keywords:
- auto_CPP
- auto
helpviewer_keywords:
- auto keyword [C++]
ms.assetid: e9d495d7-601c-4547-b897-998389a311f4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 334006e8ad06bdc174922d57d97d2d0f0335cf34
ms.sourcegitcommit: 4e01d36ffa64ea11bacf589f79d2f1df947e2510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
---
# <a name="auto-c"></a>Otomatik (C++)
Kendi başlatma ifadesinden bildirilen değişkeninin türü deduces.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
auto declarator initializer;  
```  
  
```  
[](auto param1, auto param2) {};  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `auto` Anahtar sözcüğü bir bildirilen değişken veya lambda ifadesi parametresi, başlatma ifade türünü türetme kullanmasını derleyici yönlendirir.  
  
 Kullanmanızı öneririz `auto` çoğu durum için anahtar sözcüğü — dönüştürme gerçekten istemediğiniz sürece — çünkü aşağıdaki faydaları sağlar:  
  
-   **Sağlamlık:** ifadenin türü değişirse — bir işlev dönüş türü değiştirildiğinde bu içerir — yalnızca çalışır.  
  
-   **Performans:** dönüştürme olacaktır garanti.  
  
-   **Kullanılabilirlik:** türü adı yazım sorunlar ve yazım hatalarını hakkında endişelenmeniz gerekmez.  
  
-   **Verimlilik:** , kodlama daha etkili olabilir.  
  
 Hangi değil kullanmak istediğiniz dönüştürme durumlarda `auto`:  
  
-   Belirli bir tür ve hiçbir şey istediğinizde yapın.  
  
-   İfade şablonu yardımcı türü — örneğin, `(valarray+valarray)`.  
  
 Kullanılacak `auto` anahtar sözcüğü bir değişkeni bildirmek için bir tür yerine kullanın ve başlatma ifade belirtin. İn addition, değiştirebileceğiniz `auto` tanımlayıcıları ve bildirimler gibi kullanarak anahtar sözcüğü `const`, `volatile`, işaretçisi (`*`), başvuru (`&`) ve rvalue başvuru `(&&`). Derleyici başlatma ifadeyi hesaplar ve değişken türünü türetme için bu bilgileri kullanır.  
  
 Başlatma ifade atama (eşittir işareti sözdizimi) doğrudan başlatma (işlevi stili sözdizimi) olabilir bir [new işleci](new-operator-cpp.md) ifadesi veya başlatma ifadesi olabilir  *için aralığı-bildirim* parametresinde bir [aralık tabanlı için deyimi (C++)](../cpp/range-based-for-statement-cpp.md) deyimi. Daha fazla bilgi için bkz: [başlatıcıları](../cpp/initializers.md) ve bu belgenin sonraki bölümlerinde kod örnekleri.  
  
 `auto` Anahtar sözcüğü bir tür için bir yer tutucudur, ancak kendisi değil bir türü. Bu nedenle, `auto` anahtar sözcüğü kullanılamaz atamaları veya işleçleri gibi [sizeof](../cpp/sizeof-operator.md) ve [TypeID](../windows/typeid-cpp-component-extensions.md).  
  
## <a name="usefulness"></a>Yararlılığını  
 `auto` Karmaşık bir türe sahip bir değişken bildirmek için basit bir yol bir anahtardır. Örneğin, kullanabileceğiniz `auto` başlatma ifade burada içerir şablonlar, işlev işaretçileri veya üye işaretçileri bir değişken bildirmek için.  
  
 Aynı zamanda `auto` bildirme ve bir lambda ifadesi bir değişkene başlatmak için. Lambda ifadesi türü yalnızca derleyiciye bilindiğinden değişkeninin türü kendiniz bildiremezsiniz. Daha fazla bilgi için bkz: [Lambda ifadeleri örnekleri](../cpp/examples-of-lambda-expressions.md).  
  
## <a name="trailing-return-types"></a>Sondaki dönüş türleri  
 Kullanabileceğiniz `auto`, birlikte `decltype` tür Şablon Kütüphanesi yazma yardımcı olmak için tanımlayıcısı. Kullanım `auto` ve `decltype` şablon işlevi, return bildirmek için şablon değişkenlerinin türlerinde türüne bağlıdır. Veya kullanmak `auto` ve `decltype` başka bir işlevi çağrısı sarmalar ve ardından bu diğer işlevinin dönüş türü ne olursa olsun döndüren bir şablon işlevi bildirmek için. Daha fazla bilgi için bkz: [decltype](../cpp/decltype-cpp.md).  
  
## <a name="references-and-cv-qualifiers"></a>References ve MS-niteleyicileri  
 Bu kullanarak Not `auto` başvurular, const niteleyicileri ve volatile niteleyicileri bırakır. Aşağıdaki örnek göz önünde bulundurun:  
  
```cpp  
// cl.exe /analyze /EHsc /W4  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
    int count = 10;  
    int& countRef = count;  
    auto myAuto = countRef;  
  
    countRef = 11;  
    cout << count << " ";  
  
    myAuto = 12;  
    cout << count << endl;  
}  
  
```  
  
 Çıktı önceki örnekte myAuto int, bir int başvuru olduğundan `11 11`değil `11 12` başvuru niteleyici bırakılmış değil, durumda olduğu gibi `auto`.  
  
## <a name="type-deduction-with-braced-initializers-c14"></a>Küme ayracı içine alınan başlatıcıları (C ++ 14) ile kesintisi yazın  
 Aşağıdaki kod exmample ayraçlar kullanılmasını otomatik değişkeni başlayamadı gösterilmektedir. B ve C arasındaki ve A arasındaki farkı unutmayın ve E.  
  
```cpp  
#include <initializer_list>  
  
int main()  
{  
    // std::initializer_list<int>  
    auto A = { 1, 2 };  
  
    // std::initializer_list<int>  
    auto B = { 3 };  
  
    // int  
    auto C{ 4 };  
  
    // C3535: cannot deduce type for 'auto' from initializer list'  
    auto D = { 5, 6.7 };  
  
    // C3518 in a direct-list-initialization context the type for 'auto'  
    // can only be deduced from a single initializer expression  
    auto E{ 8, 9 };  
  
    return 0;  
}  
```  
  
## <a name="restrictions-and-error-messages"></a>Kısıtlamaları ve hata iletileri  
 Kullanma kısıtlamaları aşağıdaki tabloda listelenmektedir `auto` anahtar sözcüğü ve derleyicisi yayar karşılık gelen bir tanılama hata iletisi.  
  
|Hata sayısı|Açıklama|  
|------------------|-----------------|  
|[C3530](../error-messages/compiler-errors-2/compiler-error-c3530.md)|`auto` Anahtar sözcüğü herhangi diğer tür-belirteci ile ilişkilendirilemez.|  
|[C3531](../error-messages/compiler-errors-2/compiler-error-c3531.md)|İle bildirilmiş bir simge `auto` anahtar sözcüğü bir başlatıcı olması gerekir.|  
|[C3532](../error-messages/compiler-errors-2/compiler-error-c3532.md)|Yanlış kullandığınızdan `auto` türü bildirmek için anahtar sözcüğü. Örneğin, bir yöntemin dönüş türü veya bir dizi bildirildi.|  
|[C3533](../error-messages/compiler-errors-2/compiler-error-c3533.md), [C3539](../error-messages/compiler-errors-2/compiler-error-c3539.md)|Bir parametre veya şablon bağımsız değişkeni ile bildirilemez `auto` anahtar sözcüğü.|  
|[C3535](../error-messages/compiler-errors-2/compiler-error-c3535.md)|Bir yöntemi veya şablon parametresi ile bildirilemez `auto` anahtar sözcüğü.|  
|[C3536](../error-messages/compiler-errors-2/compiler-error-c3536.md)|Bir simge başlatılmadan kullanılamaz. Uygulamada, bu değişken kendisini başlatmak için kullanılamaz anlamına gelir.|  
|[C3537](../error-messages/compiler-errors-2/compiler-error-c3537.md)|İle bildirilen bir türe atanamaz `auto` anahtar sözcüğü.|  
|[C3538](../error-messages/compiler-errors-2/compiler-error-c3538.md)|İle bildirilen bildirimcisi listesindeki tüm sembolleri `auto` anahtar sözcüğü aynı türe çözümlemelidir. Daha fazla bilgi için bkz: [bildirimler ve tanımlar](declarations-and-definitions-cpp.md).|  
|[C3540](../error-messages/compiler-errors-2/compiler-error-c3540.md), [C3541](../error-messages/compiler-errors-2/compiler-error-c3541.md)|[Sizeof](../cpp/sizeof-operator.md) ve [TypeID](../windows/typeid-cpp-component-extensions.md) işleçleri ile bildirilmiş bir simge uygulanamaz `auto` anahtar sözcüğü.|  
  
## <a name="examples"></a>Örnekler  
 Bu kod parçaları, yollardan bazılarını göstermek `auto` anahtar sözcüğü kullanılabilir.  
  
 Aşağıdaki bildirimler eşdeğerdir. Değişken ilk deyiminde `j` türü olarak bildirilmiş `int`. Değişken ikinci deyiminde `k` türü anlaşılabilen `int` başlatma ifadesi (0) bir tamsayı olduğundan.  
  
```cpp  
int j = 0;  // Variable j is explicitly type int.  
auto k = 0; // Variable k is implicitly type int because 0 is an integer.  
```  
  
 Aşağıdaki bildirimler eşdeğer ancak ikinci bildirim ilk basittir. Kullanmak için en ilgi çekici nedenlerden biri dolayısıyla `auto` Basitlik bir anahtardır.  
  
```cpp  
map<int,list<string>>::iterator i = m.begin();   
auto i = m.begin();   
```  
  
 Aşağıdaki kod parçası değişkenleri türünü bildirir `iter` ve `elem` zaman `for` ve aralık `for` döngü Başlat.  
  
```cpp  
// cl /EHsc /nologo /W4  
#include <deque>  
using namespace std;  
  
int main()  
{  
    deque<double> dqDoubleData(10, 0.1);  
  
    for (auto iter = dqDoubleData.begin(); iter != dqDoubleData.end(); ++iter)  
    { /* ... */ }  
  
    // prefer range-for loops with the following information in mind  
    // (this applies to any range-for with auto, not just deque)  
  
    for (auto elem : dqDoubleData) // COPIES elements, not much better than the previous examples  
    { /* ... */ }  
  
    for (auto& elem : dqDoubleData) // observes and/or modifies elements IN-PLACE  
    { /* ... */ }  
  
    for (const auto& elem : dqDoubleData) // observes elements IN-PLACE  
    { /* ... */ }  
}  
```  
  
 Aşağıdaki kod parçası kullanan `new` işaretçileri bildirmek için işleci ve işaretçi bildirimi.  
  
```cpp  
double x = 12.34;  
auto *y = new auto(x), **z = new auto(&x);  
```  
  
 Sonraki kod parçası, her bildirim deyiminde birden çok simgeleri bildirir. Tüm simge her deyiminde aynı türünü çözümlemek dikkat edin.  
  
```cpp  
auto x = 1, *y = &x, **z = &y; // Resolves to int.  
auto a(2.01), *b (&a);         // Resolves to double.  
auto c = 'a', *d(&c);          // Resolves to char.  
auto m = 1, &n = m;            // Resolves to int.  
```  
  
 Bu kod parçası koşullu işleç kullanır (`?:`) değişkeni bildirmek için `x` 200 değerine sahip bir tamsayı olarak:  
  
```cpp  
int v1 = 100, v2 = 200;  
auto x = v1 > v2 ? v1 : v2;  
```  
  
 Aşağıdaki kod parçası değişkenini `x` yazmak için `int`, değişken `y` yazmanız için bir başvuru `const int`ve değişken `fp` türü döndüren bir işlev işaretçisi için `int`.  
  
```cpp  
int f(int x) { return x; }  
int main()  
{  
    auto x = f(0);  
    const auto & y = f(1);  
    int (*p)(int x);  
    p = f;  
    auto fp = p;  
    //...  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Auto anahtar sözcüğü](../cpp/auto-keyword.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [/ZC:Auto (değişken türünü)](../build/reference/zc-auto-deduce-variable-type.md)   
 [sizeof işleci](../cpp/sizeof-operator.md)   
 [typeid](../windows/typeid-cpp-component-extensions.md)   
 [new işleci](new-operator-cpp.md)   
 [Bildirimler ve tanımlar](declarations-and-definitions-cpp.md)   
 [Lambda ifadeleri örnekleri](../cpp/examples-of-lambda-expressions.md)   
 [Başlatıcılar](../cpp/initializers.md)   
 [decltype](../cpp/decltype-cpp.md)