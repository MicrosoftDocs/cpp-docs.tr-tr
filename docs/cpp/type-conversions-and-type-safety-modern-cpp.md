---
title: Tür dönüştürmeleri ve tür güvenliği
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 629b361a-2ce1-4700-8b5d-ab4f57b245d5
ms.openlocfilehash: dbca9057622ab1a92b74e2958b8dfbe8d810fede
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246119"
---
# <a name="type-conversions-and-type-safety"></a>Tür dönüştürmeleri ve tür güvenliği

Bu belge, ortak tür dönüştürme sorunlarını tanımlar ve C++ kodunuzda bunları nasıl önleyebileceğinizi açıklar.

Bir C++ program yazdığınızda tür açısından güvenli olduğundan emin olmak önemlidir. Yani, her değişken, işlev bağımsız değişkeni ve işlev dönüş değeri kabul edilebilir bir tür veri depolamasıdır ve farklı türlerin değerlerini içeren işlemler "anlamlı olsun" ve veri kaybına neden olmaz, bit desenlerinin yanlış yorumlanması veya bellek bozulması. Değerleri bir türden diğerine kesinlikle açıkça veya örtük olarak dönüştürdüğü bir program, tanım ile tür açısından güvenlidir. Ancak, tür dönüştürmeleri, hatta güvenli olmayan dönüştürmeler bazen gereklidir. Örneğin, kayan nokta işleminin sonucunu **int**türünde bir değişkende depolamanız veya işaretsiz bir **int** içindeki değeri, imzalı bir **int**alan bir işleve geçirmeniz gerekebilir. Her iki örnek de, veri kaybına neden olabileceği veya bir değerin yeniden yorumlanabileceğinden güvenli olmayan dönüştürmeleri gösterir.

Derleyici güvenli olmayan bir dönüştürme algıladığında bir hata ya da uyarı verir. Bir hata derlemeyi durduruyor; bir uyarı derlemenin devam etmesine izin verir, ancak koddaki olası bir hatayı gösterir. Ancak, programınız uyarı olmadan derlense bile, yanlış sonuçlar üreten örtük tür Dönüştürmelere yol gösteren bir kod de içerebilir. Tür hataları, koddaki açık dönüşümler veya yayınlar tarafından da kullanılabilir.

## <a name="implicit-type-conversions"></a>Örtük tür dönüştürmeleri

Bir ifade farklı yerleşik türlerin işlenenleri içerdiğinde ve açık bir tür yoksa, derleyici, türlerin eşleşmesi için işlenenlerden birini dönüştürmek üzere yerleşik *Standart dönüştürmeleri* kullanır. Derleyici, dönüştürmeleri başarılı olana kadar iyi tanımlanmış bir sırayla dener. Seçilen dönüştürme bir yükseltmedir, derleyici bir uyarı vermez. Dönüştürme bir daraltma ise, derleyici olası veri kaybı hakkında bir uyarı verir. Gerçek veri kaybı oluşması, ilgili gerçek değerlere bağlıdır, ancak bu uyarıyı hata olarak değerlendirmenizi öneririz. Kullanıcı tanımlı bir tür varsa, derleyici, sınıf tanımında belirttiğiniz dönüştürmeleri kullanmaya çalışır. Kabul edilebilir bir dönüştürme bulamazsa, derleyici bir hata verir ve programı derlemez. Standart dönüştürmeleri yöneten kurallar hakkında daha fazla bilgi için bkz. [Standart dönüştürmeler](../cpp/standard-conversions.md). Kullanıcı tanımlı dönüştürmeler hakkında daha fazla bilgi için bkz. [Kullanıcı tanımlı dönüştürmeler (C++/CLI)](../dotnet/user-defined-conversions-cpp-cli.md).

### <a name="widening-conversions-promotion"></a>Genişletme dönüştürmeleri (yükseltme)

Genişleyen bir dönüştürmede, daha küçük bir değişkende bir değer, veri kaybı olmadan daha büyük bir değişkene atanır. Genişletme dönüştürmeleri her zaman güvende olduğundan, derleyici onları sessizce gerçekleştirir ve uyarı vermez. Aşağıdaki dönüşümler genişletme dönüştürmelerinde.

|Başlangıç|Bitiş|
|----------|--------|
|**Uzun uzun** veya **__int64** hariç tüm imzalı veya işaretsiz integral türleri|**double**|
|**bool** veya **char**|Diğer yerleşik tür|
|**Short** veya **wchar_t**|**int**, **Long**, **Long Long**|
|**int**, **Long**|**uzun uzun**|
|**float**|**double**|

### <a name="narrowing-conversions-coercion"></a>Daraltma dönüştürmeleri (zorlama)

Derleyici, daraltma dönüştürmelerini örtük olarak gerçekleştirir, ancak olası veri kaybı hakkında sizi uyarır. Bu uyarıları çok önemli yapın. Daha büyük bir değişkende bulunan değerler her zaman daha küçük bir değişkene sığacak olduğundan ve daha sonra derleyicinin uyarı vermesini sağlamak için açık bir tür ekleyerek bir veri kaybı gerçekleşmediğinden emin olmanız gerekir. Dönüştürmenin güvenli olduğundan emin değilseniz, olası veri kaybını işlemek için kodunuzda bir dizi çalışma zamanı denetimi ekleyin, böylece programınızın hatalı sonuçlar üretmesine neden olmaz.

Kayan nokta değerinin kesirli kısmı atıldığından ve kaybolduğundan, kayan nokta türünden integral türüne dönüştürme bir daraltma dönüştürmedir.

Aşağıdaki kod örneğinde bazı örtük daraltma dönüşümleri ve derleyicinin bunlar için verdiği uyarılar gösterilmektedir.

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

### <a name="signed---unsigned-conversions"></a>İmzalı-işaretsiz dönüşümler

İşaretli bir integral türü ve işaretsiz karşılığı her zaman aynı boyutlardır, ancak bit deseninin değer dönüşümü için nasıl yorumlandığını gösterir. Aşağıdaki kod örneği, aynı bit deseninin imzalı bir değer ve işaretsiz bir değer olarak yorumlanması durumunda ne olacağını gösterir. Hem `num` hem de `num2` depolanan bit, önceki çizimde gösterilenden hiçbir değişiklik değildir.

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

Değerlerin her iki yönde yeniden yorumlandığına dikkat edin. Programınız, değerin işaretinin beklediğiniz şekilde tersine göründüğü tek sonuçlar üretirse, imzalanmış ve işaretsiz integral türleri arasında örtük dönüştürmeler arayın. Aşağıdaki örnekte, ifadesinin sonucu (0-1) `num`içinde depolandığında **int** 'ten **işaretsiz int** 'e dönüştürülür. Bu, bit deseninin yeniden yorumlanmasına neden olur.

```cpp
unsigned int u3 = 0 - 1;
cout << u3 << endl; // prints 4294967295
```

Derleyici, imzalanmış ve işaretsiz integral türleri arasında örtük dönüştürmeler hakkında uyarı vermez. Bu nedenle, imzalanmamış ve imzasız Dönüştürmelere tamamen kaçınmanızı öneririz. Bunlardan kurtulamadıysanız, dönüştürmekte olan değerin sıfıra eşit veya daha büyük ve imzalı türün en büyük değerinden küçük veya ona eşit olup olmadığını algılamak için bir çalışma zamanı denetimi kodunuzu ekleyin. Bu aralıktaki değerler, yeniden yorumlanmadan imzalanmış veya işaretsiz olarak imzalanacak olarak aktarılır.

### <a name="pointer-conversions"></a>İşaretçi Dönüştürmeler

Birçok ifadede, bir C stili dizi örtük olarak dizideki ilk öğe için bir işaretçiye dönüştürülür ve sabit dönüştürmeler sessizce gerçekleşebilir. Bu kullanışlı olsa da büyük olasılıkla hataya açıktır. Örneğin, aşağıdaki hatalı tasarlanmış kod örneği sensik değildir ve ' p ' sonucunu derleyip üretir. İlk olarak, "Help" dize sabit değeri dizinin ilk öğesine işaret eden bir `char*` dönüştürülür; Bu işaretçi daha sonra son ' p ' öğesini işaret eden üç öğe tarafından artırılır.

```cpp
char* s = "Help" + 3;
```

## <a name="explicit-conversions-casts"></a>Açık dönüşümler (yayınlar)

Bir atama işlemi kullanarak, derleyiciye bir türdeki değeri başka bir türe dönüştürmeyi söyleyebilirsiniz. İki tür tamamen ilişkisiz ise derleyici bazı durumlarda bir hata oluşturacak, ancak başka durumlarda, işlem tür açısından güvenli olmasa bile bir hata oluşturmaz. Bir türden diğerine herhangi bir dönüştürme işlemi, olası bir program hatası kaynağı olduğundan, yayınları gelişigüzel şekilde kullanın. Ancak, bazı durumlarda yapılacak yayınlar bazen gerekli değildir ve tüm atamalar eşit derecede tehlikelidir. Bir tür kullanımı, kodunuzun bir daraltma dönüştürmesi gerçekleştirmesinin yanı sıra dönüştürmenin programınızın hatalı sonuçlar üretmesine neden olmadığını anlarsınız. Aslında bu, derleyiciye ne yaptığınızı bildiğinizi ve bununla ilgili uyarılar bothering. Başka bir kullanım, işaretçiden türetilmiş bir sınıftan işaretçiden tabana sınıfına dönüştürme yapmak için kullanılır. Başka bir kullanım, bir değişkenin **const**olma durumunu**sabit** olmayan bir bağımsız değişken gerektiren bir işleve geçirecek şekilde dönüştürmek için kullanılır. Bu tür atama işlemlerinin çoğu risk içerir.

C stili programlamada, aynı C stili tür dönüştürme işleci tüm tür atamalar için kullanılır.

```cpp
(int) x; // old-style cast, old-style syntax
int(x); // old-style cast, functional syntax
```

C stili atama işleci, Call işleci () ile aynıdır ve bu nedenle kodda ınconspicuou ve çok daha kolay bir şekilde görünür. Her ikisi de hatalı olduğundan, her ikisi de bir bakışta tanınmaları veya arama yapmak zordur ve **statik**, **const**ve **reinterpret_cast**herhangi bir birleşimini çağırmaya yetecek kadar birbirinden farklı olurlar. Eski stil dönüştürmenin gerçekten ne kadar zor ve hataya açık olduğunu öğrenme. Tüm bu nedenlerden dolayı, bir atama gerektiğinde aşağıdaki C++ atama işleçlerinden birini kullanmanızı öneririz. Bu, bazı durumlarda önemli ölçüde daha fazla güvenli olan ve programlama amacını çok daha açık bir şekilde gösteriyor.

- **static_cast**, yalnızca derleme zamanında denetlenen yayınlar için. **static_cast** , derleyici tamamen uyumsuz türler arasında dönüştürmeye çalıştığınız algıladığında bir hata döndürür. Ayrıca, taban işaretçisi ile türetilmiş işaretçi arasında dönüştürme yapmak için de kullanabilirsiniz, ancak derleyici çalışma zamanında bu dönüştürmelerin güvenli olup olmadığını her zaman söyleyebilir.

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

   Daha fazla bilgi için bkz. [static_cast](../cpp/static-cast-operator.md).

- **dynamic_cast**, güvenli, çalışma zamanında yapılacak işaretçiden türetilme işaretçisinin işaretçiden türetilme yapılacak kayıtları için. **Dynamic_cast** , aşağı bir **static_cast** daha güvenlidir, ancak çalışma zamanı denetimi bazı ek yük doğurur.

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

   Daha fazla bilgi için bkz. [dynamic_cast](../cpp/dynamic-cast-operator.md).

- **const_cast**, bir değişkenin **const**durumunu kaldırmak veya**const** olmayan bir değişkeni **const**olacak şekilde dönüştürmek için. Bu işleci kullanarak **sabit**olma durumunu serbest bırakmak, bir C stili tür dönüştürme kullanmakla aynı şekilde, örneğin **const dönüştürmesinin** yanlışlıkla dönüştürmeyi yanlışlıkla gerçekleştirmeye daha az olabilir. Bazen bir değişkenin **const**olma özelliğini (örneğin **, const olmayan bir parametre alan** bir işleve bir **const** değişkeni geçirmek için) dönüştürmelisiniz. Aşağıdaki örnek bunun nasıl yapılacağını göstermektedir.

    ```cpp
    void Func(double& d) { ... }
    void ConstCast()
    {
       const double pi = 3.14;
       Func(const_cast<double&>(pi)); //No error.
    }
    ```

   Daha fazla bilgi için bkz. [const_cast](../cpp/const-cast-operator.md).

- **int**için **işaretçi** gibi ilişkisiz türler arasındaki yayınlar için **reinterpret_cast**.

    > [!NOTE]
    >  Bu atama işleci, diğerleri gibi sıklıkla kullanılmaz ve diğer derleyicilere taşınabilir olması garanti edilmez.

   Aşağıdaki örnek **reinterpret_cast** **static_cast**nasıl farklılık gösterir.

    ```cpp
    const char* str = "hello";
    int i = static_cast<int>(str);//error C2440: 'static_cast' : cannot
                                  // convert from 'const char *' to 'int'
    int j = (int)str; // C-style cast. Did the programmer really intend
                      // to do this?
    int k = reinterpret_cast<int>(str);// Programming intent is clear.
                                       // However, it is not 64-bit safe.
    ```

   Daha fazla bilgi için bkz. [reinterpret_cast işleci](../cpp/reinterpret-cast-operator.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++tür sistemi](../cpp/cpp-type-system-modern-cpp.md)<br/>
[Uygulamasına geri hoş geldinizC++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
