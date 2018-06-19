---
title: İşlevler (C++) | Microsoft Docs
ms.custom: ''
ms.date: 01/25/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- defaults, arguments
- function definitions
- function definitions, about function definitions
- default arguments
- declarators, functions
ms.assetid: 33ba01d5-75b5-48d2-8eab-5483ac7d2274
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 720147992540b53c51e731db361cd9946a7a5313
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418422"
---
# <a name="functions-c"></a>İşlevler [C++]

Başka bir işlem gerçekleştirir kod bloğu bir işlevdir. Bir işlev tabloya işlev bağımsız değişkenleri geçirmek arayanlar etkinleştirmek giriş parametreleri isteğe bağlı olarak tanımlayabilirsiniz. Bir işlev isteğe bağlı olarak bir değer çıktısı olarak döndürür. İşlevler, ideal olarak açıkça işlevi yaptığı açıklayan bir ad ile tek bir yeniden kullanılabilir blok ortak işlemlerinde kapsüllemek için kullanışlıdır. Aşağıdaki işlevi çağıran gelen iki tamsayı kabul eder ve bunların toplamı döndürür; `a` ve `b` olan *parametreleri* türü **int**.

```cpp
int sum(int a, int b)
{
    return a + b;
}
```

İşlev çağrılan veya *adlı*, herhangi bir sayıda program yerlerde gelen. İşleve değerler *bağımsız değişkenleri*, olan türleri işlevi tanımında parametre türleri ile uyumlu olmalıdır.

```cpp
int main()
{
    int i = sum(10, 32);
    int j = sum(i, 66);
    cout << "The value of j is" << j << endl; // 108
}
```

İşlev uzunluğa pratik bir sınır yoktur ancak tek iyi tanımlanmış bir görev gerçekleştirmeniz işlevleri için iyi tasarım amaçlar. Karmaşık algoritmalar kolay anlamak daha basit işlevlerini mümkün olduğunca parçalanmış.

Sınıf kapsamda tanımlanan işlevler üye işlevleri çağrılır. C++'da, diğer diller, bir işlev de (örtük genel ad alanı dahil) ad alanı kapsamda tanımlanabilir. Bu tür işlevler adlı *serbest işlevleri* veya *olmayan üye işlevleri*; standart kitaplığında yaygın olarak kullanılır.

İşlevler olabilir *aşırı*, sayı ve/veya biçimsel parametresi türü farklıysa, bir işlev farklı sürümlerini başka bir deyişle, aynı adı paylaşan. Daha fazla bilgi için bkz: [işlev aşırı yüklemesi](../cpp/function-overloading.md).

## <a name="parts-of-a-function-declaration"></a>Bir işlev bildirimi bölümleri

En az bir işlev *bildirimi* dönüş türü, işlev adı ve (boş olabilir) parametre listesini derleyici ek yönergeler sağlayan isteğe bağlı anahtar sözcükleri birlikte oluşur. Aşağıdaki örnek, bir işlev bildirimi verilmiştir:

```cpp
int sum(int a, int b);
```

Bir bildirimi, bir işlev tanımı oluşur artı *gövde*, tüm kod süslü ayraçlar arasında olduğu:

```cpp
int sum(int a, int b)
{
    return a + b;
}
```

Noktalı virgülle ayrılır ve ardından bir işlev bildirimi, bir program birden çok yerde görünebilir. Bu işlev her çeviri biriminde yapılan her çağrı önce yer almalıdır. İşlev tanımı bir tanım kuralı (ODR) göre programın, yalnızca bir kez görünmesi gerekir.

Bir işlev bildirimi gerekli bölümleri şunlardır:

1. İşlevi döndürür değerin türünü belirtir, dönüş türü veya **void** hiçbir değer döndürülür. C ++ 11, **otomatik** return deyiminin türünden Infer derleyiciye geçerli bir dönüş türü. C ++ 14'te, decltype(auto) de izin verilir. Daha fazla bilgi için aşağıdaki türlerde dönüş türü kesintisi bakın.

1. Bir harf veya alt çizgi ile başlamalı ve boşluk içermemelidir işlev adı. Genel olarak, özel üye işlevleri başında alt çizgi standart kitaplığı işlevi adlarını göstermek veya kodunuz tarafından için tasarlanmamıştır olmayan üye işlevleri kullanın.

1. Parametre listesi ayraç sınırlandırılmış, virgülle ayrılmış kümesi sıfır veya daha çok parametrenin türü ve isteğe bağlı olarak işlev gövdesi içinde değerleri erişilebileceği yerel bir ad belirtin.

İsteğe bağlı bir işlev bildirimi bölümleri şunlardır:

1. **constexpr**, işlevin dönüş değeri sabit bir değer olduğunu belirten derleme zamanında hesaplanabilir.

    ```cpp
    constexpr float exp(float x, int n)
    {
        return n == 0 ? 1 :
            n % 2 == 0 ? exp(x * x, n / 2) :
            exp(x * x, (n - 1) / 2) * x;
    };
    ```

1. Bağlantı belirtimindekini **extern** veya **statik**.

    ```cpp
    //Declare printf with C linkage.
    extern "C" int printf( const char *fmt, ... );

    ```

     Daha fazla bilgi için bkz: [Program ve bağlantı](../cpp/program-and-linkage-cpp.md).

1. **Satır içi**, işlevi her çağrısı işlev kodu değiştirmek için derleyici talimatı verir. Satır içi kullanım can Yardım burada bir işlev hızlı bir şekilde yürütür ve performans açısından kritik kod bölümünde art arda çağrılır senaryolarda performansı.

    ```cpp
    inline double Account::GetBalance()
    {
        return balance;
    }
    ```

     Daha fazla bilgi için bkz: [satır içi işlevler](../cpp/inline-functions-cpp.md).

1. A **noexcept** ifadesi işlevi bir özel durum olup olmadığını belirtir. Aşağıdaki örnekte, bir özel durum işlevi varsa oluşturmadığını `is_pod` ifadeyi hesaplar için **doğru**.

    ```cpp
    #include <type_traits>

    template <typename T>
    T copy_object(T& obj) noexcept(std::is_pod<T>) {...}
    ```

     Daha fazla bilgi için bkz: [noexcept](../cpp/noexcept-cpp.md).

1. (Yalnızca üye işlevleri) MS-işlevi olup olmadığını belirten niteleyicileri **const** veya **volatile**.

1. (Yalnızca üye işlevleri) **sanal**, **geçersiz kılma**, veya **son**. **Sanal** türetilen bir sınıfta bir işlevi geçersiz kılınabilir belirtir. **geçersiz kılma** türetilmiş bir sınıf işlevinde sanal işlevi geçersiz kılma anlamına gelir. **Son** türetilmiş sınıf bir işlevi geçersiz kılınamaz birinde daha fazla anlamına gelir. Daha fazla bilgi için bkz: [sanal işlevler](../cpp/virtual-functions.md).

1. (yalnızca üye işlevleri) **statik** uygulanan bir üyesine işlevi işlevi tüm nesne sınıfı örnekleriyle ilişkili olmadığı anlamına gelir.

1. (Yalnızca statik olmayan üye işlevleri) Ref-ne zaman seçmek için bir işlev ait hangi aşırı yüklemenin derleyiciye belirten Niteleyici, örtük nesne parametresi (\*bu) rvalue başvuru lvalue başvuru karşılaştırması. Daha fazla bilgi için bkz: [işlev aşırı yüklemesi](function-overloading.md#ref-qualifiers).

Aşağıdaki şekilde bir işlev tanımı parçaları gösterilmektedir. İşlev gövdesi gölgeli bir alandır.

 ![Bir işlev tanımı bölümlerini](../cpp/media/vc38ru1.gif "vc38RU1") işlev tanımı bölümleri

## <a name="function-definitions"></a>İşlev tanımları

A *işlev tanımı* bildirimi ve değişken bildirimleri, ifadeler ve ifadeleri içeren süslü ayraçlar işlev gövdesi, oluşur. Aşağıdaki örnek, bir tam işlev tanımını gösterir:

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

Gövdesi içinde bildirilen değişkenlerin yerel değişkenler veya Yereller denir. İşlev çıktığında bunlar kapsam dışındadır; adresine gidin Bu nedenle, bir işlev hiç yerel bir başvuru döndürmelidir!

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

Üye işlev olarak bildirebilir **const** işlevi herhangi bir veri üyesi sınıfında değerlerini değiştirmek için izin verilmiyor belirtmek için. Üye işlev olarak bildirme tarafından **const**, derleyicinin zorlamak için Yardım *const doğruluk*. Birisi yanlışlıkla olarak bildirilen bir işlev kullanarak nesneyi değiştirmeye çalışırsa **const**, derleyici hatası tetiklenir. Daha fazla bilgi için bkz: [const](const-cpp.md).

Bir işlevi olarak bildirme **constexpr** ne zaman bu üretir değer büyük olasılıkla belirlenebilir derleme zamanında. Constexpr işlevi genellikle normal işlevi daha hızlı yürütür. Daha fazla bilgi için bkz: [constexpr](constexpr-cpp.md).

## <a name="function-templates"></a>İşlev Şablonları

Sınıf şablonu için benzer bir işlevi şablonudur; Şablon bağımsız değişkenler üzerinde temel somut işlevleri oluşturur. Çoğu durumda, şablonun tür bağımsız değişkenleri belirleyebilir ve bu nedenle bunları açıkça belirtmek gerekli değildir.

```cpp
template<typename Lhs, typename Rhs>
auto Add2(const Lhs& lhs, const Rhs& rhs)
{
    return lhs + rhs;
}

auto a = Add2(3.13, 2.895); // a is a double
auto b = Add2(string{ "Hello" }, string{ " World" }); // b is a std::string
```

Daha fazla bilgi için bkz: [işlev şablonları](../cpp/function-templates.md)

## <a name="function-parameters-and-arguments"></a>İşlev parametreleri ve bağımsız değişkenler

Her biri tarafından bu işlev gövdesi içinde erişilebilen bir ada sahip bir virgülle ayrılmış parametre sıfır veya daha fazla türlerinin listesi, bir işleve sahiptir. İşlev şablonu ek türü veya değeri parametreler belirtebilir. Çağıran, türleri parametre listesi ile uyumlu olan somut değerler bağımsız değişkenleri geçirir.

Varsayılan olarak, bağımsız değişkenler işlevine geçirilen nesne kopyasını işlevi alan anlamına gelir değeriyle geçirilir. Büyük nesneler için bir kopya yapmak pahalı olabilir ve her zaman gerekli değildir. Başvuru (özellikle lvalue başvuru) tarafından geçirilecek bağımsız değişkenler neden parametresi için bir başvuru niceleyici ekleyin:

```cpp
void DoSomething(std::string& input){...}
```

Bir işlev başvurusu tarafından geçirilen bağımsız değişken değiştirdiğinde, özgün nesne, yerel bir kopya değiştirir. Bir işlev böyle bir bağımsız değişken değiştirmesini önlemek için parametre olarak const nitelemek &:

```cpp
void DoSomething(const std::string& input){...}
```

 **C++ 11:** açıkça rvalue başvuru veya lvalue başvuru tarafından geçirilen bağımsız değişken işlemek için evrensel bir başvuru göstermek için parametresinde bir çift ve işareti kullanır:

```cpp
void DoSomething(const std::string&& input){...}
```

Bir işlev bildirilen tek anahtar sözcüğüyle **void** parametresi bildiriminde listesi bağımsız değişken, as anahtar sözcüğü uzunluğunda almayan **void** ilk ve yalnızca bağımsız değişken bildirimi listesi üyesi. Tür bağımsız değişkenleri **void** başka bir yerde hataları listede üretir. Örneğin:

```cpp

// OK same as GetTickCount()
long GetTickCount( void );
```

Belirtmek için geçersiz ederken Not bir **void** dışında bağımsız değişken Anahatlı olarak burada türetilmiş tür türünden **void** (işaretçileri gibi **void** ve dizileri**void**) her yerden bağımsız değişken bildirimi listesi görüntülenir.

### <a name="default-arguments"></a>Varsayılan Bağımsız Değişkenler

Son parametre veya işlev imzası parametrelerinde çağıran başka bir değer belirtmek istemiyorsanız işlevi çağrılırken bağımsız değişkeni bırakabilir anlamına gelir bir varsayılan bağımsız atanabilir.

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

Daha fazla bilgi için bkz: [varsayılan bağımsız değişkenler](../cpp/default-arguments.md).

## <a name="function-return-types"></a>İşlev dönüş türleri

Bir işlevin başka bir işlevi veya yerleşik bir dizi döndürmeyebilir; Ancak, bu tür için işaretçileri döndürebilir ya da bir *lambda*, bir işlev nesnesi oluşturur. Bu durumlarda, bir işlev kapsamında olan herhangi bir türde bir değer döndürebilir ya da herhangi bir değer döndürebilir dışında bu durumda dönüş türü olan **void**.

### <a name="trailing-return-types"></a>Sondaki dönüş türleri

"Normal" bir dönüş türü, işlev imzası sol tarafta bulunur. A *dönüş türü sondaki* imza çoğu sağ tarafında bulunur ve öncesinde -> işleci. Döndürülen değerin türü şablonu parametrelere bağlı olduğunda sonunda dönüş türleri işlevi şablonlarında özellikle yararlıdır.

```cpp
template<typename Lhs, typename Rhs>
auto Add(const Lhs& lhs, const Rhs& rhs) -> decltype(lhs + rhs)
{
    return lhs + rhs;
}
```

Zaman **otomatik** kullanılan sonunda bir dönüş türü ile birlikte, yalnızca bir yer tutucu olarak ne olursa olsun decltype ifade üreten için sunduğu ve kendisi türü kesintisi yapmaz.


## <a name="function-local-variables"></a>Yerel değişkenler işlevi

İşlev gövdesi içinde bildirilen bir değişken adı verilen bir *yerel değişken* veya sadece bir *yerel*. Statik olmayan Yereller yalnızca işlev gövdesi içinde görünür ve yığında bildirilir varsa işlevi çıktığında kapsamının dışına gidin. Yerel bir değişken oluşturun ve değeri tarafından iade ettiğinde derleyici genellikle gereksiz kopyalama işlemleri önlemek için dönüş değeri iyileştirme gerçekleştirebilirsiniz. Başvuruya göre yerel bir değişken döndürürse, bu başvuruyu kullanmak için arayan her türlü girişim yerel yok sonra nedeni derleyici bir uyarı verecek.

C++'da yerel bir değişken static olarak bildirilebilir. İşlev gövdesi içinde değişkeni görülebilir ancak değişkeni tek bir kopyasını işlevi tüm örnekler için yok. Yerel statik nesneleri tarafından belirtilen sonlandırma sırasında yok **atexit**. Programın denetim akışı bildirimi atlamasından dolayı statik nesne oluşturulmazsa, söz konusu nesneyi yok etmek için girişimde bulunulmaz.

##  <a name="type_deduction"></a> Dönüş türleri (C ++ 14) kesintisi yazın

C ++ 14'te, kullandığınız **otomatik** sonunda bir dönüş türü sağlamasına gerek kalmadan işlev gövdesi dönüş türünden gerçekleştirip görevlendirin için. Unutmayın **otomatik** her zaman bir return-tarafından-değerine deduces. Kullanım **otomatik & &** başvuru türetme görevlendirin için.

Bu örnekte, **otomatik** lhs ve rhs toplamı const olmayan değer kopya olarak anlaşılan.

```cpp
template<typename Lhs, typename Rhs>
auto Add2(const Lhs& lhs, const Rhs& rhs)
{
    return lhs + rhs; //returns a non-const object by value
}
```

Unutmayın **otomatik** , deduces türü const şahit korumaz. Dönüş değeri gerekiyor const şahit ya da kendi bağımsız değişkenleri ref şahit korumak için işlevleri iletmek için kullandığınız **decltype(auto)** kullanan anahtar sözcüğü **decltype** çıkarım kuralları yazın ve Tüm türü bilgileri korur. **decltype(Auto)** sol tarafındaki sıradan bir dönüş değeri olarak ya da sonunda dönüş değeri olarak kullanılabilir.

Aşağıdaki örnekte (koddan göre [N3493](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2013/n3493.html)), gösterir **decltype(auto)** şablon kadar bilinen olmayan bir dönüş türü işlev bağımsız değişkenleri kusursuz iletme etkinleştirmek için kullanılan örneği.

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

## <a name="returning-multiple-values-from-a-function"></a>Bir işlevden birden çok değer döndürüyor

Bir işlevden birden fazla değer döndürmek için çeşitli yolları vardır:

1. Adlandırılmış bir sınıf veya yapı nesnesindeki değerlerin kapsüller. Sınıfta veya yapı tanımı çağırana görünür olmasını gerektirir:

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

1. **Visual Studio 2017 15.3 ve sonraki sürümleri** (bulunan [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): yapılandırılmış bağlamaları kullanın. Yapılandırılmış bağlamaları avantajı, bazı durumlarda önemli ölçüde daha etkili olabilir dönüş değerlerini depolamak değişkenler bildirilir, aynı anda başlatılır ' dir. Bu bildirimde--`auto[x, y, z] = f();`--köşeli ayraçlar getirir ve tüm işlevi blok kapsamında adları başlayamadı.

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
    
1. Dönüş değerini kullanarak ek olarak, "değerlerini pass-by-reference kullanabilir, böylece işlevi değiştirmek veya çağıranın sağlar nesneleri değerlerini başlatma parametreleri herhangi bir sayıda tanımlayarak dönebilirsiniz". Daha fazla bilgi için bkz: [başvuru türü işlev bağımsız değişkenleri](reference-type-function-arguments.md).

## <a name="function-pointers"></a>İşlev işaretçileri

C++, C dil aynı şekilde işlev işaretçileri destekler. Ancak daha fazla tür kullanımı uyumlu alternatifi genellikle bir işlev nesnesi kullanmaktır.

Önerilir **typedef** işlev işaretçisi türü için bir diğer ad işlev işaretçisi türü döndüren bir işlev bildirme olmadığını bildirmek için kullanılır.  Örneğin

```cpp
typedef int (*fp)(int);
fp myFunction(char* s); // function returning function pointer
```

Bu yapılmazsa, işlev bildirimi için doğru sözdizimi, tanımlayıcı (yukarıdaki örnekte `fp`) işlev adı ve bağımsız değişken listesiyle değiştirilerek aşağıdaki gibi işlev işaretçisine yönelik bildirimci sözdiziminden çıkarılır:

```cpp
int (*myFunction(char* s))(int);
```

Yukarıdaki bildirim, yukarıdaki örneği kullanan bildirime eşdeğerdir.

## <a name="see-also"></a>Ayrıca Bkz.

- [İşlev Aşırı Yüklemesi](../cpp/function-overloading.md)
- [Değişken Bağımsız Değişken Listeleriyle İşlevler](../cpp/functions-with-variable-argument-lists-cpp.md)
- [Açıkça Varsayılan Haline Getirilen ve Silinen İşlevler](../cpp/explicitly-defaulted-and-deleted-functions.md)
- [İşlevlerde Bağımsız Değişkene Bağlı Ad (Koenig) Arama](../cpp/argument-dependent-name-koenig-lookup-on-functions.md)
- [Varsayılan Bağımsız Değişkenler](../cpp/default-arguments.md)
- [Satır İçi İşlevler](../cpp/inline-functions-cpp.md)
