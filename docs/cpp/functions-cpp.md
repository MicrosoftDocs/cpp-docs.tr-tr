---
title: İşlevler [C++]
ms.date: 11/19/2018
helpviewer_keywords:
- defaults, arguments
- function definitions
- function definitions, about function definitions
- default arguments
- declarators, functions
ms.assetid: 33ba01d5-75b5-48d2-8eab-5483ac7d2274
ms.openlocfilehash: 5beadbbf283a64f12dab7f0ee39a267ec1797861
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213443"
---
# <a name="functions-c"></a>İşlevler [C++]

İşlev, bazı işlemleri gerçekleştiren bir kod bloğudur. Bir işlev isteğe bağlı olarak, çağrı yapanların işleve bağımsız değişkenleri geçmesini sağlayan giriş parametrelerini tanımlayabilir. Bir işlev, isteğe bağlı olarak bir değeri çıkış olarak döndürebilir. İşlevler, tek bir yeniden kullanılabilir blok içinde yaygın işlemleri kapsüllemek için faydalıdır ve bu, işlevin ne yaptığını açıkça açıklayan bir ad ile idealdir. Aşağıdaki işlev, bir çağıranın iki tamsayı kabul eder ve toplamlarını döndürür; *a* ve *b* , türünde *parametrelerdir* **`int`** .

```cpp
int sum(int a, int b)
{
    return a + b;
}
```

İşlev, programdaki herhangi bir sayıda konumdan çağrılabilir veya *çağrılabilir*. İşleve geçirilen değerler, türleri işlev tanımındaki parametre türleriyle uyumlu olması gereken *bağımsız değişkenlerdir*.

```cpp
int main()
{
    int i = sum(10, 32);
    int j = sum(i, 66);
    cout << "The value of j is" << j << endl; // 108
}
```

İşlev uzunluğuna yönelik pratik bir sınır yoktur, ancak iyi tanımlanmış tek bir görev gerçekleştiren işlevler için iyi bir tasarım sağlar. Karmaşık algoritmalar mümkün olduğunda kolayca anlaşılması kolay bir işlevlere bölünmüştür.

Sınıf kapsamında tanımlı işlevlere üye işlevleri denir. C++ ' da, diğer dillerin aksine, bir işlev ad alanı kapsamında da tanımlanabilir (örtük genel ad alanı dahil). Bu işlevler, *ücretsiz işlevler* veya *üye olmayan işlevler*olarak adlandırılır; Bunlar, standart kitaplıkta yaygın olarak kullanılırlar.

İşlevler *aşırı yüklenmiş*olabilir, bu da bir işlevin farklı sürümlerinin, biçimsel parametrelerin sayısı ve/veya türü farklı olduğunda aynı adı paylaşabileceği anlamına gelir. Daha fazla bilgi için bkz. [Işlev aşırı yüklemesi](../cpp/function-overloading.md).

## <a name="parts-of-a-function-declaration"></a>İşlev bildiriminin kısımları

En az bir işlev *bildirimi* dönüş türü, işlev adı ve parametre listesinden oluşur (boş olabilir) ve derleyiciye ek yönergeler sağlayan isteğe bağlı anahtar sözcüklerle birlikte. Aşağıdaki örnek bir işlev bildirimidir:

```cpp
int sum(int a, int b);
```

Bir işlev tanımı, bir bildirimden ve gövde ayraçları arasındaki tüm kod olan *gövdeden*oluşur:

```cpp
int sum(int a, int b)
{
    return a + b;
}
```

Bir işlev bildirimi, sonra noktalı virgül gelen bir programda birden çok yerde görünebilir. Her bir çeviri biriminde bu işleve yapılan çağrılardan önce gelmelidir. İşlev tanımı, tek bir tanım kuralına (ODR) göre yalnızca programda bir kez görünmelidir.

İşlev bildiriminin gerekli bölümleri şunlardır:

1. İşlevin döndürdüğü değerin türünü belirten dönüş türü veya **`void`** hiçbir değer döndürülmediğinde. C++ 11 ' de, **`auto`** derleyicinin türü Return ifadesinden çıkarması için geçerli bir dönüş türüdür. C++ 14 ' te `decltype(auto)` de izin verilir. Daha fazla bilgi için bkz. aşağıdaki dönüş türlerinde tür kesintisi.

1. Bir harf veya alt çizgi ile başlaması gereken işlev adı ve boşluk içermemelidir. Genel olarak, standart kitaplık işlev adlarında önde gelen alt çizgiler özel üye işlevlerini veya kodunuz tarafından kullanılmak üzere tasarlanmamış üye olmayan işlevleri gösterir.

1. Parametre listesi, küme ayracı ile ayrılmış, virgülle ayrılmış sıfır veya daha fazla parametre kümesi ve isteğe bağlı olarak, değerleri işlev gövdesi içinde erişilebilen yerel bir ad.

İşlev bildiriminin isteğe bağlı kısımları şunlardır:

1. **`constexpr`**, işlevin dönüş değerinin sabit bir değer olduğunu ve derleme zamanında hesaplanamayacağını gösterir.

    ```cpp
    constexpr float exp(float x, int n)
    {
        return n == 0 ? 1 :
            n % 2 == 0 ? exp(x * x, n / 2) :
            exp(x * x, (n - 1) / 2) * x;
    };
    ```

1. Bağlantı belirtimi **`extern`** veya **`static`** .

    ```cpp
    //Declare printf with C linkage.
    extern "C" int printf( const char *fmt, ... );

    ```

   Daha fazla bilgi için bkz. [çeviri birimleri ve bağlantısı](../cpp/program-and-linkage-cpp.md).

1. **`inline`** Bu, derleyiciye işlev kodunun kendisi ile her çağrısını değiştirmesini söyler. satır içi bir işlevin hızlı bir şekilde çalıştırıldığı ve kodun performans açısından kritik bölümünde tekrar tekrar çağrıldığı senaryolarda performans sağlanmasına yardımcı olabilir.

    ```cpp
    inline double Account::GetBalance()
    {
        return balance;
    }
    ```

   Daha fazla bilgi için bkz. [satır Içi işlevler](../cpp/inline-functions-cpp.md).

1. **`noexcept`** İşlevin bir özel durum yapıp oluşturmadığını belirten bir ifade. Aşağıdaki örnekte, ifadesi olarak değerlendirilirse, işlev bir özel durum oluşturmaz `is_pod` **`true`** .

    ```cpp
    #include <type_traits>

    template <typename T>
    T copy_object(T& obj) noexcept(std::is_pod<T>) {...}
    ```

   Daha fazla bilgi için bkz. [`noexcept`](../cpp/noexcept-cpp.md).

1. (Yalnızca üye işlevleri) İşlevin veya olup olmadığını belirten CV niteleyicileri **`const`** **`volatile`** .

1. (Yalnızca üye işlevleri) **`virtual`** , **`override`** , veya **`final`** . **`virtual`** bir işlevin türetilmiş bir sınıfta geçersiz kılınabileceğini belirtir. **`override`** türetilmiş sınıftaki bir işlevin sanal işlevi geçersiz kıldığı anlamına gelir. **`final`** başka bir türetilmiş sınıfta bir işlevin geçersiz kılınmadığı anlamına gelir. Daha fazla bilgi için bkz. [sanal işlevler](../cpp/virtual-functions.md).

1. (yalnızca üye işlevleri) **`static`** bir üye işlevine uygulandığında, işlevin sınıfın herhangi bir nesne örneğiyle ilişkilendirilmemiş olması anlamına gelir.

1. (Yalnızca statik olmayan üye işlevleri) Örtük nesne parametresi (), bir rvalue başvurusu ve bir lvalue başvurusu olduğunda, bir işlevin ne zaman seçim olduğunu derleyiciye belirten ref niteleyicisi `*this` . Daha fazla bilgi için bkz. [Işlev aşırı yüklemesi](function-overloading.md#ref-qualifiers).

Aşağıdaki şekilde bir işlev tanımının bölümleri gösterilmektedir. Gölgeli alan, işlev gövdesidir.

![Bir işlev tanımının bölümleri](../cpp/media/vc38ru1.gif "Bir işlev tanımının bölümleri") <br/>
Bir işlev tanımının bölümleri

## <a name="function-definitions"></a>İşlev tanımları

Bir *işlev tanımı* , değişken bildirimleri, deyimleri ve ifadeleri içeren küme ayraçları ve işlev gövdesinden oluşur. Aşağıdaki örnekte, bir bütün işlev tanımı gösterilmektedir:

```cpp
    int foo(int i, std::string s)
    {
       int value {i};
       MyClass mc;
       if(strcmp(s, "default") != 0)
       {
            value = mc.do_something(i);
       }
       return value;
    }
```

Gövde içinde belirtilen değişkenlere yerel değişkenler veya Yereller denir. İşlev çıktığında kapsam dışına çıkırlar; Bu nedenle, bir işlev asla yerel bir başvuru döndürmemelidir!

```cpp
    MyClass& boom(int i, std::string s)
    {
       int value {i};
       MyClass mc;
       mc.Initialize(i,s);
       return mc;
    }
```

## <a name="const-and-constexpr-functions"></a>const ve constexpr işlevleri

**`const`** İşlevin, sınıftaki herhangi bir veri üyesinin değerlerini değiştirmesine izin verilmediğini belirtmek için olarak bir üye işlevi bildirebilirsiniz. Bir üye işlevi olarak bildirerek **`const`** , derleyicinin *const doğruluğu*zorlayacağına yardımcı olursunuz. Birisi yanlışlıkla olarak belirtilen bir işlevi kullanarak nesneyi değiştirmeye çalışırsa **`const`** , bir derleyici hatası tetiklenir. Daha fazla bilgi için bkz. [const](const-cpp.md).

Bir işlevi **`constexpr`** , ürettiği değer derleme zamanında belirlenebileceği zaman bildirin. Constexpr işlevi genellikle normal işlevden daha hızlı yürütülür. Daha fazla bilgi için bkz. [`constexpr`](constexpr-cpp.md).

## <a name="function-templates"></a>İşlev Şablonları

Bir işlev şablonu, sınıf şablonuna benzer; şablon bağımsız değişkenlerine göre somut işlevler oluşturur. Çoğu durumda, şablon tür bağımsız değişkenlerini çıkarsayabilir ve bu nedenle bunları açıkça belirtmek gerekli değildir.

```cpp
template<typename Lhs, typename Rhs>
auto Add2(const Lhs& lhs, const Rhs& rhs)
{
    return lhs + rhs;
}

auto a = Add2(3.13, 2.895); // a is a double
auto b = Add2(string{ "Hello" }, string{ " World" }); // b is a std::string
```

Daha fazla bilgi için bkz. [Işlev şablonları](../cpp/function-templates.md)

## <a name="function-parameters-and-arguments"></a>İşlev parametreleri ve bağımsız değişkenler

Bir işlevde, her birinin işlev gövdesi içinde erişilebilen bir adı olan sıfır veya daha fazla türden oluşan, virgülle ayrılmış bir parametre listesi bulunur. Bir işlev şablonu, ek tür veya değer parametreleri belirtebilir. Çağıran, türleri parametre listesiyle uyumlu somut değerler olan bağımsız değişkenleri geçirir.

Varsayılan olarak, bağımsız değişkenler değere göre işleve geçirilir, bu da işlevin geçirilmiş nesnenin bir kopyasını aldığı anlamına gelir. Büyük nesneler için, bir kopyanın pahalıdır ve her zaman gerekli değildir. Bağımsız değişkenlerin başvuruya göre geçirilmesini sağlamak için (özel lvalue başvurusu), parametresine bir başvuru nicelik değeri ekleyin:

```cpp
void DoSomething(std::string& input){...}
```

Bir işlev başvuruya göre geçirilen bir bağımsız değişkeni değiştirdiğinde, yerel bir kopya değil, özgün nesneyi değiştirir. Bir işlevin böyle bir bağımsız değişkeni değiştirmesini engellemek için parametreyi const& olarak niteleyin:

```cpp
void DoSomething(const std::string& input){...}
```

**C++ 11:**  Rvalue başvurusu veya lvalue ile geçirilen bağımsız değişkenleri açıkça işlemek için, bir evrensel başvuruyu göstermek için parametresinde çift ve işareti kullanın:

```cpp
void DoSomething(const std::string&& input){...}
```

**`void`** **`void`** Bağımsız değişken bildirim listesinin ilk ve tek üyesi olduğu sürece, parametre bildirim listesindeki tek bir anahtar sözcükle belirtilen bir işlev bağımsız değişken almaz. **`void`** Listede başka bir yerde bulunan tür bağımsız değişkenleri hata üretir. Örnek:

```cpp

// OK same as GetTickCount()
long GetTickCount( void );
```

**`void`** Burada özetlenen bir bağımsız değişken belirtmek geçersiz olsa da, türden türetilmiş türler **`void`** (örneğin işaretçiler **`void`** ve diziler gibi **`void`** ) bağımsız değişken bildirim listesinin herhangi bir yerinde görünebilir.

### <a name="default-arguments"></a>Varsayılan Bağımsız Değişkenler

Bir işlev imzasında son parametreye veya parametrelere varsayılan bir bağımsız değişken atanabilir. Bu, çağıranın, başka bir değer belirtmek istemedikçe işlevi çağırırken bağımsız değişkeni bırakabileceği anlamına gelir.

```cpp
int DoSomething(int num,
    string str,
    Allocator& alloc = defaultAllocator)
{ ... }

// OK both parameters are at end
int DoSomethingElse(int num,
    string str = string{ "Working" },
    Allocator& alloc = defaultAllocator)
{ ... }

// C2548: 'DoMore': missing default parameter for parameter 2
int DoMore(int num = 5, // Not a trailing parameter!
    string str,
    Allocator& = defaultAllocator)
{...}
```

Daha fazla bilgi için bkz. [Varsayılan bağımsız değişkenler](../cpp/default-arguments.md).

## <a name="function-return-types"></a>İşlev dönüş türleri

Bir işlev, başka bir işlevi veya yerleşik bir diziyi döndüremeyebilir; Ancak, bu türlere işaretçiler veya bir işlev nesnesi üreten bir *lambda*döndürebilir. Bu durumlar dışında, bir işlev kapsamda olan herhangi bir türde bir değer döndürebilir veya değer döndürmez; bu durumda, dönüş türü olur **`void`** .

### <a name="trailing-return-types"></a>Sondaki dönüş türleri

"Sıradan" dönüş türü, işlev imzasının sol tarafında bulunur. *Sondaki dönüş türü* , imzanın en sağ tarafında bulunur ve öncesinde **`->`** işleçtir. Döndürülen değerin türü şablon parametrelerine bağlı olduğunda, sondaki dönüş türleri özellikle işlev şablonlarında yararlıdır.

```cpp
template<typename Lhs, typename Rhs>
auto Add(const Lhs& lhs, const Rhs& rhs) -> decltype(lhs + rhs)
{
    return lhs + rhs;
}
```

**`auto`** Bir sondaki dönüş türü ile birlikte kullanıldığında, yalnızca decltype ifadesinin ürettiği her şey için bir yer tutucu görevi görür ve kendisi tür kesintisi yapmaz.

## <a name="function-local-variables"></a>İşlev yerel değişkenleri

Bir işlev gövdesi içinde belirtilen bir değişken *yerel bir değişken* veya yalnızca *Yerel*olarak adlandırılır. Statik olmayan Yereller yalnızca işlev gövdesi içinde görünür ve yığında bildirilirse, işlev çıktığında kapsam dışına çıkar. Yerel bir değişken oluşturup değeri değere göre döndürdüğünüzde, derleyici, gereksiz kopyalama işlemlerini önlemek için *adlandırılmış dönüş değeri iyileştirmesini* genellikle gerçekleştirebilir. Başvuruya göre yerel bir değişken döndürürler, bu başvuruyu kullanan çağıran tarafından herhangi bir girişim yerel olarak yok edildikten sonra, derleyici bir uyarı verir.

C++ ' da yerel bir değişken statik olarak tanımlanmış olabilir. Değişken yalnızca işlev gövdesinin içinde görünür, ancak işlevin tüm örnekleri için değişkenin tek bir kopyası vardır. Yerel statik nesneler `atexit` tarafından belirtilen sonlandırma sırasında yok edilir. Programın denetim akışı bildirimi atlamasından dolayı statik nesne oluşturulmazsa, söz konusu nesneyi yok etmek için girişimde bulunulmaz.

## <a name="type-deduction-in-return-types-c14"></a><a name="type_deduction"></a>Dönüş türlerinde tür kesintisi (C++ 14)

C++ 14 ' te, **`auto`** derleyicinin dönüş türünü, bir sondaki dönüş türü sağlamak zorunda kalmadan işlev gövdesinden çıkarmasını söylemek için kullanabilirsiniz. **`auto`** Her zaman bir değere dönüşe kadar kesintiler olduğunu unutmayın. `auto&&`Derleyiciye bir başvuru başlatmalarını bildirmek için kullanın.

Bu örnekte, **`auto`** lhs ve rhs toplamının const olmayan bir değer kopyası olarak çıkarılır.

```cpp
template<typename Lhs, typename Rhs>
auto Add2(const Lhs& lhs, const Rhs& rhs)
{
    return lhs + rhs; //returns a non-const object by value
}
```

Bu, **`auto`** kesintiler olan türün sabitliğini korumadığını unutmayın. Dönüş değeri, bağımsız değişkenlerinin const durumunu veya başvurusunu korumak zorunda olan işlevleri iletmek için, **`decltype(auto)`** **`decltype`** tür çıkarımı kurallarını kullanan ve tüm tür bilgilerini koruyan anahtar sözcüğünü kullanabilirsiniz. **`decltype(auto)`** Sol tarafta normal bir dönüş değeri veya sondaki dönüş değeri olarak kullanılabilir.

Aşağıdaki örnek ( [N3493](https://wg21.link/n3493)' dan kod temel alınarak), **`decltype(auto)`** işlev bağımsız değişkenlerinin, şablon örneklenene kadar bilinmeyen bir dönüş türünde tam olarak iletilmesini sağlamak için kullanıldığını gösterir.

```cpp
template<typename F, typename Tuple = tuple<T...>, int... I>
decltype(auto) apply_(F&& f, Tuple&& args, index_sequence<I...>)
{
    return std::forward<F>(f)(std::get<I>(std::forward<Tuple>(args))...);
}

template<typename F, typename Tuple = tuple<T...>,
    typename Indices = make_index_sequence<tuple_size<Tuple>::value >>
   decltype( auto)
    apply(F&& f, Tuple&& args)
{
    return apply_(std::forward<F>(f), std::forward<Tuple>(args), Indices());
}
```

## <a name="returning-multiple-values-from-a-function"></a><a name="multi_val"></a>Bir işlevden birden çok değer döndürme

Bir işlevden birden fazla değer döndürmek için çeşitli yollar vardır:

1. Adlandırılmış bir sınıf veya yapı nesnesindeki değerleri kapsülle. Sınıf veya yapı tanımının arayan tarafından görünür olmasını gerektirir:

    ```cpp
    #include <string>
    #include <iostream>

    using namespace std;

    struct S
    {
        string name;
        int num;
    };

    S g()
    {
        string t{ "hello" };
        int u{ 42 };
        return { t, u };
    }

    int main()
    {
        S s = g();
        cout << s.name << " " << s.num << endl;
        return 0;
    }
    ```

1. Std:: Tuple veya std::p AIR nesnesi döndürür:

    ```cpp
    #include <tuple>
    #include <string>
    #include <iostream>

    using namespace std;

    tuple<int, string, double> f()
    {
        int i{ 108 };
        string s{ "Some text" };
        double d{ .01 };
        return { i,s,d };
    }

    int main()
    {
        auto t = f();
        cout << get<0>(t) << " " << get<1>(t) << " " << get<2>(t) << endl;

        // --or--

        int myval;
        string myname;
        double mydecimal;
        tie(myval, myname, mydecimal) = f();
        cout << myval << " " << myname << " " << mydecimal << endl;

        return 0;
    }
    ```

1. **Visual Studio 2017 sürüm 15,3 ve üzeri** (ile kullanılabilir [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) ): yapılandırılmış bağlamaları kullanın. Yapılandırılmış bağlamaların avantajı, dönüş değerlerini depolayan değişkenlerin, bildirildiği anda başlatıldığını, bazı durumlarda de önemli ölçüde daha verimli bir şekilde çalışmasını sağlar. `auto[x, y, z] = f();`Köşeli ayraçlar, tüm işlev bloğunun kapsamında olan adları tanıtın ve başlatır.

    ```cpp
    #include <tuple>
    #include <string>
    #include <iostream>

    using namespace std;

    tuple<int, string, double> f()
    {
        int i{ 108 };
        string s{ "Some text" };
        double d{ .01 };
        return { i,s,d };
    }
    struct S
    {
        string name;
        int num;
    };

    S g()
    {
        string t{ "hello" };
        int u{ 42 };
        return { t, u };
    }

    int main()
    {
        auto[x, y, z] = f(); // init from tuple
        cout << x << " " << y << " " << z << endl;

        auto[a, b] = g(); // init from POD struct
        cout << a << " " << b << endl;
        return 0;
    }
    ```

1. Dönüş değerinin kendisini kullanmanın yanı sıra, işlevin çağıranın sağladığı nesnelerin değerlerini değiştirebilmeleri veya başlatabilmesi için, başvuruya göre geçiş yapmak için herhangi bir sayıda parametre tanımlayarak "döndürebilirsiniz". Daha fazla bilgi için bkz. [başvuru türü Işlev bağımsız değişkenleri](reference-type-function-arguments.md).

## <a name="function-pointers"></a>İşlev işaretçileri

C++, işlev işaretçilerini C diliyle aynı şekilde destekler. Ancak, daha fazla tür açısından güvenli bir alternatif, genellikle bir işlev nesnesi kullanmaktır.

İşlev işaretçisi **`typedef`** türü döndüren bir işlev bildirirseniz, işlev işaretçisi türü için bir diğer ad bildirmek üzere kullanılması önerilir.  Örneğin:

```cpp
typedef int (*fp)(int);
fp myFunction(char* s); // function returning function pointer
```

Bu yapılmazsa, işlev bildirimi için doğru sözdizimi, tanımlayıcı (yukarıdaki örnekte `fp`) işlev adı ve bağımsız değişken listesiyle değiştirilerek aşağıdaki gibi işlev işaretçisine yönelik bildirimci sözdiziminden çıkarılır:

```cpp
int (*myFunction(char* s))(int);
```

Yukarıdaki bildirim, yukarıda kullanılan bildirime eşdeğerdir **`typedef`** .

## <a name="see-also"></a>Ayrıca bkz.

[İşlev aşırı yüklemesi](../cpp/function-overloading.md)<br/>
[Değişken bağımsız değişken listeleriyle işlevler](../cpp/functions-with-variable-argument-lists-cpp.md)<br/>
[Açık olarak varsayılan ve silinen Işlevler](../cpp/explicitly-defaulted-and-deleted-functions.md)<br/>
[Işlevlerde bağımsız değişkene bağlı ad (KOENIG) arama](../cpp/argument-dependent-name-koenig-lookup-on-functions.md)<br/>
[Varsayılan bağımsız değişkenler](../cpp/default-arguments.md)<br/>
[Satır içi Işlevler](../cpp/inline-functions-cpp.md)
