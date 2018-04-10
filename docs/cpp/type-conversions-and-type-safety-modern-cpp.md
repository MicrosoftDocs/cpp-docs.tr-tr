---
title: Tür dönüştürmeleri ve tür güvenliği (Modern C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 629b361a-2ce1-4700-8b5d-ab4f57b245d5
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2c77b7269ae70d24878ff02c0661b60365c76d1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="type-conversions-and-type-safety-modern-c"></a>Tür Dönüştürmeleri ve Tür Güvenliği (Modern C++)
Bu belge türü dönüştürme karşılaşılan tanımlar ve nasıl bunları C++ kodunuzda önleyebilirsiniz açıklar.  
  
 C++ programı yazdığınızda, tür kullanımı uyumlu olduğundan emin olmak önemlidir. Yani, her değişken, işlev bağımsız değişkeni ve değeri kabul edilebilir bir tür verinin depolanması dönüş işlevi ve farklı türlerde değerler içeren işlemleri "anlamlı" ve bit desenleri yanlış yorumu veri kaybına neden veya Bellek Bozulması. Tür kullanımı uyumlu asla açıkça veya örtük değerleri bir türden diğerine dönüştürür bir program tarafından tanımı. Ancak, tür dönüştürmeleri, hatta güvensiz dönüşümleri, bazen gereklidir. Örneğin, bir kayan sonucunu depolamak olabilir nokta işlemi türünde bir değişken `int`, veya değeri bir imzasız geçmesi gerekebilir `int` işaretli isteyen bir işlevi için `int`. Veri kaybı veya bir değer yeniden yorumu neden olabileceğinden örneklerin her ikisi de güvenli olmayan dönüşümleri gösterilmektedir.  
  
 Derleyici güvenli olmayan bir dönüştürme algıladığında, bir hata veya uyarı verir. Bir hata derleme durdurur; bir uyarı devam etmek derleme verir, ancak kodda olası bir hatayı gösterir. Uyarılar olmadan programınızı derler olsa bile, ancak bunu hala hatalı sonuçlar örtük tür dönüştürmeleri için müşteri adayları kod içeriyor olabilir. Tür hatalarının açık dönüşümler ya da koddaki atamalar da tanıtılabilir.  
  
## <a name="implicit-type-conversions"></a>Örtük tür dönüşümleri  
 Bir ifade farklı yerleşik türündeki işlenenler içeriyor ve hiçbir açık atamaları mevcut olduğundan, yerleşik derleyici kullanır *standart dönüşümler* türleriyle eşleşecek şekilde işlenenler birini dönüştürmek için. Biri başarılı olana kadar derleyici dönüşümleri iyi tanımlanmış bir sırada çalışır. Seçili dönüştürme bir yükseltme ise, bir uyarı derleyici kesmez. Dönüştürme bir daraltma ise, derleyici olası veri kaybı hakkında bir uyarı verir. Olup gerçek veri kaybı oluştuğunda söz konusu gerçek değerlerine bağlıdır, ancak bu uyarıyı hata olarak kabul öneririz. Kullanıcı tanımlı bir tür alıyorsa, derleyici, sınıf tanımında belirtilen dönüşümleri kullanmaya çalışır. Kabul edilebilir bir dönüştürme bulamazsanız, derleyici bir hata verir ve program derlenmiyor. Standart dönüşümler yöneten kuralları hakkında daha fazla bilgi için bkz: [standart dönüşümler](../cpp/standard-conversions.md). Kullanıcı tanımlı dönüşümler hakkında daha fazla bilgi için bkz: [kullanıcı tanımlı Dönüşümler (C + +/ CLI)](../dotnet/user-defined-conversions-cpp-cli.md).  
  
### <a name="widening-conversions-promotion"></a>Genişletme Dönüşümleri (yükseltme)  
 Bir genişletme dönüştürmede daha küçük bir değişken değeri hiçbir veri kaybı olan daha büyük bir değişkene atanır. Genişletme dönüşümleri her zaman güvenli olduğundan derleyici sessiz bir şekilde gerçekleştirir ve Uyarıları kesmez. Aşağıdaki dönüşümleri dönüşümleri.  
  
|Başlangıç|Bitiş|  
|----------|--------|  
|Tüm imzalı veya dışında tam sayı türü imzasız `long long` veya`__int64`|`double`|  
|`bool`veya`char`|Herhangi bir yerleşik türü|  
|`short`veya`wchar_t`|`int`, `long`, `long long`|  
|`int`, `long`|`long long`|  
|`float`|`double`|  
  
### <a name="narrowing-conversions-coercion"></a>Daraltma Dönüşümleri (zorlama)  
 Derleyici örtük olarak daraltma dönüşümleri gerçekleştirir, ancak veri kaybı hakkında sizi uyarır. Bu uyarıların ele çok ciddiye. Ardından büyük değişken değerleri daha küçük değişken her zaman sığması için veri kaybı meydana gelmez, böylece derleyici artık bir uyarı verecek bir açık atama ekleyin. Dönüştürme güvenli olduğundan emin değilseniz, kodunuzu çalışma zamanı onay hatalı sonuçlar, program neden olmaz böylece olası veri kaybı işlemek için bir tür ekleyin. 
  
 Bir kayan gelen herhangi bir dönüştürmeye noktası olarak bir tam sayı tür türüdür daraltma dönüşümü kayan kesirli kısmı noktası çünkü değeri atılan ve kaybolabilir.  
  
 Aşağıdaki kod örneğinde dönüşümler ve bunlar için derleyici sorunları uyarıları daraltma bazı örtük gösterir.  
  
```cpp  
int i = INT_MAX + 1; //warning C4307:'+':integral constant overflow  
wchar_t wch = 'A'; //OK  
char c = wch; // warning C4244:'initializing':conversion from 'wchar_t'  
              // to 'char', possible loss of data  
unsigned char c2 = 0xfffe; //warning C4305:'initializing':truncation from  
                           // 'int' to 'unsigned char'  
int j = 1.9f; // warning C4244:'initializing':conversion from 'float' to  
              // 'int', possible loss of data  
int k = 7.7; // warning C4244:'initializing':conversion from 'double' to  
             // 'int', possible loss of data  
```  
  
### <a name="signed---unsigned-conversions"></a>İmzalı - imzasız dönüşümleri  
 İmzalı tam sayı türü ve imzasız kendisine karşılık gelen her zaman aynı boyuttadır ancak bit desenini değeri dönüşümü nasıl yorumlanır içinde farklılık gösterir. Aşağıdaki kod örneği, aynı bit desenini imzalı bir değer ve imzasız bir değer olarak yorumlanır ne olacağını gösterir. İkisi de depolanan bit desenini `num` ve `num2` hiçbir zaman önceki çizimde gösterilen gelen değiştirir.  
  
```cpp  
using namespace std;  
unsigned short num = numeric_limits<unsigned short>::max(); // #include <limits>  
short num2 = num;  
cout << "unsigned val = " << num << " signed val = " << num2 << endl;  
// Prints: unsigned val = 65535 signed val = -1  
  
// Go the other way.  
num2 = -1;  
num = num2;  
cout << "unsigned val = " << num << " signed val = " << num2 << endl;  
// Prints: unsigned val = 65535 signed val = -1  
  
```  
  
 Her iki yönde de değerleri reinterpreted dikkat edin. Programınızı beklediğinizden ters tek sonuçları hangi değerin oturum görünüyor oluşturursa, imzalı ve imzasız tam sayı türleri arasında örtük dönüşümler arayın. Aşağıdaki örnekte, ifadenin sonucu (0 - 1) örtük olarak dönüştürülür `int` için `unsigned int` zaman onu depolanır `num`. Bu, bit desenini reinterpreted neden olur.  
  
```cpp  
unsigned int u3 = 0 - 1;  
cout << u3 << endl; // prints 4294967295  
  
```  
  
 İmzalı ve imzasız tam sayı türleri arasında örtük dönüşümler hakkında derleyici uyarmaz. Bu nedenle, imzasız için imzalanmış dönüşümleri tamamen kaçının öneririz. Bunları yoksayılamaz, kodunuzu dönüştürülen değeri sıfırdan büyük veya sıfıra eşit olup olmadığını saptamak için bir çalışma zamanı denetimi ekleyin ve imzalı türü en yüksek değeri küçük veya buna eşit. Bu aralık değerleri reinterpreted olmadan imzalı imzasız veya imzasız için imzalanmış aktarmaya.  
  
### <a name="pointer-conversions"></a>İşaretçi dönüşümleri  
 Birçok ifadelerde C tarzı dizi örtük olarak dizinin ilk öğe için bir işaretçi dönüştürülür ve sabit dönüşümleri sessizce oluşabilir. Bu kullanışlı olsa da büyük olasılıkla hataya. Örneğin, aşağıdaki hatalı tasarlanmış kod örneğinde nonsensical gibi görünüyor ve henüz Visual c++'ta derlenir ve 'p' sonucunu üretir. "Yardım" dize sabit değişmez değeri için ilk olarak, dönüştürülen bir `char*` dizinin ilk öğesi işaret; bunu şimdi son öğesi 'p' işaret eden, işaretçi sonra üç öğeleri tarafından artırılır.  
  
```cpp  
char* s = "Help" + 3;  
  
```  
  
## <a name="explicit-conversions-casts"></a>Açık Dönüşümler (atamaları)  
 Atama işlemi kullanarak, bir türde bir değer başka bir türüne dönüştürmek için derleyici söyleyebilirsiniz. Derleyici, iki tür tamamen ilişkisiz ancak işlemi tür kullanımı uyumlu olsa bile diğer durumlarda, bir hata oluşturmaz bazı durumlarda bir hata ortaya koyar. Herhangi bir türden diğerine dönüştürme başka bir program hatanın olası bir kaynağı olduğundan atamaları tutumlu kullanın. Ancak, atamaları bazen gereklidir ve tüm atamaları eşit olarak tehlikeli. Bir etkili bir cast kodunuzu daraltma dönüşümü gerçekleştirdiğinde ve dönüştürme programınız hatalı sonuçlar üretmek neden olmadığını bilmek kullanılır. Gerçekte, bu derleyici yapmakta olduğunuz bildiğiniz bildirir ve uyarılarla ilgili rahatsız etme durdurmak için. Başka bir işaretçi taban sınıfı için türetilen işaretçi bir sınıftan dönüştürmek için kullanılır. Hemen dönüştürmek için başka bir kullanımıdır `const`- şahit olmayan bir gerektiren bir işleve geçirmek için bir değişken -`const` bağımsız değişkeni. Bu atama işlemlerin çoğunu bazı risk içerir.  
  
 C türü programlamada aynı C tarzı dönüştürme işleci atamaları tüm türleri için kullanılır.  
  
```cpp  
(int) x; // old-style cast, old-style syntax  
int(x); // old-style cast, functional syntax  
  
```  
  
 C türü atama işleci çağrısı işleci (.)'için aynıdır ve bu nedenle kodda inconspicuous ve overlook kolaydır. Her ikisi de bir bakışta veya arama tanıması zor ve herhangi bir bileşimini çağırmak için farklı bozuk olduğu `static`, `const`, ve `reinterpret_cast`. Eski Tarz cast gerçekte yaptığı açık zor ve hataya yatkın olabilir. Bir cast gerektiğinde bu nedenlerle, bazı durumlarda önemli ölçüde daha fazla tür kullanımı uyumlu ve programlama amacı, açıkça çok daha hızlı aşağıdaki C++ cast işleçleri, birini kullanmanızı öneririz:  
  
-   `static_cast`, derleme denetlenir atamaları zaman yalnızca. `static_cast`Derleyici tamamen uyumlu türleri arasında dönüştürme çalıştığınız algılarsa bir hata döndürür. Ayrıca bunu işaretçi temel ve türetilen işaretçi arasında dönüştürmek için kullanabilirsiniz, ancak derleyici, her zaman böyle dönüşümleri çalışma zamanında güvenli olup olmayacağını bildiremez.  
  
    ```cpp  
    double d = 1.58947;  
    int i = d;  // warning C4244 possible loss of data  
    int j = static_cast<int>(d);       // No warning.  
    string s = static_cast<string>(d); // Error C2440:cannot convert from  
                                       // double to std:string  
  
    // No error but not necessarily safe.  
    Base* b = new Base();  
    Derived* d2 = static_cast<Derived*>(b);  
  
    ```  
  
     Daha fazla bilgi için bkz: [static_cast](../cpp/static-cast-operator.md).  
  
-   `dynamic_cast`, işaretçi taban türetilmiş işaretçi için güvenli, çalışma zamanı işaretli yayınları için. A `dynamic_cast` daha güvenlidir bir `static_cast` downcasts, ancak çalışma zamanı için bazı ek yükü onay doğurur.  
  
    ```cpp  
    Base* b = new Base();  
  
    // Run-time check to determine whether b is actually a Derived*  
    Derived* d3 = dynamic_cast<Derived*>(b);  
  
    // If b was originally a Derived*, then d3 is a valid pointer.  
    if(d3)  
    {  
       // Safe to call Derived method.  
       cout << d3->DoSomethingMore() << endl;  
    }  
    else  
    {  
       // Run-time check failed.  
       cout << "d3 is null" << endl;  
    }  
  
    //Output: d3 is null;  
  
    ```  
  
     Daha fazla bilgi için bkz: [dynamic_cast](../cpp/dynamic-cast-operator.md).  
  
-   `const_cast`, hemen atama için `const`- şahit bir değişken veya olmayan bir dönüştürme -`const` olması için değişken `const`. Atama dışarıda `const`-bu işleci kullanılarak şahit olduğundan yalnızca olarak hataya yatkın C tarzı ile dışında dönüştürme kullandığından `const-cast` cast yanlışlıkla gerçekleştirmek olasılığı daha düşüktür. Hemen cast zorunda bazen `const`-şahit geçirmek için bir değişken, örneğin, bir `const` olmayan bir isteyen bir işlevi için değişken`const` parametresi. Aşağıdaki örnek bunun nasıl yapılacağı gösterilmektedir.  
  
    ```cpp  
    void Func(double& d) { ... }  
    void ConstCast()  
    {  
       const double pi = 3.14;  
       Func(const_cast<double&>(pi)); //No error.  
    }  
  
    ```  
  
     Daha fazla bilgi için bkz: [const_cast](../cpp/const-cast-operator.md).  
  
-   `reinterpret_cast`, atamaları arasında türleri gibi ilgisiz için `pointer` için `int`.  
  
    > [!NOTE]
    >  Bu atama işleci sıklıkta diğer olarak kullanılmaz ve diğer derleyiciler taşınabilmesini garantili.  
  
     Aşağıdaki örnek gösterilmektedir nasıl `reinterpret_cast` farklı `static_cast`.  
  
    ```cpp  
    const char* str = "hello";  
    int i = static_cast<int>(str);//error C2440: 'static_cast' : cannot  
                                  // convert from 'const char *' to 'int'  
    int j = (int)str; // C-style cast. Did the programmer really intend  
                      // to do this?  
    int k = reinterpret_cast<int>(str);// Programming intent is clear.  
                                       // However, it is not 64-bit safe.  
  
    ```  
  
     Daha fazla bilgi için bkz: [reinterpret_cast işleci](../cpp/reinterpret-cast-operator.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ tür sistemi](../cpp/cpp-type-system-modern-cpp.md)   
 [C++ için yeniden Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)