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
ms.openlocfilehash: 1425ddebffc150158e88e44b1d2c22e3f85e5a31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375731"
---
# <a name="functions-c"></a>İşlevler [C++]

İşlev, bazı işlemleri gerçekleştiren bir kod bloğudur. Bir işlev isteğe bağlı olarak, arayanların bağımsız değişkenleri işleve geçirmesini sağlayan giriş parametrelerini tanımlayabilir. Bir işlev isteğe bağlı olarak çıktı olarak bir değer döndürebilir. İşlevler, ideal olarak işlevin ne yaptığını açıkça açıklayan bir adla, ortak işlemleri tek bir yeniden kullanılabilir blokta kapsüllemek için yararlıdır. Aşağıdaki işlev, arayandan iki tamsayı kabul eder ve toplamlarını döndürür; *a* ve *b* türü **int** *parametreleridir.*

```cpp
int sum(int a, int b)
{
    return a + b;
}
```

İşlev, programdaki herhangi bir sayıdan çağrılabilir veya *çağrılabilir.* İşleve geçirilen değerler, işlev tanımındaki parametre türleri ile uyumlu olması gereken *bağımsız değişkenlerdir.*

```cpp
int main()
{
    int i = sum(10, 32);
    int j = sum(i, 66);
    cout << "The value of j is" << j << endl; // 108
}
```

İşlev uzunluğu için pratik bir sınır yoktur, ancak iyi tasarım, iyi tanımlanmış tek bir görevi gerçekleştiren işlevleri hedefler. Karmaşık algoritmalar mümkün olduğunda anlaşılması kolay basit işlevlere bölünmelidir.

Sınıf kapsamında tanımlanan işlevlere üye işlevler denir. C++'da, diğer dillerin aksine, ad alanı kapsamında (örtük genel ad alanı dahil) bir işlev de tanımlanabilir. Bu tür işlevler *serbest işlevler* veya *üye olmayan işlevler*olarak adlandırılır; Standart Kitaplık'ta yaygın olarak kullanılırlar.

İşlevler *aşırı yüklenmiş*olabilir, bu da bir işlevin farklı sürümlerinin resmi parametrelerin sayısına ve/veya türüne göre farklılık gösterirse aynı adı paylaşabileceği anlamına gelir. Daha fazla bilgi için [bkz.](../cpp/function-overloading.md)

## <a name="parts-of-a-function-declaration"></a>İşlev bildiriminin bölümleri

En az işlev *bildirimi,* derleyiciye ek yönergeler sağlayan isteğe bağlı anahtar kelimelerle birlikte iade türü, işlev adı ve parametre listesinden (boş olabilir) oluşur. Aşağıdaki örnek bir işlev bildirimidir:

```cpp
int sum(int a, int b);
```

Bir işlev tanımı bir bildirim, artı *gövde*, kıvırcık parantez arasındaki tüm kod oluşur:

```cpp
int sum(int a, int b)
{
    return a + b;
}
```

Bir yarı kolon tarafından izlenen bir işlev bildirimi, bir programda birden çok yerde görünebilir. Her çeviri biriminde bu işleve yapılan tüm çağrılardan önce görünmelidir. İşlev tanımı, Tek Tanım Kuralı'na (ODR) göre programda yalnızca bir kez görünmelidir.

İşlev bildiriminin gerekli bölümleri şunlardır:

1. İşlevin döndürdettiği değer türünü belirten veya değer döndürülmezse **geçersiz kılınan** iade türü. C++11'de **otomatik,** derleyiciye dönüş deyiminden türü çıkarmasını söyleyen geçerli bir iade türüdür. C++14'te decltype(auto) da izin verilir. Daha fazla bilgi için aşağıdaki İade Türlerinde Tür Kesintisi'ne bakın.

1. Bir harfle veya alt la başlamalıdır ve boşluk içeremez işlev adı. Genel olarak, Standart Kitaplık işlev adlarının önde gelen alt alt alt ları, kodunuz tarafından kullanılmak üzere tasarlanmayan özel üye işlevleri veya üye olmayan işlevleri gösterir.

1. Parametre listesi, bir ayraç sınırlı, virgülle ayrılmış sıfır veya daha fazla parametre türü ve isteğe bağlı olarak değerleri işlev gövdesi içinde erişilebilen yerel bir ad belirterek kümesi.

İşlev bildiriminin isteğe bağlı bölümleri şunlardır:

1. `constexpr`, işlevin geri dönüş değerinin sabit bir değer olduğunu gösteren derleme zamanda hesaplanabilir.

    ```cpp
    constexpr float exp(float x, int n)
    {
        return n == 0 ? 1 :
            n % 2 == 0 ? exp(x * x, n / 2) :
            exp(x * x, (n - 1) / 2) * x;
    };
    ```

1. Bağlantı belirtimi, **extern** veya **statik.**

    ```cpp
    //Declare printf with C linkage.
    extern "C" int printf( const char *fmt, ... );

    ```

   Daha fazla bilgi için [Çeviri birimleri ve bağlantı](../cpp/program-and-linkage-cpp.md)bilgilerine bakın.

1. **inline**, derleyiciye işlev koduyla her çağrıyı değiştirmesini emreder. inlining, bir işlevin hızlı bir şekilde yürütüldüğü ve kodun performans açısından kritik bir bölümünde tekrar tekrar çağrıldığı senaryolarda performansa yardımcı olabilir.

    ```cpp
    inline double Account::GetBalance()
    {
        return balance;
    }
    ```

   Daha fazla bilgi için [Satır İçi Fonksiyonlar'a](../cpp/inline-functions-cpp.md)bakın.

1. İşlevin bir özel durum atıp atamayacağını belirten bir `noexcept` ifade. Aşağıdaki örnekte, `is_pod` ifade **doğru**değerlendirirse işlev bir özel durum atmaz.

    ```cpp
    #include <type_traits>

    template <typename T>
    T copy_object(T& obj) noexcept(std::is_pod<T>) {...}
    ```

   Daha fazla bilgi için [noexcept'a](../cpp/noexcept-cpp.md)bakın.

1. (Yalnızca Üye işlevler) **İşlevin const** veya **uçucu**olup olmadığını belirten cv-qualifiers.

1. (Yalnızca Üye işlevler) **sanal** `override`, `final`veya . **sanal,** bir işlevin türetilmiş bir sınıfta geçersiz kılınabileceğini belirtir. `override`türetilmiş bir sınıftaki bir işlevin sanal bir işlevi geçersiz kılarak geçersiz kılındığı anlamına gelir. `final`bir işlevin başka bir türetilmiş sınıfta geçersiz kılınamayacağı anlamına gelir. Daha fazla bilgi için [Sanal İşlevler'e](../cpp/virtual-functions.md)bakın.

1. (yalnızca üye işlevler) bir üye işleve uygulanan **statik,** işlevin sınıfın herhangi bir nesne örnekleriyle ilişkili olmadığı anlamına gelir.

1. (Yalnızca statik olmayan üye işlevler) Ref-qualifier, hangi örtülü nesne parametresi (bu)\*bir lvalue referans karşı bir rvalue referans olduğunda seçmek için bir işlevin aşırı yüklenir derleyici için belirtir. Daha fazla bilgi için [bkz.](function-overloading.md#ref-qualifiers)

Aşağıdaki şekil, işlev tanımının bölümlerini gösterir. Gölgeli alan işlev gövdesidir.

![İşlev tanımının bölümleri](../cpp/media/vc38ru1.gif "İşlev tanımının bölümleri") <br/>
İşlev tanımının bölümleri

## <a name="function-definitions"></a>Fonksiyon tanımları

*İşlev tanımı,* değişken bildirimleri, deyimleri ve ifadeleri içeren kıvırcık ayraçlarla kaplanan bildirim ve işlev gövdesinden oluşur. Aşağıdaki örnekte tam bir işlev tanımı gösterilmektedir:

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

Vücut içinde bildirilen değişkenlere yerel değişkenler veya yerel değişkenler denir. İşlev çıktığında kapsam dışına çıkarlar; bu nedenle, bir işlev yerel bir referans dönmek asla!

```cpp
    MyClass& boom(int i, std::string s)
    {
       int value {i};
       MyClass mc;
       mc.Initialize(i,s);
       return mc;
    }
```

## <a name="const-and-constexpr-functions"></a>const ve constexpr fonksiyonları

Bir üye işlevi, işlevin sınıftaki herhangi bir veri üyesinin değerlerini değiştirmesine izin verilmediğini belirtmek için **const** olarak bildirebilirsiniz. Bir üye **işlevi const**olarak beyan ederek, derleyicinin *const-correctness'i*uygulamasına yardımcı olursunuz. Birisi yanlışlıkla **const**olarak bildirilen bir işlev kullanarak nesneyi değiştirmeye çalışırsa, derleyici hatası yükseltilir. Daha fazla bilgi için [bkz.](const-cpp.md)

Bir işlevi, `constexpr` ürettiği değerin derleme zamanında belirlenebileceği zaman olarak bildirin. Bir constexpr işlevi genellikle normal bir işlevden daha hızlı yürütür. Daha fazla bilgi için [constexpr](constexpr-cpp.md)bakın.

## <a name="function-templates"></a>İşlev Şablonları

İşlev şablonu sınıf şablonuna benzer; şablon bağımsız değişkenlerine dayalı somut işlevler oluşturur. Çoğu durumda, şablon tür bağımsız değişkenleri çıkarabiliyor ve bu nedenle bunları açıkça belirtmeniz gerekmez.

```cpp
template<typename Lhs, typename Rhs>
auto Add2(const Lhs& lhs, const Rhs& rhs)
{
    return lhs + rhs;
}

auto a = Add2(3.13, 2.895); // a is a double
auto b = Add2(string{ "Hello" }, string{ " World" }); // b is a std::string
```

Daha fazla bilgi için [İşlev Şablonları'na](../cpp/function-templates.md) bakın

## <a name="function-parameters-and-arguments"></a>Fonksiyon parametreleri ve bağımsız değişkenler

Bir işlev, her biri işlev gövdesi içinde erişilebilen bir ad almıştır sıfır veya daha fazla tür virgülle ayrılmış parametre listesi vardır. İşlev şablonu ek tür veya değer parametreleri belirtebilir. Arayan, türleri parametre listesiyle uyumlu olan somut değerler olan bağımsız değişkenleri geçirir.

Varsayılan olarak, bağımsız değişkenler işleve değer olarak aktarılır, bu da işlevin geçirilen nesnenin bir kopyasını aldığı anlamına gelir. Büyük nesneler için, kopya yapmak pahalı olabilir ve her zaman gerekli değildir. Bağımsız değişkenlerin referansla geçirilmesine (özellikle lvalue başvurusu) neden olmak için, parametreye bir referans niceleyicisi ekleyin:

```cpp
void DoSomething(std::string& input){...}
```

Bir işlev başvuru yla geçirilen bir bağımsız değişkeni modiöldüğünde, yerel bir kopyayı değil, özgün nesneyi değiştirir. Bir işlevin böyle bir bağımsız değişkeni değiştirmesini önlemek için, parametreyi const& olarak nitelendirin:

```cpp
void DoSomething(const std::string& input){...}
```

**C++ 11:**  Rvalue-reference veya lvalue-reference ile geçirilen bağımsız değişkenleri açıkça işlemek için, evrensel bir başvuruyu belirtmek için parametreüzerinde çift ampersand kullanın:

```cpp
void DoSomething(const std::string&& input){...}
```

Parametre bildirimi listesinde tek anahtar kelime **geçersizliği** ile bildirilen bir işlev, anahtar kelime **geçersiz** bağımsız değişken bildirimi listesinin ilk ve tek üyesi olduğu sürece hiçbir bağımsız değişken alır. Listenin başka bir yerinde ki tür **geçersiz** bağımsız değişkenleri hata üretir. Örneğin:

```cpp

// OK same as GetTickCount()
long GetTickCount( void );
```

Burada özetlenenler dışında **geçersiz** bir bağımsız değişken belirtmek yasa dışı olmakla birlikte, tür **geçersizden** türetilen türlerin **(void** işaretçileri ve **boşluk**dizileri gibi) bağımsız değişken bildirim listesinin her yerinde görünebileceğini unutmayın.

### <a name="default-arguments"></a>Varsayılan Bağımsız Değişkenler

İşlev imzasındaki son parametre veya parametrelere varsayılan bir bağımsız değişken atanabilir, bu da arayanın başka bir değer belirtmek istemedikleri sürece işlevi ararken bağımsız değişkeni dışarıda bırakabileceği anlamına gelir.

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

Daha fazla bilgi için [Varsayılan Bağımsız Değişkenler'e](../cpp/default-arguments.md)bakın.

## <a name="function-return-types"></a>İşlev dönüş türleri

Bir işlev başka bir işlev veya yerleşik bir dizi döndürmeyebilir; ancak işaretçileri bu türlere veya bir işlev nesnesi üreten *lambda'ya*döndürebilir. Bu durumlar dışında, bir işlev kapsamda ki herhangi bir türde bir değer döndürebilir veya hiçbir değer döndürmeyebilir, bu durumda iade türü **geçersizdir.**

### <a name="trailing-return-types"></a>Sondaki dönüş türleri

İşlev imzasının sol tarafında "sıradan" bir dönüş türü bulunur. *İzleyen bir dönüş türü* imzanın sağ tarafında yer alır ve önce -> işleci gelir. İade değeri türü şablon parametrelerine bağlı olduğunda, sondaki iade türleri özellikle işlev şablonlarında kullanışlıdır.

```cpp
template<typename Lhs, typename Rhs>
auto Add(const Lhs& lhs, const Rhs& rhs) -> decltype(lhs + rhs)
{
    return lhs + rhs;
}
```

**Otomatik** bir sonda dönüş türü ile birlikte kullanıldığında, sadece decltype ifadesi üretir ne olursa olsun bir yer tutucu olarak hizmet vermektedir ve kendisi tür çıkarımı gerçekleştirmez.

## <a name="function-local-variables"></a>İşlev yerel değişkenleri

Bir işlev gövdesi içinde bildirilen bir *değişkene yerel değişken* veya sadece *yerel*değişken denir. Statik olmayan yerel ler yalnızca işlev gövdesiiçinde görünür ve yığında bildirilirlerse işlev çıktığında kapsam dışına çıkarlar. Yerel bir değişken oluşturup değere göre döndürdükten sonra, derleyici gereksiz kopyalama işlemlerini önlemek için genellikle *adlandırılmış iade değeri optimizasyonu* gerçekleştirebilir. Yerel bir değişkeni başvuru yla döndürerseniz, derleyici bir uyarı yayımlar, çünkü arayan tarafından bu başvuruyu kullanma girişimi yerel yok edildikten sonra gerçekleşir.

C++'da yerel bir değişken statik olarak bildirilebilir. Değişken yalnızca işlev gövdesi içinde görünür, ancak değişkenin tek bir kopyası işlevin tüm örnekleri için vardır. Yerel statik nesneler `atexit` tarafından belirtilen sonlandırma sırasında yok edilir. Programın denetim akışı bildirimi atlamasından dolayı statik nesne oluşturulmazsa, söz konusu nesneyi yok etmek için girişimde bulunulmaz.

## <a name="type-deduction-in-return-types-c14"></a><a name="type_deduction"></a>İade türlerinde tür çıkarımı (C++14)

C++14'te, parçalayıcıyı, sondalı bir dönüş türü sağlamak zorunda kalmadan işlev gövdesinden geri dönüş türünü çıkarmasını bildirmek için **otomatik** olarak kullanabilirsiniz. Otomatik **in** her zaman bir return-by-value üzerinde sonuç verdiğini unutmayın. Derleyiciye bir başvuruyu anlması için talimat vermek için kullanın. `auto&&`

Bu örnekte, **otomatik** lhs ve rhs toplamının const olmayan bir değer kopyası olarak çıkarılacaktır.

```cpp
template<typename Lhs, typename Rhs>
auto Add2(const Lhs& lhs, const Rhs& rhs)
{
    return lhs + rhs; //returns a non-const object by value
}
```

**Otomatik** sonucuna vardığı türün const-ness korumaz unutmayın. İade değeri bağımsız değişkenlerinin const-ness veya ref-ness korumak için gereken yönlendirme işlevleri için, **decltype** türü çıkarım kuralları nı kullanan ve tüm tür bilgilerini koruyan **decltype(otomatik)** anahtar sözcük kullanabilirsiniz. **decltype(otomatik)** sol tarafta sıradan bir iade değeri olarak veya sondalı bir iade değeri olarak kullanılabilir.

Aşağıdaki örnek [(N3493](https://wg21.link/n3493)koduna dayalı), şablon anında bulunana kadar bilinmeyen bir dönüş türünde işlev bağımsız değişkenlerinin mükemmel iletilmesini sağlamak için kullanılan **decltype(auto)** gösterir.

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

Bir işlevden birden fazla değer döndürmenin çeşitli yolları vardır:

1. Adlandırılmış bir sınıf veya yapı nesnesi değerlerini kapsüllemek. Sınıf veya yapı tanımının arayanın görünür olmasını gerektirir:

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

1. Std::tuple veya std::pair nesnesi:

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

1. **Visual Studio 2017 sürüm 15.3 ve sonrası** [(/std:c++17](../build/reference/std-specify-language-standard-version.md)ile birlikte kullanılabilir ): Yapılandırılmış ciltler kullanın. Yapılandırılmış bağlamaların avantajı, iade değerlerini depolayan değişkenlerin, beyan edildikleri anda başharflere alınmasıdır ve bu da bazı durumlarda önemli ölçüde daha verimli olabilir. Bu ifadede`auto[x, y, z] = f();`-- -- parantezler tüm işlev bloğu için kapsamda olan adları tanıyır ve başlatır.

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

1. İade değerinin kendisini kullanmanın yanı sıra, işlevin arayanın sağladığı nesnelerin değerlerini değiştirebilmeleri veya başlatılması için geçiş başvurusu kullanmak için herhangi bir sayıda parametre tanımlayarak değerleri "döndürebilirsiniz". Daha fazla bilgi için [Bkz. Başvuru Türü İşlev Bağımsız Değişkenleri.](reference-type-function-arguments.md)

## <a name="function-pointers"></a>İşlev işaretçileri

C++ işlev işaretçilerini C diliyle aynı şekilde destekler. Ancak daha tür güvenli bir alternatif genellikle bir işlev nesnesi kullanmaktır.

İşlev işaretçisi türünü döndüren bir işlev bildiriyorsa, işlev işaretçisi türü için bir diğer ad bildirmek için **typedef** kullanılması önerilir.  Örneğin:

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
