---
title: Tür Dönüştürmeleri ve Tür Güvenliği (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 629b361a-2ce1-4700-8b5d-ab4f57b245d5
ms.openlocfilehash: 201f09cc9ac17f76634103c9c9b6c0259c8a8637
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51332627"
---
# <a name="type-conversions-and-type-safety-modern-c"></a>Tür Dönüştürmeleri ve Tür Güvenliği (Modern C++)

Bu belge, tür dönüştürme için yaygın sorunlar tanımlanmakta ve nasıl bunları C++ kodunuzu önleyebilirsiniz açıklar.

Bir C++ programını yazdığınızda, tür kullanımı uyumlu olmasını sağlamak önemlidir. Yani, her değişken, işlev bağımsız değişkeni ve işlev dönüş değeri kabul edilebilir bir tür verileri depolamak ve farklı türlerde değerler ilgili işlemleri "mantıklı" ve bit desenlerinin yanlış yorumlanmasını veri kaybına neden olmayan veya Bellek Bozulması. Tür kullanımı uyumlu asla açıkça veya dolaylı olarak değerleri bir türden diğerine dönüştürür bir program tarafından tanımı. Ancak, tür dönüştürmeleri, güvenli olmayan dönüştürme bile, bazen gereklidir. Örneğin, bir kayan sonucunu depolamak zorunda kalabilirsiniz işlemi türündeki bir değişkene işaret **int**, veya değer işaretsiz bir geçirmeniz gerekebilir **int** imzalı bir alan bir işleve  **int**. Örneklerin her ikisi de, veri kaybı veya bir değerin yeniden yorumu neden olabileceğinden güvenli olmayan dönüştürme gösterilmektedir.

Derleyici, güvenli olmayan bir dönüştürme algıladığında, bir hata veya uyarı verir. Bir hata derleme durdurur; bir uyarı, devam etmek derleme verir ancak koddaki olası bir hatayı gösterir. Programınızı uyarılar olmadan derleme olsa bile, ancak bunu hala yanlış sonuçlar örtük tür dönüştürmelerini müşteri adayları kod içerebilir. Tür hataları, açık dönüştürmeler ya da kod atamaları da tanıtılabilir.

## <a name="implicit-type-conversions"></a>Örtük tür dönüştürmelerini

Bir ifade işlenenleri farklı yerleşik türleri içeriyor ve açık cast mevcut olduğunda yerleşik derleyici kullanır *standart dönüştürmeler* türleri aynı şekilde işlenenlerden dönüştürmek için. Derleyici, biri başarılı olana kadar iyi tanımlanmış bir dizi Dönüşümlerde çalışır. Seçili dönüştürme promosyon ise, derleyici bir uyarı kesmez. Dönüştürme bir daraltma ise, derleyici, olası veri kaybı ile ilgili bir uyarı verir. Olup gerçek veri kaybı oluştuğunda ilgili gerçek değerlerine bağlıdır, ancak bu uyarıyı hata olarak gör öneririz. Kullanıcı tanımlı bir tür söz konusu ise, derleyici, sınıf tanımında belirttiğiniz dönüştürmeler kullanmaya çalışır. Kabul edilebilir bir dönüştürme bulamazsanız, derleyici bir hata verir ve program derlenmiyor. Standart dönüştürmeler yöneten kurallar hakkında daha fazla bilgi için bkz: [standart dönüştürmeler](../cpp/standard-conversions.md). Kullanıcı tanımlı dönüştürmeler hakkında daha fazla bilgi için bkz. [kullanıcı tanımlı Dönüşümler (C + +/ CLI)](../dotnet/user-defined-conversions-cpp-cli.md).

### <a name="widening-conversions-promotion"></a>Genişletme dönüştürmeleri (yükseltme)

Öğesinde Genişletme dönüşümü, veri kaybı olmadan büyük bir değişkenle daha küçük bir değişkene bir değer atanır. Genişletme dönüştürmeleri her zaman güvenli olduğu için derleyici sessiz bir şekilde gerçekleştirir ve Uyarıları kesmez. Aşağıdaki dönüşümlerden dönüşümlerdir.

|Başlangıç|Bitiş|
|----------|--------|
|Tüm imzalı veya dışında tamsayı türü imzasız **uzun uzun** veya **__int64**|**double**|
|**bool** veya **char**|Herhangi bir yerleşik türü|
|**kısa** veya **wchar_t**|**int**, **uzun**, **uzun uzun**|
|**int**, **uzun**|**Long long**|
|**float**|**double**|

### <a name="narrowing-conversions-coercion"></a>Daraltma Dönüşümleri (zorlama)

Derleyici örtük olarak daraltma dönüştürmelerini gerçekleştirir, ancak veri kaybı hakkında sizi uyarır. Bu uyarıları ele çok ciddi bir şekilde. Ardından daha küçük bir değişkende büyük değişken değerler her zaman sığması için veri kaybı meydana gelir, böylece derleyici artık bir uyarı verir açık bir tür dönüştürme ekleyin. Dönüştürme güvenli olduğundan emin değilseniz, programınızın yanlış sonuçlar neden olmaz, böylece olası veri kaybı işlemek için çalışma zamanı denetimi tür kod ekleyin.

Kayan öğesinden herhangi bir dönüştürme türü bir tamsayı türüne olduğundan bir daraltma dönüşümü kesirli bölümü kayan noktası değeri noktası atılır ve kaybolur.

Aşağıdaki kod örneği, bazı örtük dönüştürmeler ve derleyicinin bunları için sorunları uyarılar daraltma gösterir.

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

### <a name="signed---unsigned-conversions"></a>İmzalı - işaretsiz dönüştürmeler

İşaretli bir integral türe ve imzasız kendisine karşılık gelen her zaman aynı boyuttaysa, ancak bit deseni değeri dönüştürme için nasıl yorumlanır içinde farklılık gösterir. Aşağıdaki kod örneği, aynı bit deseninin imzalı değer olarak ve işaretsiz bir değer olarak yorumlanır ne olacağını gösterir. Her ikisinde de depolanan bir bit desenine `num` ve `num2` hiçbir zaman önceki çizimde gösterilen gelen değiştirir.

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

Değerler her iki yönde düşürülen dikkat edin. Programınızı beklediğinizden ters tek sonuçları hangi değerin oturum görünüyor oluşturursa, imzalı ve imzasız tamsayı türleri arasında örtük dönüştürme arayın. Aşağıdaki örnekte, ifadenin sonucunu (0 - 1) örtük olarak dönüştürülür **int** için **işaretsiz int** olduğunda, depolanan `num`. Bu bit deseninin düşürülen neden olur.

```cpp
unsigned int u3 = 0 - 1;
cout << u3 << endl; // prints 4294967295
```

Derleyici, işaretli ve işaretsiz integral türleri arasında örtük dönüştürme hakkında uyarmaz. Bu nedenle, imzasız için imzalanmış dönüştürmeler tamamen önlemek öneririz. Bunları yoksayılamaz ise kodunuza dönüştürülen değerin daha büyük veya sıfıra eşit olup olmadığını algılamak için bir çalışma zamanı denetimi ekleyin ve en yüksek değeri işaretli tür küçüktür veya eşittir. Bu aralıktaki değerleri imzalanmamış veya işaretsiz düşürülen olmadan oturum açmış nden aktarırız.

### <a name="pointer-conversions"></a>İşaretçi dönüşümleri

Birçok ifadelerde dizideki ilk öğe işaretçisi için bir C tarzı dizi örtük olarak dönüştürülür ve sabit dönüştürmeler sessizce oluşabilir. Bu kullanışlı olsa da büyük olasılıkla hata yapmaya açık. Örneğin, aşağıdaki kötü tasarlanmış bir kod örneği nonsensical gibi görünüyor ve henüz Visual c++'ta derlenir ve 'p' bir sonuç üretir. "Yardım" dize sabit hazır değer için ilk olarak, dönüştürülen bir `char*` dizisinin ilk öğesine işaret eder; böylece onu artık son öğesi 'p' işaret işaretçiyle ardından üç öğe tarafından artırılır.

```cpp
char* s = "Help" + 3;
```

## <a name="explicit-conversions-casts"></a>Açık dönüştürmeler (yayınları)

Tür dönüştürme işlemini kullanarak, bir türün bir değerini başka bir türe dönüştürmek için derleyici bildirebilirsiniz. Derleyici, iki tür tamamen ilişkisiz hak Kazandıysanız ancak işlemi, tür kullanımı uyumlu olmasa bile diğer durumlarda, bir hata oluşturmaz bazı durumlarda bir hata verir. Atamalar, herhangi bir türden diğerine dönüştürme başka bir programın hatasının olası bir kaynak olduğundan tedbirli şekilde kullanın. Ancak, yayınları bazen gereklidir ve tüm atamaları eşit tehlikeli. Bir etkili bir tür dönüştürme bir daraltma dönüşümü kodunuzu gerçekleştirir ve dönüştürme programınızın yanlış sonuçlar neden olmadığını bildiğiniz kullanılır. Aslında bu neler yaptığını bilmek derleyiciye ve uyarılarla ilgili rahatsız etme durdurmak için. Başka bir işaretçi temel sınıfına işaretçi-türetilmiş bir sınıftan dönüştürme için kullanılır. Hemen dönüştürme için başka bir kullanılır **const**- ness olmayan bir gerektiren bir işleve geçirilecek bir değişkenin -**const** bağımsız değişken. Bazı risk bu dönüştürme işlemleri çoğunu içerir.

C stili programlamada, aynı C stili tür dönüştürme işleci, her türden atamalar için kullanılır.

```cpp
(int) x; // old-style cast, old-style syntax
int(x); // old-style cast, functional syntax
```

C stili tür dönüştürme işleci çağrısı işleci ()'olarak aynıdır ve bu nedenle inconspicuous kod içinde ve kolayca gözden kaçabilir kolaydır. Her ikisi de bir bakışta veya arama tanımak zordur ve bunlar herhangi bir birleşimini çağırmak için farklı hatalı olduğu **statik**, **const**, ve **reinterpret_cast**. Eski stil atama gerçekten yaptıklarını anlamak zor ve hata yapmaya açık olabilir. Bir yayın gerektiğinde bu nedenlerle, bazı durumlarda önemli ölçüde daha fazla tür kullanımı uyumlu ve hangi programlama hedefini açıkça çok daha hızlı aşağıdaki C++ atama işleçleri, birini kullanmanızı öneririz:

- **static_cast**, derleme sırasında denetlenir yayınları zaman yalnızca. **static_cast** derleyici tamamen uyumlu olmayan türleri arasında dönüştürme çalıştığınız algılarsa bir hata döndürür. Ayrıca, işaretçi temel ve türetilmiş işaretçi arasında dönüştürme için kullanabilirsiniz, ancak derleyici, her zaman bu tür dönüştürmeler çalışma zamanında güvenli olup olmayacağını bildiremez.

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

   Daha fazla bilgi için [static_cast](../cpp/static-cast-operator.md).

- **dynamic_cast**, işaretçi temel alınan işaretçi için güvenli, çalışma zamanı işaretli yayınları için. A **dynamic_cast** daha güvenlidir bir **static_cast** onay, alt türe çevirme işlemleri, ancak çalışma zamanı, bazı ek yüke neden olur.

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

   Daha fazla bilgi için [dynamic_cast](../cpp/dynamic-cast-operator.md).

- **const_cast**hemen atama için **const**- ness bir değişkenin veya olmayan bir dönüştürme -**const** olmasını değişkeni **const**. Hemen atama **const**-ness kullanarak bu işleci yalnızca gibi hataya eğilimli C stili atama ile hariç kullandığından olan **const atama** yanlışlıkla dönüştürme gerçekleştirmek daha düşüktür. Bazen hemen türüne sahip **const**-ness geçirmek için bir değişken, örneğin, bir **const** olmayan bir alan bir işlev için değişken**const** parametresi. Aşağıdaki örnek bunun nasıl yapılacağı gösterilmektedir.

    ```cpp
    void Func(double& d) { ... }
    void ConstCast()
    {
       const double pi = 3.14;
       Func(const_cast<double&>(pi)); //No error.
    }
    ```

   Daha fazla bilgi için [const_cast](../cpp/const-cast-operator.md).

- **reinterpret_cast**yayınları arasında gibi türler ilgisiz için **işaretçi** için **int**.

    > [!NOTE]
    >  Bu tür dönüştürme işleci olarak diğerleriyle genellikle kullanılmaz ve diğer derleyiciler için taşınabilir olması garantili.

   Aşağıdaki örnekte nasıl **reinterpret_cast** farklıdır **static_cast**.

    ```cpp
    const char* str = "hello";
    int i = static_cast<int>(str);//error C2440: 'static_cast' : cannot
                                  // convert from 'const char *' to 'int'
    int j = (int)str; // C-style cast. Did the programmer really intend
                      // to do this?
    int k = reinterpret_cast<int>(str);// Programming intent is clear.
                                       // However, it is not 64-bit safe.
    ```

   Daha fazla bilgi için [reinterpret_cast işleci](../cpp/reinterpret-cast-operator.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ tür sistemi](../cpp/cpp-type-system-modern-cpp.md)<br/>
[C++ tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)