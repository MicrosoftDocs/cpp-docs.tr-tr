---
title: İşlevler [C++]
ms.date: 01/25/2018
helpviewer_keywords:
- defaults, arguments
- function definitions
- function definitions, about function definitions
- default arguments
- declarators, functions
ms.assetid: 33ba01d5-75b5-48d2-8eab-5483ac7d2274
ms.openlocfilehash: 777bffab922bc7122444110a32874f9b77171b0a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626154"
---
# <a name="functions-c"></a>İşlevler [C++]

Başka bir işlem gerçekleştiren bir kod bloğunu bir işlevdir. Bir işlev bağımsız değişkenleri işleve geçirilecek çağıranlar sağlayan giriş parametreleri isteğe bağlı olarak tanımlayabilirsiniz. Bir işlev, isteğe bağlı olarak çıkış olarak bir değer döndürebilir. İşlevler, ideal olarak işlevin ne yaptığını açıkça tanımlayan bir ad ile tek bir yeniden kullanılabilir blok ortak işlemlerinde kapsüllemek için yararlıdır. Aşağıdaki işlev çağıran gelen iki tamsayı kabul eder ve toplamları döndürür; *bir* ve *b* olan *parametreleri* türü **int**.

```cpp
int sum(int a, int b)
{
    return a + b;
}
```

İşlev çağrılabilir, veya *adlı*, program içinde herhangi bir dizi. İşleve geçirilen değerler *bağımsız değişkenleri*, eşleşen türleri işlev tanımında parametre türleri ile uyumlu olmalıdır.

```cpp
int main()
{
    int i = sum(10, 32);
    int j = sum(i, 66);
    cout << "The value of j is" << j << endl; // 108
}
```

İşlev uzunluğu için pratik bir sınır yoktur ancak tek iyi tanımlanmış bir görevi gerçekleştirmek için işlevleri iyi tasarım amaçlar. Karmaşık algoritmalar anlaşılması kolay daha basit işlevlere mümkün olduğunca bölünmesi.

Sınıf kapsamında tanımlanan işlevleri, üye işlevleri olarak adlandırılır. C++'da, diğer dillerden farklı olarak, bir işlev de (örtük genel ad alanı dahil) ad alanı kapsamında tanımlanabilir. Bu işlevlerin çağrılma biçimini *işlevleri ücretsiz* veya *üye olmayan işlevleri*; standart kitaplıkta yaygın olarak kullanılır.

İşlevler olabilir *aşırı*, numarası ve/veya biçimsel parametre türüne göre farklılık gösteriyorsa, bir işlevi farklı sürümlerini başka bir deyişle, aynı adı paylaşan. Daha fazla bilgi için [işlev aşırı yüklemesi](../cpp/function-overloading.md).

## <a name="parts-of-a-function-declaration"></a>Bir işlev bildirimi bölümleri

En az bir işlev *bildirimi* dönüş türü, işlev adı ve (boş olabilir) parametre listesi derleyici ek yönergeler sağlayan isteğe bağlı anahtar sözcük birlikte oluşur. Aşağıdaki örnek bir işlev bildirimi şu şekildedir:

```cpp
int sum(int a, int b);
```

Bildirimi, bir işlev tanımı oluşur artı *gövdesi*, kaşlı ayraçlar arasındaki tüm kodu verilmiştir:

```cpp
int sum(int a, int b)
{
    return a + b;
}
```

Noktalı virgül tarafından izlenen bir işlev bildirimi, bir program birden çok yerde görünebilir. Her bir çeviri birimindeki bu işleve yapılan tüm çağrılar önce yer almalıdır. İşlev tanımı, tek Tanım Kuralı (ODR) göre programda, yalnızca bir kez görünmelidir.

Bir işlev bildirimi gerekli bölümleri şunlardır:

1. İşlevinin döndürdüğü değerin türünü belirtir, dönüş türü veya **void** , hiçbir değer döndürülmez. C ++ 11, **otomatik** derleyiciye dönüş deyiminden türünün çıkarsanması için geçerli bir dönüş türü. C ++ 14'te, decltype(auto) da izin verilir. Daha fazla bilgi için aşağıdaki türlerde dönüş türü çıkarma bakın.

1. Bir harf veya alt çizgi ile başlamalı ve boşluk içeremez işlev adı. Genel olarak, özel üye işlevleri önde gelen altçizgilere standart kitaplığı işlev adlarını belirtin veya kodunuz tarafından için hedeflenmemiş üye olmayan işlevleri kullanın.

1. Parametre listesi, ayrılmış bir küme ayracı, virgülle ayrılmış bir dizi sıfır veya daha çok parametrenin türü ve isteğe bağlı olarak işlev gövdesi değerleri erişilebilecek yerel bir ad belirtin.

İsteğe bağlı bir işlev bildirimi bölümleri şunlardır:

1. `constexpr`, işlev dönüş değeri bir sabit değer olduğunu belirten, derleme zamanında hesaplanabilir.

    ```cpp
    constexpr float exp(float x, int n)
    {
        return n == 0 ? 1 :
            n % 2 == 0 ? exp(x * x, n / 2) :
            exp(x * x, (n - 1) / 2) * x;
    };
    ```

1. Kendi bağlama belirtimi **extern** veya **statik**.

    ```cpp
    //Declare printf with C linkage.
    extern "C" int printf( const char *fmt, ... );

    ```

   Daha fazla bilgi için [Program ve bağlantı](../cpp/program-and-linkage-cpp.md).

1. **Satır içi**, derleyiciye işlev yapılan her çağrı, işlev kodunu değiştirin bildirir. Satır içi kullanım can burada bir işlev hızlı bir şekilde yürütür ve performans açısından kritik bir kod bölümünde tekrarlanarak çağrılır senaryolarda performansı yardımcı olur.

    ```cpp
    inline double Account::GetBalance()
    {
        return balance;
    }
    ```

   Daha fazla bilgi için [satır içi işlevleri](../cpp/inline-functions-cpp.md).

1. A `noexcept` işlev bir özel durum olup olmadığını belirten bir ifade. Aşağıdaki örnekte, bir özel durum işlevi, oluşturmaz `is_pod` ifadeyi hesaplar için **true**.

    ```cpp
    #include <type_traits>

    template <typename T>
    T copy_object(T& obj) noexcept(std::is_pod<T>) {...}
    ```

   Daha fazla bilgi için [noexcept](../cpp/noexcept-cpp.md).

1. (Yalnızca üye işlevleri) Cv işlevi olup olmadığını belirten niteleyicileri, **const** veya **geçici**.

1. (Yalnızca üye işlevleri) **sanal**, `override`, veya `final`. **Sanal** bir işlev türetilen bir sınıfta geçersiz kılınabilir belirtir. `override` türetilen bir sınıfta bir işlev bir sanal işlevi geçersiz kılma anlamına gelir. `final` türetilmiş sınıf bir işlev, tüm daha fazla geçersiz kılınamaz anlamına gelir. Daha fazla bilgi için [sanal işlevler](../cpp/virtual-functions.md).

1. (yalnızca üye işlevleri) **statik** uygulanan üye işlevi işlev sınıfı herhangi bir nesne örnekleri ile ilişkili olmadığı anlamına gelir.

1. (Yalnızca statik olmayan üye işlevleri) Ref derleyiciye bir işlev seçin ait hangi aşırı yüklemenin belirten niteleyicisi, örtük nesne parametresi (\*bu) bir lvalue başvurusu ve rvalue başvurudur. Daha fazla bilgi için [işlev aşırı yüklemesi](function-overloading.md#ref-qualifiers).

Aşağıdaki şekil, bir işlev tanımının bölümlerini gösterir. Gölgeli alan işlev gövdesidir.

![Bir işlev tanımının bölümlerini](../cpp/media/vc38ru1.gif "vc38RU1") bir işlev tanımının bölümleri

## <a name="function-definitions"></a>İşlev tanımları

A *işlev tanımı* bildirimi ve değişken bildirimleri, ifadeler ve deyimler içeren küme ayraçları içine alınmış işlev gövdesindeki oluşur. Aşağıdaki örnek, bir tam işlev tanımı gösterilmektedir:

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

Gövde içinde bildirilen değişkenler, yerel değişkenler veya yerel öğelerin adı verilir. İşlev, kapsam dışına çıkmadan; Bu nedenle, bir işlev yerel başvuru hiçbir zaman döndürmesi gerekir!

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

Bir üye işlev olarak bildirebilirsiniz **const** işlevi sınıfındaki tüm veri üyelerinin değerlerini değiştirmek için izin verilmiyor belirtmek için. Bir üye işlev olarak bildirmek **const**, zorlamak için derleyici yardımcı *const doğruluğu*. Birisi yanlışlıkla olarak bildirilen bir işlevi kullanarak bir nesneyi değiştirmeye çalışırsa **const**, bir derleyici hatası oluşturulur. Daha fazla bilgi için [const](const-cpp.md).

Bir işlev olarak bildirmek `constexpr` olduğunda ürettiği değer muhtemelen belirlenebilir derleme zamanında. Constexpr işlevi genellikle normal işlevinden daha hızlı yürütür. Daha fazla bilgi için [constexpr](constexpr-cpp.md).

## <a name="function-templates"></a>İşlev Şablonları

Bir işlev şablonu için bir sınıf şablonunun benzer. Bu, şablon bağımsız değişkenlerine göre somut işlevleri oluşturur. Çoğu durumda, şablon türü bağımsız değişkenleri belirleyebilir ve bu nedenle açıkça belirtmek gerekli değildir.

```cpp
template<typename Lhs, typename Rhs>
auto Add2(const Lhs& lhs, const Rhs& rhs)
{
    return lhs + rhs;
}

auto a = Add2(3.13, 2.895); // a is a double
auto b = Add2(string{ "Hello" }, string{ " World" }); // b is a std::string
```

Daha fazla bilgi için [işlev şablonları](../cpp/function-templates.md)

## <a name="function-parameters-and-arguments"></a>İşlev parametreleri ve bağımsız değişkenler

Sıfır veya daha fazla türlerinin parametre virgülle ayrılmış listesi her biri tarafından işlev gövdesi içinde erişilebilen bir ada sahip bir işleve sahiptir. Bir işlev şablonu, tür veya değer ek parametreler belirtebilir. Çağıran parametre listesiyle eşleşen türleri uyumlu somut değerler bağımsız değişken geçirir.

Varsayılan olarak, bağımsız değişkenleri işleve geçirilen nesnesinin bir kopyasını alır. yani değere göre işleve geçirilir. Büyük nesneler için kopyalayarak pahalı olabilir ve her zaman gerekli değildir. Başvuruya göre (özellikle lvalue başvuru) geçirilecek bağımsız değişkenleri neden olmak için bir başvuru niceleyici parametre ekleyin:

```cpp
void DoSomething(std::string& input){...}
```

Bir işlevin başvuruya göre geçirilen bağımsız değişken değiştirdiğinde, orijinal nesnenin, yerel bir kopyasını değiştirir. Bir işlev, bu tür bir bağımsız değişken değiştirmesini önlemek için parametre olarak const uygun &:

```cpp
void DoSomething(const std::string& input){...}
```

**C++ 11:** rvalue başvurusu veya lvalue başvuru tarafından geçirilen bağımsız değişkenleri açıkça işlemek için evrensel bir başvuru belirtmek için parametresi bir çift ampersan kullanın:

```cpp
void DoSomething(const std::string&& input){...}
```

Tek anahtar sözcüğüyle bildirilen bir işlev **void** parametre bildiriminde listesi hiçbir bağımsız değişken anahtar sözcüğü uzun sürer **void** ilk ve tek bağımsız değişken bildirimi listesinin bir üyesi. Türünde bağımsız değişkenler **void** başka bir yerde listesinde hata üretir. Örneğin:

```cpp

// OK same as GetTickCount()
long GetTickCount( void );
```

Belirtmek geçersiz olsa Not bir **void** dışındaki bağımsız değişken özetlenen burada türünden türetilmiş türlerin **void** (işaretçileri gibi **void** ve dizileri**void**) herhangi bir bağımsız değişken bildirim listesi görüntülenir.

### <a name="default-arguments"></a>Varsayılan Bağımsız Değişkenler

Son parametresi veya bir işlev imzası parametrelere arayan bağımsız değişkeni başka bir değer belirtmek istemiyorsanız işlev çağrılırken bırakabilir anlamına gelir. bir varsayılan bağımsız değişken atanabilir.

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

Daha fazla bilgi için [varsayılan bağımsız değişkenler](../cpp/default-arguments.md).

## <a name="function-return-types"></a>İşlev dönüş türleri

Bir işlev, başka bir işlev veya yerleşik bir dizi döndürmeyebilir; Ancak, bu türleri için işaretçiler döndürebilir veya *lambda*, bir işlev nesnesi oluşturur. Bu durumlarda, bir işlev kapsamındaki herhangi bir türde bir değer döndürebilir veya herhangi bir değer döndürebilir dışında bu durumda dönüş türü olan **void**.

### <a name="trailing-return-types"></a>Dönüş türlerini takip etme

"Normal" bir dönüş türü işlev imzası sol tarafında bulunur. A *bitiş dönüş türüne* imza çoğu sağ tarafında bulunur ve öncesinde -> işleci. Sondaki dönüş türleri, dönüş değerinin türü, şablon parametrelerine bağlıysa işlev şablonlarında özellikle yararlı olur.

```cpp
template<typename Lhs, typename Rhs>
auto Add(const Lhs& lhs, const Rhs& rhs) -> decltype(lhs + rhs)
{
    return lhs + rhs;
}
```

Zaman **otomatik** kullanılan bitiş dönüş türü ile birlikte, yalnızca bir yer tutucu olarak hangi decltype ifade üretir için kullanılır ve kendisi türü çıkarma gerçekleştirir.

## <a name="function-local-variables"></a>İşlevi yerel değişkenler

Bir işlev gövdesinin içinde bildirilen bir değişken olarak adlandırılan bir *yerel değişken* veya yalnızca bir *yerel*. Statik olmayan yerel öğeler, yalnızca işlev gövdesi içinde görünür olduğundan ve yığında bildirilmemişse işlev kapsam dışına çıkmaz. Yerel bir değişken oluşturun ve değeri döndürür, derleyici genellikle gereksiz kopyalama işlemleri önlemek için dönüş değeri iyileştirme gerçekleştirebilirsiniz. Yerel bir değişken başvuru ile döndürülen, yerel edildikten sonra referans kullanmak üzere her türlü girişim çağıran tarafından oluşacaktır, derleyici bir uyarı verir.

C++'da yerel bir değişken statik olarak bildirilmelidir. Değişken yalnızca işlev gövdesi içinde görünür olur, ancak işlevin tüm örnekleri için değişkenin tek bir kopyası bulunmaktadır. Yerel statik nesneler `atexit` tarafından belirtilen sonlandırma sırasında yok edilir. Programın denetim akışı bildirimi atlamasından dolayı statik nesne oluşturulmazsa, söz konusu nesneyi yok etmek için girişimde bulunulmaz.

##  <a name="type_deduction"></a> Çıkarım dönüş türleri (C ++ 14) yazın.

C ++ 14'te, kullandığınız **otomatik** sondaki dönüş türünü sağlamak zorunda kalmamanız işlev gövdesi dönüş türünden çıkarsanacak derleyicisinin. Unutmayın **otomatik** her zaman bir dönüş değere göre için çıkarır. Kullanım `auto&&` derleyicinin başvuru için.

Bu örnekte, **otomatik** lhs ve sol toplamı sabit olmayan değer kopya olarak deyimli.

```cpp
template<typename Lhs, typename Rhs>
auto Add2(const Lhs& lhs, const Rhs& rhs)
{
    return lhs + rhs; //returns a non-const object by value
}
```

Unutmayın **otomatik** çıkarır, türü değişkenlerinin sabitliğine korumaz. Kullanabileceğiniz işlevler dönüş değeri gerekiyor const-ness veya bağımsız değişkenlerinin ref durumunu korumak için iletmek için **decltype(auto)** kullanan anahtar sözcüğü **decltype** çıkarım kuralları yazın ve Tüm tür bilgilerini korur. **decltype(Auto)** sol tarafındaki sıradan bir dönüş değeri olarak veya sondaki dönüş değeri olarak kullanılabilir.

Aşağıdaki örnek (koddan göre [N3493](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2013/n3493.html)), gösterir **decltype(auto)** şablon kadar bilinen değil bir dönüş türü işlev bağımsız değişkenleri kusursuz iletme etkinleştirmek için kullanılan örneği.

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
}
```

## <a name="multi_val"></a> Bir işlevden birden çok değer döndürüyor

Bir işlevden birden fazla değer döndürmek için çeşitli yollar vardır:

1. Adlandırılmış bir class veya struct nesne değerleri kapsüller. Sınıf veya yapı tanımına çağırana görünür olmasını gerektirir:

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

1. Bir std::tuple veya std::pair nesnesi döndürür:

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

1. **Visual Studio 2017 sürüm 15.3 ve üzeri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): yapılandırılmış bağlamalar kullanın. Yapılandırılmış bağlamalar avantajı, bazı durumlarda önemli ölçüde daha verimli olabilir dönüş değerlerini depolayan değişkenleri bildirildikleri, aynı anda başlatılır ' dir. Bu bildirimde--`auto[x, y, z] = f();`--köşeli ayraçlar tanıtır ve tüm işlev bloğu için kapsamda olan adlar Başlat.

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

1. Dönüş değeri kullanmanın yanı sıra, "değerleri herhangi bir sayıda başvuru ile geçişi işlevi değiştirebilir veya çağıranın sağlayan nesneleri değerlerini başlatmak için kullanmak üzere parametreleri tanımlayarak dönebilirsiniz". Daha fazla bilgi için [başvuru türü işlev bağımsız değişkenleri](reference-type-function-arguments.md).

## <a name="function-pointers"></a>İşlev işaretçileri

C++, C dili olarak aynı şekilde işlev işaretçilerine destekler. Ancak daha fazla tür kullanımı uyumlu bir alternatif genellikle bir işlev nesnesi kullanmaktır.

Önerilir **typedef** bir işlev işaretçisi türü döndüren bir işlev bildiriliyorsa, işlev işaretçisi türü için bir diğer ad bildirmek için kullanılır.  Örneğin

```cpp
typedef int (*fp)(int);
fp myFunction(char* s); // function returning function pointer
```

Bu yapılmazsa, işlev bildirimi için doğru sözdizimi, tanımlayıcı (yukarıdaki örnekte `fp`) işlev adı ve bağımsız değişken listesiyle değiştirilerek aşağıdaki gibi işlev işaretçisine yönelik bildirimci sözdiziminden çıkarılır:

```cpp
int (*myFunction(char* s))(int);
```

Yukarıdaki bildirim, yukarıdaki örneği kullanan bildirime eşdeğerdir.

## <a name="see-also"></a>Ayrıca bkz.

[İşlev Aşırı Yüklemesi](../cpp/function-overloading.md)<br/>
[Değişken Bağımsız Değişken Listeleriyle İşlevler](../cpp/functions-with-variable-argument-lists-cpp.md)<br/>
[Açıkça Varsayılan Haline Getirilen ve Silinen İşlevler](../cpp/explicitly-defaulted-and-deleted-functions.md)<br/>
[İşlevlerde Bağımsız Değişkene Bağlı Ad (Koenig) Arama](../cpp/argument-dependent-name-koenig-lookup-on-functions.md)<br/>
[Varsayılan Bağımsız Değişkenler](../cpp/default-arguments.md)<br/>
[Satır İçi İşlevler](../cpp/inline-functions-cpp.md)
