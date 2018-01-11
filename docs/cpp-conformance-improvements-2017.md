---
title: "C++ uygunluk geliştirmeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3a1010d7061fb8df20cc821e26e903e356050850
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-conformance-improvements-in-visual-studio-2017-versions-150-153improvements153-and-155improvements155"></a>C++ uygunluk geliştirmeleri 15.0, Visual Studio 2017 sürümlerde [15.3](#improvements_153) ve [15,5](#improvements_155).


Genelleştirilmiş constexpr desteği ve Toplamalar için NSDMI ile derleyici C ++ 14 standart eklenen özellikler için tamamlanmıştır. Yine de derleyicide C++11 ve C++98 Standartlarındaki bazı özellikler eksiktir. Bkz: [Visual C++ dili uygunluk](visual-cpp-language-conformance.md) derleyici geçerli durumunu gösteren bir tablo için.

## <a name="c11"></a>C ++ 11
**İfade SFINAE desteği daha fazla kitaplıklarında** Visual C++ Derleyici devam eder, desteğini ifade SFINAE, burada decltype ve constexpr ifadeleri görünebilir olarak şablon bağımsız değişken kesintisi ve değiştirme için gerekli olduğu artırmak Şablon parametreleri. Daha fazla bilgi için bkz: [Visual Studio 2017 RC ifade SFINAE yenilikleri](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3). 


## <a name="c-14"></a>C++ 14
**Toplamalar için NSDMI** bir dizi veya hiçbir kullanıcı tarafından sağlanan oluşturucusu, hiçbir özel veya korumalı olmayan statik veri üyeleri, hiçbir temel sınıflar ve hiçbir sanal işlevler sınıfıyla toplama başvurudur. C ++ 14 toplamalar'den itibaren üye başlatıcıları içerebilir. Daha fazla bilgi için bkz: [üye başlatıcılar ve toplamalar](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html).

**Constexpr Genişletilmiş** constexpr bildirilen ifadeleri, bildirimler, belirli türde içerebilir ve ifadeler, döngü ifadeleri ve mutation, yaşam süresi içinde constexpr ifade değerlendirme başlangıcından nesnelerin geçiş yapmak için şimdi verilir. Ayrıca, artık constexpr statik olmayan üye işlevi örtük olarak const bir gereksinimi yoktur. Daha fazla bilgi için bkz: [constexpr işlevleri kısıtlamalar gevşetme](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html). 

## <a name="c17"></a>C ++ 17
**Terse static_assert** (bulunan/Std: c ++ 17) C ++ 17 static_assert iletisi parametresi isteğe bağlıdır. Daha fazla bilgi için bkz: [geniletmek static_assert, v2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf). 

**[[fallthrough]] özniteliği** (bulunan/Std: c ++ 17) [[fallthrough]] özniteliği switch deyimleri bağlamında başarısızlığı davranışı geçmesini derleyici ipucu olarak kullanılabilir. Bu, derleyici uyarıları bu gibi durumlarda vermesini engeller. Daha fazla bilgi için bkz: [[[fallthrough]] özniteliği için ifadesi](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf). 

**Döngüler için aralık tabanlı genelleştirilmiş** (derleyici anahtar gerekli) aralığı tabanlı begin() ve end() aynı türde nesneler döndürmeye döngüler artık gerek için. Bu aralıklardaki tarafından kullanılan bir sentinel döndürülecek end() sağlar [aralığı v3](https://github.com/ericniebler/range-v3) ve tamamlandı ancak-değil-sessiz-yayımlanmış aralıkları teknik belirtim. Daha fazla bilgi için bkz: [Range-Based genelleme For döngüsü](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html). 

## <a name="improvements_153"></a>Visual Studio 2017 sürüm 15.3 yenilikleri

**constexpr Lambda'lar** Lambda ifadeleri şimdi sabit ifadelerinde kullanılamaz. Daha fazla bilgi için bkz: [Constexpr Lambda](http://open-std.org/JTC1/SC22/WG21/docs/papers/2015/n4487.pdf).

**varsa işlevi şablonlarındaki constexpr** işlevi şablon içerebilir `if constexpr` derleme zamanı dallanma etkinleştirmek için deyimleri. Daha fazla bilgi için bkz: [varsa constexpr](http://open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0128r1.html).

**Seçim deyimleri başlatıcıları ile** bir `if` deyimi bir değişkene deyimi içinde blok kapsamında tanıtan bir başlatıcı içerebilir. Daha fazla bilgi için bkz: [Başlatıcısı ile seçim deyimleri](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0305r1.html).

**[[maybe_unused]] ve [[nodiscard]] öznitelikleri** bir varlık kullanılmadığı görünürken uyarıları Sessiz ya da bir işlev çağrısının dönüş değerini atılır halinde bir uyarı oluşturmak için yeni öznitelikler. Daha fazla bilgi için bkz: [maybe_unused özniteliği için ifadesi](http://open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0212r0.pdf) ve [kullanılmayan, nodiscard ve fallthrough öznitelikleri önerisini](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0068r0.pdf).

**Yineleme olmadan özniteliği ad alanlarını kullanma** bir öznitelik listesinde yalnızca bir tek bir ad tanımlayıcısı etkinleştirmek için yeni sözdizimi. Daha fazla bilgi için bkz: [C++ öznitelikleri](cpp/attributes2.md).

**Bağlamaları yapılandırılmış** artık değer bir dizi, std::tuple veya std::pair olduğunda veya tüm ortak statik olmayan veri üyeleri olan bir değer, bileşenleri tek tek adlarıyla depolamak için tek bir bildirimde daha mümkündür. Daha fazla bilgi için bkz: [yapılandırılmış bağlamaları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0144r0.pdf).

**Enum için yapım kuralları sınıf değerleri** yapıldığında şimdi bir örtük/olmayan-daraltma kapsamlı bir numaralandırmanın temel türüne dönüştürme numaralandırması kendisi için hiçbir Numaralandırıcı tanımına tanıtır ve kaynağı kullanan bir Liste başlatma sözdizimi. Daha fazla bilgi için bkz: [enum için yapım kuralları sınıf değerleri ](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf).

**Yakalama *bu değere göre**  "\*bu" lambda ifadesi nesnesinde şimdi yakalanıp değeri. Bu, özellikle yeni makine mimarileri üzerinde paralel ve zaman uyumsuz işlemleri lambda içinde çağrılacak senaryolara olanak sağlar. Daha fazla bilgi için bkz: [Lambda yakalamayı \*bu değere göre [=\*bu]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html).

**Kaldırma operator ++ bool için** operator ++ artık desteklenmeyen üzerinde `bool` türleri. Daha fazla bilgi için bkz: [kaldırmak kullanım dışı operator++(bool)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html).

**Kaldırma kullanım dışı "register" anahtar sözcüğü** `register` anahtar sözcüğü, daha önce kullanım dışı (ve Visual C++ derleyicisi tarafından göz ardı) dilinden artık kaldırılmıştır. Daha fazla bilgi için bkz: [kullanım dışı kullanımı anahtar sözcük kaydı kaldırma](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html).

Visual Studio 2015 güncelleştirme 3'ü aracılığıyla uygunluk geliştirmeleri tam listesi için bkz: [Visual C++ ne ait yeni 2003 2015 aracılığıyla](https://msdn.microsoft.com/en-us/library/mt723604.aspx).

## <a name="improvements_155"></a>Visual Studio 2017 sürüm 15,5 yenilikleri
[14] ile işaretli özellikleri kullanılabilir koşulsuz olarak bile/Std: c içinde ++ 14 modu.

**Extern constexpr için yeni derleyici anahtar** Visual Studio'nun önceki sürümleri derleyici her zaman vermiş bir `constexpr` değişkeni bile işaretlendi, değişken iç bağlantı `extern`. Visual Studio 2017 sürüm 15,5, yeni bir derleyici anahtar içinde [/Zc:externConstexpr](build/reference/zc-externconstexpr.md), doğru standartları uyumsuz davranışı etkinleştirir. Daha fazla bilgi için bkz: [extern constexpr bağlantı](#extern_linkage).

**Dinamik özel durum belirtimleri kaldırma**: [P0003R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html). Dinamik özel durum belirtimleri C++11'de kullanım dışı bırakıldı. Özellik C ++ 17 ' kaldırılır, ancak (hala) kullanım dışı `throw()` belirtimi için diğer ad olarak kesinlikle tutulur `noexcept(true)`. Daha fazla bilgi için bkz: [dinamik özel durum belirtimi kaldırma ve noexcept](#noexcept_removal). 

**not_fn()** : [P0005R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html) not1 ve not2 yerini alır.

**Enable_shared_from_this uygun sözcükler kullanmak**: [P0033R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html) `enable_shared_from_this` C ++ 11'de eklendi. C ++ 17 standart daha iyi belirli köşe durumlarında belirtimi güncelleştirir. [14]

**MAPS ve kümelerini boşluklarına ayıran**: [P0083R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf). Bu özellik, daha sonra değiştirilebilir ve geri aynı kapsayıcı ya da aynı düğüm türü kullanan farklı bir kapsayıcı eklenen ilişkilendirilebilir kapsayıcıları (örn., harita, kümesi, unordered_map, unordered_set) düğümlerinin ayıklama sağlar. (Bir ortak kullanım std::map bir düğümü çıkarmak, kayıt anahtarını değiştirin ve yeniden için durumdur.)

**Vestigial kitaplığı bölümleri onaysız kılınmadan**: [P0174R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html). C++ Standart Kitaplığı, çeşitli özellikler göre yeni özellikler yıllar içinde kılınan, aksi takdirde çok kullanışlı olmaması veya sorunlu bulundu. Bu özellikler C ++ 17 resmi olarak kullanım dışı bırakılmıştır. 

**Destek ayırıcısı olarak std::function kaldırma**: [P0302R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html). C ++ 17 önce sınıf şablonu `std::function` ayırıcısı bağımsız değişken sürdü birkaç Oluşturucusu vardı. Ancak, bu bağlamda allocators kullanımını sorunlu ve semantiğini belirsiz. Bu nedenle bu contructors kaldırıldı.

**Not_fn() için düzeltmeler**: [P0358R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html). İçin yeni ifadesi `std::not_fn` değeri kategori sarmalayıcı çağırma durumunda yayılmasını desteği sağlar.

**shared_ptr < T [] >, < T [N] > shared_ptr**: [P0414R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html). Kitaplık temelleri shared_ptr değişikliklerden C ++ 17 için birleştirme. [14]

**Diziler için shared_ptr düzelttikten**: [P0497R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html). Shared_ptr destek diziler için giderir. [14]

**İnsert_return_type açıklığa kavuşturan**: [P0508R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html). Benzersiz anahtarlar ile ilişkilendirilebilir kapsayıcıları ve sırasız kapsayıcıları benzersiz anahtarlara sahip bir üye işlevi sahip `insert` iç içe geçmiş tür döndüren `insert_return_type`. Bu türü artık uzmanlık Yineleyici ve kapsayıcının NodeType parametreli bir türü olarak tanımlanmış olan döndür. 

**STL için satır içi değişkenleri**: [P0607R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html). 

**Kullanım dışı bırakılan annex D Özellikler** eki D C++ Standart dahil olmak üzere onaylanmamış tüm özellikler içeriyor `shared_ptr::unique()`, `<codecvt>`, ve `namespace std::tr1`. Zaman / Std: c ++ 17 derleyici anahtar olarak ayarlanmışsa, eki d neredeyse tüm standart kitaplığı özellikleri kullanım dışı olarak işaretlenir. Daha fazla bilgi için bkz: [eki D standart kitaplığı özellikleri kullanım dışı olarak işaretlenmiş](#annex_d).

`std::tr2::sys` Ad alanında `<experimental/filesystem>` artık kullanımdan kaldırma uyarısı/Std: c altında yayar ++ 14 varsayılan olarak ve şimdi/Std: c altında kaldırılır ++ 17 varsayılan olarak.

Standart olmayan bir uzantı (sınıf açık özelleştirmeleri) önleme tarafından iostreams geliştirilmiş uyumluluğu.

Standart Kitaplığı şimdi değişken şablonlar dahili olarak kullanır.

Standart Kitaplığı, yanıt noexcept eklenmesi tür sistemi ve dinamik özel durum belirtimleri kaldırılmasını dahil C ++ 17 derleyici değişiklikler olarak güncelleştirildi.

## <a name="bug-fixes-in-visual-studio-versions-150-153update153-and-155update155"></a>Visual Studio sürümlerinde 15.0, hata düzeltmeleri [15.3](#update_153), ve [15,5](#update_155)
### <a name="copy-list-initialization"></a>Kopya listesi başlatma
Visual Studio 2017, doğru nesne oluşturma, Visual Studio 2015'te yakalanan değil ve çökme (Crash) için yol açabilecek Başlatıcı Listeleri kullanarak ilgili derleyici hataları başlatır veya tanımsız çalışma zamanı davranışı. Copy-listesi-başlatılmasında N4594 13.3.1.7p1 göredir derleyici aşırı yükleme çözünürlüğü için açık bir oluşturucu dikkate alınması gereken gereklidir, ancak bu aşırı gerçekte seçilirse hatayla yükseltmeniz gerekir. 

Aşağıdaki iki örnek Visual Studio 2015'te ancak Visual Studio 2017'de derleyin.
```cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    A a1 = { 1 }; // error C3445: copy-list-initialization of 'A' cannot use an explicit constructor
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot convert from 'int' to 'const A &'

}
```
Hatayı düzeltmek için doğrudan başlatma kullanın:
```cpp  
A a1{ 1 };
const A& a2{ 1 };
```

Visual Studio 2015'te derleyici yanlışlıkla kopyalama listesi başlatma Normal kopyalama başlatma aynı şekilde ele; yalnızca oluşturucuları aşırı yükleme çözünürlüğü için dönüştürme kabul. Aşağıdaki örnekte, Visual Studio 2015 MyInt(23) ancak Visual Studio 2017 doğru hata başlatır seçer. 

```cpp  
// From http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_closed.html#1228
struct MyStore {
       explicit MyStore(int initialCapacity);
};

struct MyInt {
       MyInt(int i);
};

struct Printer {
       void operator()(MyStore const& s);
       void operator()(MyInt const& i);
};

void f() {
       Printer p;
       p({ 23 }); // C3066: there are multiple ways that an object of this type can be called with these arguments
}
```

Bu örnek önceki bir benzer ancak farklı bir hata oluşturur. Visual Studio 2015'te başarılı ve Visual Studio 2017 C2668 ile de başarısız olur. 

```cpp  
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```

### <a name="deprecated-typedefs"></a>Kullanım dışı tür tanımları
Visual Studio 2017 şimdi bir sınıf veya yapı biriminde bildirilen kullanım dışı tür tanımları için doğru uyarı verir. Aşağıdaki örnek, Visual Studio 2015'te uyarılar olmadan derler ancak Visual Studio 2017 C4996 üretir.

```cpp  
struct A 
{
    // also for __declspec(deprecated) 
    [[deprecated]] typedef int inttype;
};

int main()
{
    A::inttype a = 0; // C4996 'A::inttype': was declared deprecated
}
```

### <a name="constexpr"></a>constexpr
Koşullu değerlendirilirken işlemi sol işleneni bir constexpr bağlamında geçerli olmadığında visual Studio 2017 doğru bir hata oluşturur. Aşağıdaki kod, Visual Studio 2015'te ancak Visual Studio 2017 (C3615 constexpr işlevi 'f' sabit bir ifade olamaz) derler:

```cpp  
template<int N>
struct array 
{
       int size() const { return N; }
};

constexpr bool f(const array<1> &arr)
{
       return arr.size() == 10 || arr.size() == 11; // C3615    
}
```
Hatayı düzeltmek için dizi:: size() işlevi constexpr bildirme veya constexpr niteleyici f kaldırın. 

### <a name="class-types-passed-to-variadic-functions"></a>Variadic, işlevlere geçirilen sınıf türleri
Visual Studio 2017 sınıfları veya printf gibi variadic işlevine geçirilen yapılar trivially copyable olması gerekir. Bu tür nesneleri geçirirken, derleyici, sadece Bitsel bir kopya oluşturur ve oluşturucunun ya da yıkıcı çağırmaz. 

```cpp  
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function
                        // note: the constructor and destructor will not be called; 
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function

    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);
    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                      // as an argument to a variadic function
}
```
Hatayı düzeltmek için trivially copyable türü döndüren bir üye işlev çağrısı, 

```cpp  
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```
Aksi takdirde geçirmeden önce nesneyi dönüştürmek için bir statik atama gerçekleştirin:
```cpp  
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```
Oluşturulan ve yönetilen CStringW, kullanarak dizeleri için sağlanan `operator LPCWSTR()` biçim dizesi tarafından beklenen C işaretçi CStringW nesnesine dönüştürmek için kullanılmalıdır.

```cpp  
CStringW str1;
CStringW str2;
str1.Format(L"%s", static_cast<LPCWSTR>(str2));
```

### <a name="cv-qualifiers-in-class-construction"></a>MS-niteleyicileri içinde sınıfı oluşturma
Visual Studio 2015'te derleyici bazen yanlış Oluşturucusu aramasıyla sınıf nesnesi oluşturulurken MS-niteleyici yoksayar. Bu büyük olasılıkla bir kilitlenme veya beklenmeyen çalışma zamanı davranışını neden olabilir. Aşağıdaki örnek, Visual Studio 2015'te derler ancak Visual Studio 2017'deki bir derleyici hatası oluşturur:

```cpp  
struct S 
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```
Hatayı düzeltmek için işleci Int() const olarak bildirin. 

### <a name="access-checking-on-qualified-names-in-templates"></a>Nitelikli adlar şablonlarındaki denetimi erişim
Derleyici önceki sürümleri, bazı şablon bağlamlarında nitelenmiş adlar denetimi erişim gerçekleştirmedi. Bu, beklenen SFINAE davranışı değiştirme bir ad inaccessibility nedeniyle başarısız olmasına beklenirken etkileyebilir. Bu olası kilitlenme veya yanlış işleci yanlış yüklemesini çağırma derleyici nedeniyle çalışma zamanında beklenmeyen davranışlara neden olmuş. Visual Studio 2017 ' bir derleyici hatası oluştu. Özel hata farklılık gösterebilir, ancak genellikle "eşleşme bulundu işlevi aşırı C2672" dır. Aşağıdaki kod, Visual Studio 2015'te derler ancak Visual Studio 2017 bir hata oluşturur:

```cpp  
#include <type_traits>

template <class T> class S {
       typedef typename T type;
};

template <class T, std::enable_if<std::is_integral<typename S<T>::type>::value, T> * = 0>
bool f(T x);

int main()
{
       f(10); // C2672: No matching overloaded function found. 
}
```

### <a name="missing-template-argument-lists"></a>Eksik şablon bağımsız değişken listeleri
Şablon (örneğin varsayılan şablon bağımsız değişken veya kapsamında tür olmayan şablon parametresi) bir şablon parametre listesinde görüntülendiğinde Visual Studio 2015 ve önceki sürümlerinde, derleyici eksik şablon bağımsız değişken listeleri tanılayın değil. Bu derleyici çökme (Crash) dahil olmak üzere beklenmeyen davranışlara veya beklenmeyen çalışma zamanı davranışı neden olabilir. Aşağıdaki kod, Visual Studio 2015'te derler ancak Visual Studio 2017 hata üretir.

```cpp  
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias 
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;  
```

### <a name="expression-sfinae"></a>İfade SFINAE
Şablonları bildirilen örneği yerine olduğunda ifade SFINAE desteği için derleyici şimdi decltype bağımsız değişkenlerini ayrıştırır. Sonuç olarak, bağlı olmayan uzmanlık decltype değişkeninde bulunursa, örnek oluşturma zamanında ertelenmiş değil ve hemen işlenir ve sonuçta ortaya çıkan hataları o anda koydu.  

Aşağıdaki örnek, bildirim noktasında tetiklenir böyle bir derleyici hatası gösterir:

```cpp  
#include <utility>
template <class T, class ReturnT, class... ArgsT> class IsCallable
{
public:
       struct BadType {};
       template <class U>
       static decltype(std::declval<T>()(std::declval<ArgsT>()...)) Test(int); //C2064. Should be declval<U>
       template <class U>
       static BadType Test(...);
       static constexpr bool value = std::is_convertible<decltype(Test<T>(0)), ReturnT>::value;
};

constexpr bool test1 = IsCallable<int(), int>::value;
static_assert(test1, "PASS1");
constexpr bool test2 = !IsCallable<int*, int>::value;
static_assert(test2, "PASS2");
```
### <a name="classes-declared-in-anonymous-namespaces"></a>Anonim ad alanlarında bildirilen sınıfları
C++ Standart göre anonim bir ad alanı içinde bildirilen bir sınıf iç bağlantı vardır ve bu nedenle verilemez. Visual Studio 2015 ve önceki sürümleri, bu kural zorunlu değildir. Visual Studio 2017 içinde kural kısmen zorlanır. Aşağıdaki örnek Visual Studio 2017 bu hatayı başlatır: "hata C2201: const anonim namespace::S1::vftable: dış bağlantı dışarı/alınması için olması gerekir."

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>Varsayılan başlatıcılar değeri için sınıf üyeleri (C + +/ CLI)
Visual Studio 2015 ve önceki sürümlerinde, derleyici izin (ancak göz ardı) bir değer sınıfı üyesi için varsayılan üye başlatıcıdan. Varsayılan olarak başlatılması değer sınıfı her zaman sıfır-üyeleri başlatır; Varsayılan bir oluşturucu izin verilmez. Visual Studio 2017 ' varsayılan üye başlatıcıları Bu örnekte gösterildiği gibi bir derleyici hatası Yükselt:

```cpp  
value struct V
{
       int i = 0; // error C3446: 'V::i': a default member initializer  
                  // is not allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>Varsayılan dizin oluşturucular (C + +/ CLI)
Visual Studio 2015 ve önceki sürümleri, bazı durumlarda derleyici varsayılan bir özellik bir varsayılan dizin oluşturucu misidentified. Bir özelliğe erişmek için "varsayılan" tanımlayıcıyı kullanarak sorunu çözmek mümkündü. Varsayılan olarak bir anahtar sözcük C ++ 11 tanıtılan sonra geçici sorunlu hale geldi. Bu nedenle, Visual Studio 2017 içinde geçici çözüm gerekli hatalar düzeltilmiştir ve "varsayılan" bir sınıf için varsayılan özelliğine erişmek için kullanıldığında, derleyici şimdi hata başlatır.

```cpp  
//class1.cs

using System.Reflection;
using System.Runtime.InteropServices;

namespace ClassLibrary1
{
    [DefaultMember("Value")]
    public class Class1
    {
        public int Value
        {
            // using attribute on the return type triggers the compiler bug
            [return: MarshalAs(UnmanagedType.I4)]
            get;
        }
    }
    [DefaultMember("Value")]
    public class Class2
    {
        public int Value
        {
            get;
        }
    }
}

 
// code.cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value; // error
       r1->default;
       r2->Value;
       r2->default; // error
}
```

Visual Studio 2017 ', her iki değeri özellik adına göre erişebilirsiniz:

```cpp  
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value;
       r2->Value;
}
```

## <a name="update_153"></a>Visual Studio 2017 sürüm 15.3 hata düzeltmeleri
### <a name="calls-to-deleted-member-templates"></a>Silinen üye şablonları çağrıları
Visual Studio'nun önceki sürümleri, bazı durumlarda derleyici hatalı oluşturulmuş çağrılar çökme (Crash) çalışma zamanında olası nedeni silinmiş üyeyi şablon için bir hata yaymak üzere başarısız olur. Aşağıdaki kod C2280, şimdi üreten "'int S<int>:: f<int>(void)': silinen işlevi başvuru girişimi":
```cpp
template<typename T> 
struct S { 
   template<typename U> static int f() = delete; 
}; 
 
void g() 
{ 
   decltype(S<int>::f<int>()) i; // this should fail 
}
```
Hatayı düzeltmek için i bildirme olarak `int`.

### <a name="pre-condition-checks-for-type-traits"></a>Tür özellikleri için ön koşul denetimleri
Visual Studio 2017 sürüm 15.3 daha kesinlikle standart izlemek tür-özellikleri için ön koşul denetimleri artırır. Bu tür bir denetimi içindir atanabilir. Aşağıdaki kod, Visual Studio 2017 sürüm 15.3 C2139 üretir:

```cpp
struct S; 
enum E; 
 
static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>Yönetilen yerel hazırlama üzerinde yeni derleyici uyarı ve çalışma zamanı denetimleri
Yerel işlevleri çağırma yönetilen işlevlerden dizimi gerektirir. Hazırlama CLR yapar ancak C++ semantiği anlamıyor. Yerel bir nesne değeri geçirirseniz, CLR nesnenin copy-constructor çağrısı veya çalışma zamanında tanımsız davranışa neden olabilir BitBlt kullanın. 
 
Şimdi, silinen copy ctor yerel bir nesneyle değeriyle yerel ve yönetilen sınır arasında geçirilen derleme zamanında biliyorsanız, derleyici bir uyarı yayma. Böylece bir hatalı oluşturulmuş dizimi oluştuğunda hemen program std::terminate çağıracak derleyici derleme zamanında bilmiyor bu gibi durumlarda, bir çalışma zamanı denetimi ekle. Visual Studio 2017 içinde sürüm 15.3, aşağıdaki kodu C4606 üreten "'A': bağımsız değişkeni değere göre yerel ve yönetilen sınırından geçirme geçerli kopya Oluşturucu gerektirir. Aksi halde çalışma zamanı davranışı tanımlı değil".
```cpp
class A 
{ 
public: 
   A() : p_(new int) {} 
   ~A() { delete p_; } 
 
   A(A const &) = delete; 
   A(A &&rhs) { 
   p_ = rhs.p_; 
} 
 
private: 
   int *p_; 
}; 
 
#pragma unmanaged 
 
void f(A a) 
{ 
} 
 
#pragma managed 
 
int main() 
{ 
    f(A()); // This call from managed to native requires marshalling. The CLR doesn't understand C++ and uses BitBlt, which will result in a double-free later. 
}
```
Hatayı düzeltmek için kaldırma `#pragma managed` arayanı yerel olarak işaretlemek ve dizimi önlemek için yönergesi. 

### <a name="experimental-api-warning-for-winrt"></a>WinRT için Deneysel API Uyarısı
Deneme ve görüşlerinizi ile donatılmış için yayımlanan WinRT API'leri `Windows.Foundation.Metadata.ExperimentalAttribute`. Visual Studio 2017 içinde sürüm 15.3, öznitelik karşılaştığında derleyici C4698 uyarı üretecektir. Öznitelik önceki sürümlerinde Windows SDK'sı, birkaç API'leri zaten donatılmış ve bu API çağrıları Bu derleyici uyarının tetikleneceği başlar. Daha yeni Windows SDK'ları tüm sevk edilen türlerinden kaldırılan özniteliğine sahip, ancak daha eski bir SDK kullanıyorsanız, tüm çağrılar sevk edilen türleri için bu uyarıları bastırma gerekir.
Aşağıdaki kod C4698 uyarı üretir: "'Windows:: Depolama:: IApplicationDataStatics2::GetForUserAsync' olduğu değerlendirme yalnızca amacıyla ve değiştirilebilir veya temizleme gelecekteki güncelleştirmeleri":
```cpp
Windows::Storage::IApplicationDataStatics2::GetForUserAsync() //C4698
```

Uyarıyı devre dışı bırakmak için bir #pragma ekleyin:

```cpp
#pragma warning(push) 
#pragma warning(disable:4698) 
 
Windows::Storage::IApplicationDataStatics2::GetForUserAsync() 
 
#pragma warning(pop)
```
### <a name="out-of-line-definition-of-a-template-member-function"></a>Satır dışı tanımını bir şablon üye işlevi 
**Visual Studio 2017 sürüm 15.3** sınıfında bildirilmedi bir şablon üye işlevi satır dışı tanımını karşılaştığında bir hata oluşturur. Aşağıdaki kod artık hata C2039 üretir: 'f': bir üyesi değil 'S':

```cpp
struct S {}; 
 
template <typename T> 
void S::f(T t) {} //C2039: 'f': is not a member of 'S'
```

Hatayı düzeltmek için bir bildirim sınıfına ekleyin:

```cpp
struct S { 
    template <typename T> 
    void f(T t); 
}; 
template <typename T> 
void S::f(T t) {}
```

### <a name="attempting-to-take-the-address-of-this-pointer"></a>"Bu" işaretçi adresini alın çalışılıyor
C++'ta '' bir prvalue türü işaretçinin x budur. 'This' adresi alamaz veya bir lvalue başvuru bağlayın. Visual Studio'nun önceki sürümleri derleyici, bu kısıtlamayı bir cast gerçekleştirerek sağlamasına olanak tanır. Visual Studio 2017 içinde sürüm 15.3, derleyici hatası C2664 oluşturur.

### <a name="conversion-to-an-inaccessible-base-class"></a>Erişilemez bir temel sınıf dönüştürme
**Visual Studio 2017 sürüm 15.3** erişilemeyen bir taban sınıfı için bir tür dönüştürmeye çalıştığınızda bir hata oluşturur. Derleyici şimdi başlatır "hata C2243: 'tür belirtimi': dönüştürme vardı *' için ' B *' var, ancak erişilemiyor". Aşağıdaki kod, hatalı biçimlendirilmiş ve çalışma zamanında bir kilitlenme neden olabilir. Aşağıdakine benzer bir kod karşılaştığında derleyici C2243 şimdi üretir:

```cpp
#include <memory> 
 
class B { }; 
class D : B { }; // C2243. should be public B { }; 
 
void f() 
{ 
   std::unique_ptr<B>(new D()); 
}
```
### <a name="default-arguments-are-not-allowed-on-out-of-line-definitions-of-member-functions"></a>Varsayılan bağımsız değişkenler üye işlevleri satır tanımları dışında izin verilmez
Varsayılan bağımsız değişkenler yapılamaz üye işlevleri şablon sınıfları derleyici altında / izin veren bir uyarı vermek ve altında / izin veren sabit bir hata, satır dışı tanımlarını-. 

Visual Studio'nun önceki sürümleri aşağıdaki hatalı oluşturulmuş kodu olası çalışma zamanı çökmeyle neden olabilir. Visual Studio 2017 sürüm 15.3 üreten uyarı C5034: ' A<T>:: f': sınıf şablonu üyesi satır dışı tanımını varsayılan bağımsız değişkenler olamaz:
```cpp
 
template <typename T> 
struct A { 
    T f(T t, bool b = false); 
}; 
 
template <typename T> 
T A<T>::f(T t, bool b = false) // C5034
{ 
... 
}
```
Hatayı düzeltmek için "= false" varsayılan bağımsız kaldırın. 

### <a name="use-of-offsetof-with-compound-member-designator"></a>Offsetof ile bileşik üye göstergesi kullanımı
Wln seçeneğiyle derlerken Visual Studio 2017 içinde sürüm 15.3, m "bileşik üye Belirleyicisi" olduğu offsetof (T, m) kullanarak bir uyarısına neden olur. Aşağıdaki kod, hatalı biçimlendirilmiş ve çalışma zamanında bir kilitlenme neden olabilir. Visual Studio 2017 sürüm 15.3 üreten "C4841 Uyarı: kullanılan standart uzantısı: bileşik üye Belirleyicisi offseto içinde":

```cpp
  
struct A { 
int arr[10]; 
}; 
 
// warning C4841: non-standard extension used: compound member designator in offsetof 
constexpr auto off = offsetof(A, arr[2]);
```
Kod düzeltmek için bir pragma uyarıyla devre dışı bırakır veya kodu offsetof kullanmayacak şekilde değiştirin: 

```cpp
#pragma warning(push) 
#pragma warning(disable: 4841) 
constexpr auto off = offsetof(A, arr[2]); 
#pragma warning(pop) 
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>Statik veri üyesi veya üye işlevi offsetof kullanma
Visual Studio, statik veri üyesi m başvuruyor veya üye işlevi bir hatayla sonuçlanır offsetof (T, m) kullanarak 2017 içinde sürüm 15.3. Aşağıdaki kod üretir "hata C4597: tanımsız davranış: 'foo' üye işlevine uygulanan offsetof" ve "hata C4597: tanımsız davranış: statik veri üyesi 'Çubuğu' uygulanan offsetof":
```cpp
 
#include <cstddef> 
 
struct A { 
int foo() { return 10; } 
static constexpr int bar = 0; 
}; 
 
constexpr auto off = offsetof(A, foo); 
Constexpr auto off2 = offsetof(A, bar);
```
 
Bu kod, hatalı biçimlendirilmiş ve çalışma zamanında bir kilitlenme neden olabilir. Hatayı düzeltmek için artık tanımsız davranışı çağırmak için kodu değiştirin. C++ Standart tarafından izin verilmeyen taşınabilir olmayan kodu budur.

### <a name="declspec"></a>Yeni uyarı declspec öznitelikleri hakkında
__Declspec(...) extern "C" bağlantı belirtimi önce uygulandıysa, Visual Studio 2017 içinde sürüm 15.3, derleyici öznitelikleri artık yoksayar. Daha önce derleyici, çalışma zamanı etkileri olabilir attritbute göz ardı. Zaman `/Wall /WX` seçeneği olarak ayarlanmışsa, aşağıdaki kod üretmez "C4768 Uyarı: bağlantı belirtimi önce __declspec öznitelikleri yok sayılır":

```cpp
 
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

Uyarı, put extern "C" ilk düzeltmek için:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```
Bu uyarı-varsayılan olarak kapalı (üzerinde varsayılan olarak 15,5) ve yalnızca ile derlenmiş kod etkiler `/Wall /WX`.

### <a name="decltype-and-calls-to-deleted-destructors"></a>decltype ve Silinen yıkıcı çağrıları
Silinen yıkıcı bir çağrı 'decltype' ile ilişkili ifade bağlamda oluştuğunda Visual Studio'nun önceki sürümleri derleyici algılamadı. Visual Studio 2017 içinde sürüm 15.3, aşağıdaki kod üretir "hata C2280: ' A<T>:: ~ A(void)': silinen işlevi başvuru girişimi":

```cpp
template<typename T> 
struct A 
{ 
   ~A() = delete; 
}; 
 
template<typename T> 
auto f() -> A<T>; 
 
template<typename T> 
auto g(T) -> decltype((f<T>())); 
 
void h() 
{ 
   g(42); 
}
```
### <a name="uninitialized-const-variables"></a>Başlatılmamış const değişkenleri
Visual Studio 2017 RTW yayın 'const' değişkeni başlatılmadı, C++ derleyicisi bir tanılama verilmediğine olmayan bir gerileme vardı. Bu regresyon Visual Studio 2017 sürüm 15.3 düzeltilmiştir. Aşağıdaki kod artık üretir "C4132 Uyarı: 'Value': const nesne başlatılmalıdır":

```cpp
const int Value; //C4132
```
Hatayı düzeltmek için bir değer atadığınız `Value`.

### <a name="empty-declarations"></a>Boş bildirimleri
**Visual Studio 2017 sürüm 15.3** tüm türleri için yalnızca yerleşik türler boş bildirimlerinde şimdi sizi uyarır. Aşağıdaki kod artık tüm dört bildirimleri Düzey 2 C4091 uyarı üretir:

```cpp
struct A {};
template <typename> struct B {};
enum C { c1, c2, c3 };
 
int;    // warning C4091 : '' : ignored on left of 'int' when no variable is declared
A;      // warning C4091 : '' : ignored on left of 'main::A' when no variable is declared
B<int>; // warning C4091 : '' : ignored on left of 'B<int>' when no variable is declared
C;      // warning C4091 : '' : ignored on left of 'C' when no variable is declared
```

Uyarıları, yalnızca açıklama genişletme kaldırın veya boş bildirimleri kaldırmak için. Burada beklemediğiniz adlandırılmış nesne (RAII gibi) bir yan etkisi olması amaçlanmıştır durumlarda bir ad verilmelidir.
 
Uyarı /Wv:18 altında hariç tutulan ve düzey W2 uyarı altında varsayılan olarak etkindir.


### <a name="stdisconvertible-for-array-types"></a>dizi türleri için Std::is_convertible
Derleyici önceki sürümleri için yanlış sonuçları vermiş [std::is_convertible](standard-library/is-convertible-class.md) dizi türleri için. Bu özel durum kitaplığı yazıcılarının Visual C++ derleyicisi kullanırken gerekli `std::is_convertible<…>` türü ayırdedici nitelik. Aşağıdaki örnekte, Visual Studio'nun önceki sürümleri geçişinde statik onaylar ancak Visual Studio 2017 sürüm 15.3 başarısız:

```cpp
#include <type_traits>
 
using Array = char[1];
 
static_assert(std::is_convertible<Array, Array>::value);
static_assert(std::is_convertible<const Array, const Array>::value, "");
static_assert(std::is_convertible<Array&, Array>::value, "");
static_assert(std::is_convertible<Array, Array&>::value, "");
```

**Std::is_convertible < gelen, >** bir sanal işlev tanımı iyi biçimlendirilmiş olup olmadığını görmek için kontrol ederek hesaplanır:
```cpp 
   To test() { return std::declval<From>(); }
``` 

### <a name="private-destructors-and-stdisconstructible"></a>Özel yok ediciler ve std::is_constructible
Bir yıkıcı sonucu karar verirken özel olup olmadığını göz ardı Derleyici önceki sürümlerini [std::is_constructible](standard-library/is-constructible-class.md). Artık bunları değerlendirir. Aşağıdaki örnekte, Visual Studio'nun önceki sürümleri geçişinde statik onaylar ancak Visual Studio 2017 sürüm 15.3 başarısız:

```cpp
#include <type_traits>
 
class PrivateDtor {
   PrivateDtor(int) { }
private:
   ~PrivateDtor() { }
};
 
// This assertion used to succeed. It now correctly fails.
static_assert(std::is_constructible<PrivateDtor, int>::value);
```  

Özel Yıkıcılar oluşturulabilir olmayan olması için bir türü neden. **Std::is_constructible < T, bağımsız değişken... >** aşağıdaki bildirimi yazılmışsa gibi hesaplanır:
```cpp 
   T obj(std::declval<Args>()…)
``` 
Bu çağrı bir yıkıcı çağrı anlamına gelir.

### <a name="c2668-ambiguous-overload-resolution"></a>C2668: Belirsiz aşırı yükleme çözümü
Derleyici önceki sürümlerini bazen başarısız her ikisi de aracılığıyla birden çok adayları bulduğunuz sırada belirsizlik algılamak bildirimler ve değişken bağımlı arama kullanma. Bu yanlış aşırı seçilmekte ve beklenmeyen çalışma zamanı davranışını neden olabilir. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15.3 doğru C2668 'f' başlatır: aşırı yüklenmiş işlevi çağrısı belirsiz:

```cpp
namespace N {
   template<class T>
   void f(T&, T&);
 
   template<class T>
   void f();
}
 
template<class T>
void f(T&, T&);
 
struct S {};
void f()
{
   using N::f; 
 
   S s1, s2;
   f(s1, s2); // C2668
}
```
Kullanarak kodu düzeltmek için kaldırma çağrısı amaçlıyorsanız N::f deyimi:: f().

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: yerel işlev bildirimleri ve bağımsız değişkeni bağımlı arama
Yerel işlev bildirimleri çevreleyen kapsamdaki işlevi bildiriminde gizleyebilir ve bağımsız değişkeni bağımlı arama devre dışı bırakın.
Ancak, Visual C++ derleyicisi önceki sürümlerini bağımsız değişkeni bağımlı arama bu durumda, büyük olasılıkla yanlış baştaki aşırı seçilmekte ve beklenmeyen çalışma zamanı davranışı gerçekleştirilir. Genellikle, bir yerel işlev bildirimi hatalı imza nedeniyle hatasıdır. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15.3 doğru C2660 'f' başlatır: işlevi 2 bağımsız değişkenleri olmaz:

```cpp
struct S {}; 
void f(S, int);
 
void g()
{
   void f(S); // C2660 'f': function does not take 2 arguments:
   // or void f(S, int);
   S s;
   f(s, 0);
}
```

Sorunu düzeltmek için ya da değiştirme **f (S)** imza veya kaldırın.

### <a name="c5038-order-of-initialization-in-initializer-lists"></a>C5038: Başlatıcı Listeleri başlatma sırasını
Sınıf üyeleri bildirilir, sırayla değil Başlatıcı Listeleri göründükleri sırada başlatılır. Bildirim sıra başlatıcı listesi sırasını farklıydı geçtiğinde Derleyici önceki sürümlerini uyar değil. Başka bir üye zaten başlatılmış listesinde bir üye başlatma bağımlı varsa bu tanımsız çalışma zamanı davranışı neden olabilir. Aşağıdaki örnekte, Visual Studio 2017 sürüm 15.3 (ile wln) uyarı C5038 başlatır: 'A::y' veri üyesi 'A::x' sonra başlatılacaktır veri üyesi:

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};

```
Sorunu düzeltmek için bildirimler aynı sırada olmasını ıntializer listesini düzenleyin. Bir veya iki başlatıcıları taban sınıf üyelerine başvurduğunuzda benzer bir uyarı oluşturulur.

Uyarı-varsayılan olarak kapalı olduğunu ve yalnızca wln ile derlenmiş kod etkiler unutmayın.

## <a name="update_155"></a>Hata düzeltmeleri ve diğer Visual Studio 2017 sürüm 15,5 davranış değişiklikleri
### <a name="partial-ordering-change"></a>Kısmi sıralama Değiştir

Derleyici artık doğru aşağıdaki kodu reddeder ve doğru hata iletisi verir:

```cpp

template<typename... T>
int f(T* ...)
{
    return 1;
}

template<typename T>
int f(const T&)
{
    return 2;
}

int main()
{
    int i = 0;
    f(&i);    // C2668
}
```
```output
t161.cpp
t161.cpp(16): error C2668: 'f': ambiguous call to overloaded function
t161.cpp(8): note: could be 'int f<int*>(const T &)'
        with
        [
            T=int*
        ]
t161.cpp(2): note: or       'int f<int>(int*)'
t161.cpp(16): note: while trying to match the argument list '(int*)'
``` 
Yukarıdaki örnekte türleri iki farklılıklar vardır bir sorundur (const const olmayan karşılaştırması ve paketi olmayan ve paketi). Derleyici Hatası ortadan kaldırmak için farklar birini kaldırın. Bu işlevler belirsizliğe sıralamak derleyici sağlar.

```cpp
template<typename... T>
int f(T* ...)
{
    return 1;
}

template<typename T>
int f(T&)
{
    return 2;
}

int main()
{
    int i = 0;
    f(&i);
}
```


### <a name="exception-handlers"></a>Özel durum işleyicileri
Dizi ya da işlevi türü referansı işleyicileri hiçbir zaman herhangi bir özel durum nesnesi için bir eşleşme var. Derleyici artık doğru şekilde bu kural geliştirir ve düzey 4 uyarı başlatır. Ayrıca artık bir işleyiciyi eşleşecek `char*` veya `wchar_t*` dize değişmez değer olduğunda **/ZC: strictstrings** kullanılır.

```cpp
int main()
{
    try {
        throw "";
    }
    catch (int (&)[1]) {} // C4843 (This should always be dead code.)
    catch (void (&)()) {} // C4843 (This should always be dead code.)
    catch (char*) {} // This should not be a match under /Zc:strictStrings
}
```

```output
warning C4843: 'int (&)[1]': An exception handler of reference to array or function type is unreachable, use 'int*' instead
warning C4843: 'void (__cdecl &)(void)': An exception handler of reference to array or function type is unreachable, use 'void (__cdecl*)(void)' instead
```
Aşağıdaki kod hata ortadan kaldırır:

```cpp
catch (int (*)[1]) {}
```

### <a name="tr1"></a>Std::tr1 namespace kullanım dışıdır
Standart olmayan std::tr1 namespace, şimdi C ++ 14 ve C ++ 17 modları içinde kullanım dışı olarak işaretlenir. Visual Studio 2017 içinde sürüm 15,5, aşağıdaki kodu C4996 başlatır:

```cpp
#include <functional>
#include <iostream>
using namespace std;

int main() {
    std::tr1::function<int (int, int)> f = std::plus<int>(); //C4996
    cout << f(3, 5) << std::endl;
    f = std::multiplies<int>();
    cout << f(3, 5) << std::endl;
}
```

```output
warning C4996: 'std::tr1': warning STL4002: The non-Standard std::tr1 namespace and TR1-only machinery are deprecated and will be REMOVED. You can define _SILENCE_TR1_NAMESPACE_DEPRECATION_WARNING to acknowledge that you have received this warning.
```

Hatayı düzeltmek için tr1 ad alanı başvurusunu kaldırın:

```cpp
#include <functional>
#include <iostream>
using namespace std;

int main() {
    std::function<int (int, int)> f = std::plus<int>();
    cout << f(3, 5) << std::endl;
    f = std::multiplies<int>();
    cout << f(3, 5) << std::endl;
}
```


### <a name="annex_d"></a>Eki D standart kitaplığı özellikleri kullanım dışı olarak işaretlenir.
Zaman / Std: c ++ 17 modu derleyici anahtar olarak ayarlanmışsa, eki d neredeyse tüm standart kitaplığı özellikleri kullanım dışı olarak işaretlenir.

Visual Studio 2017 içinde sürüm 15,5, aşağıdaki kodu C4996 başlatır:

```cpp
#include <iterator>

class MyIter : public std::iterator<std::random_access_iterator_tag, int> {
public:
    // ... other members ...
};

#include <type_traits>

static_assert(std::is_same<MyIter::pointer, int*>::value, "BOOM");
```

```output
warning C4996: 'std::iterator<std::random_access_iterator_tag,int,ptrdiff_t,_Ty*,_Ty &>::pointer': warning STL4015: The std::iterator class template (used as a base class to provide typedefs) is deprecated in C++17. (The <iterator> header is NOT deprecated.) The C++ Standard has never required user-defined iterators to derive from std::iterator. To fix this warning, stop deriving from std::iterator and start providing publicly accessible typedefs named iterator_category, value_type, difference_type, pointer, and reference. Note that value_type is required to be non-const, even for constant iterators. You can define _SILENCE_CXX17_ITERATOR_BASE_CLASS_DEPRECATION_WARNING or _SILENCE_ALL_CXX17_DEPRECATION_WARNINGS to acknowledge that you have received this warning.
```

Hatayı düzeltmek için aşağıdaki kodda gösterildiği gibi uyarı metni'ndaki yönergeleri izleyin:

```cpp
#include <iterator>

class MyIter {
public:
    typedef std::random_access_iterator_tag iterator_category;
    typedef int value_type;
    typedef ptrdiff_t difference_type;
    typedef int* pointer;
    typedef int& reference;

    // ... other members ...
};

#include <type_traits>

static_assert(std::is_same<MyIter::pointer, int*>::value, "BOOM");
```

### <a name="unreferenced-local-variables"></a>Başvurulmayan yerel değişkenler
Visual Studio 15,5 içinde uyarı C4189 aşağıdaki kodda gösterildiği gibi daha fazla durumlarda yayılır:

```cpp
void f() {
    char s[2] = {0}; // C4189. Either use the variable or remove it.
}

```

```output
warning C4189: 's': local variable is initialized but not referenced
```

Hatayı düzeltmek için kullanılmayan değişkeni kaldırın.

### <a name="single-line-comments"></a>Tek satırlı açıklamaları 
Visual Studio 2017 içinde sürüm 15,5, uyarılar C4001 ve C4179 artık C derleyicisi tarafından gösterilen. Daha önce bunlar yalnızca altında gösterilen **/Za** derleyici anahtar.  Tek satırlı yorumlar itibaren C99 standart C parçası bırakıldığından uyarıları artık gerekli değildir. 

```cpp
/* C only */
#pragma warning(disable:4001) //C4619
#pragma warning(disable:4179)
// single line comment
//* single line comment */
```

```output
warning C4619: #pragma warning: there is no warning number '4001'   
```

Kod geriye dönük olarak uyumlu olması gerekmez, C4001/C4179 gizleme kaldırarak uyarı önleyebilirsiniz. Kod geriye dönük uyumluluk gerekiyorsa, C4619 yalnızca engelleyin.

```cpp
/* C only */

#pragma warning(disable:4619)
#pragma warning(disable:4001)
#pragma warning(disable:4179)

// single line comment
/* single line comment */
```


### <a name="declspec-attributes-with-extern-c-linkage"></a>extern "C" bağlantı __declspec özniteliklerle 

Visual Studio'nun önceki sürümleri derleyici göz ardı `__declspec(…)` ne zaman öznitelikleri `__declspec(…)` önce uygulandı `extern "C"` bağlantı belirtimi. Kod neden bu davranış, oluşturulan kullanıcı kaydetmedi düşünüyorsanız, olası çalışma zamanı uygulamaları ile. Uyarı Visual Studio sürüm 15.3 eklendi, ancak varsayılan olarak kapalı olan. Visual Studio 2017 içinde sürüm 15,5, uyarı varsayılan olarak etkindir.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

```output
warning C4768: __declspec attributes before linkage specification are ignored
```

Hatayı düzeltmek için __declspec özniteliği önce bağlantı belirtimi koyun:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```
Bu yeni uyarı C4768 ile Visual Studio 2017 15.3 geldiği bazı Windows SDK'sı üst bilgileri verilen ya da eski olur (örneğin: sürüm 10.0.15063.0, RS2 SDK olarak da bilinir). Ancak, böylece bu uyarıyı üreten değil Windows SDK üst bilgilerinin (özellikle, ShlObj.h ve ShlObj_core.h) sonraki sürümlerinde düzeltildi. Windows SDK üstbilgileri yakında bu uyarıyı gördüğünüzde, bu eylemleri gerçekleştirebilirsiniz:
1)  Visual Studio 2017 15,5 sürüm ile birlikte gelen en son Windows SDK geçin.
2)  Geçici uyarıyı Kapat # Windows SDK üstbilgi deyiminin include:
```cpp
#pragma warning (push) 
#pragma warning(disable:4768)
#include <shlobj.h>
#pragma warning (pop) 
```

### <a name="extern_linkage"></a>Extern constexpr bağlantı 

Visual Studio'nun önceki sürümleri derleyici her zaman vermiş bir `constexpr` değişkeni bile işaretlendi, değişken iç bağlantı `extern`. Visual Studio 2017 sürüm 15,5, yeni derleyici anahtar içinde (/ Zc:externConstexpr) doğru standartları uyumsuz davranışı etkinleştirir. Sonuç olarak bu varsayılan olur.

```cpp
extern constexpr int x = 10; 
```

```output
error LNK2005: "int const x" already defined
```

Üstbilgi dosyası bildirilen bir değişken içeriyorsa `extern constexpr`, işaretlenmesi gerekir `__declspec(selectany)` birlikte, yinelenen bildirimler doğru olması için:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

### <a name="typeid-cant-be-used-on-incomplete-class-type"></a>TypeId tamamlanmamış sınıfı türünde kullanılamaz.
Visual Studio'nun önceki sürümleri derleyici aşağıdaki kod, büyük olasılıkla yanlış türde bilgileri kaynaklanan yanlış izin. Visual Studio 2017 içinde sürüm 15,5, derleyici, doğru bir hata oluşturur:

```cpp
#include <typeinfo>

struct S;

void f() { typeid(S); } //C2027 in 15.5
```

```output
error C2027: use of undefined type 'S'
```


### <a name="stdisconvertible-target-type"></a>Std::is_convertible hedef türü

`std::is_convertible`Hedef türü geçerli bir dönüş türü olmasını gerektirir. Visual Studio'nun önceki sürümleri derleyici yanlış yanlış aşırı yükleme çözümü ve istenmeyen çalışma zamanı davranışını yol açabilecek soyut türler izin verilir.  Aşağıdaki kod artık doğru C2338 başlatır:

```cpp
#include <type_traits>
 
struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };
 
static_assert(std::is_convertible<D, B>::value, "fail"); // C2338 in 15.5

```
Kullanırken hatayı önlemek için `is_convertible` soyut bir tür ise bir işaretçi türü karşılaştırma işlemi başarısız olduğundan işaretçi türleri karşılaştırmanız gerekir:

```cpp
#include <type_traits>
 
struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };
 
static_assert(std::is_convertible<D *, B *>::value, "fail");

```
### <a name="noexcept_removal"></a>Dinamik özel durum belirtimi kaldırma ve noexcept
C ++ 17 ' de `throw()` için diğer ad olduğu `noexcept`, `throw(<type list>)` ve `throw(…)` kaldırılır ve belirli türleri içerebilir `noexcept`. Bu C ++ 14 veya önceki sürümleri uyumlu koduyla kaynak uyumluluk sorunlarına neden olabilir. **/Zc:noexceptTypes-** anahtar, C ++ 14 sürümüne geri dönmek için kullanılabilir `noexcept` genel C ++ 17 modu kullanırken. Bu, C ++ 17'ye tüm yeniden yazmaya gerek kalmadan uygun olması için kaynak kodu güncelleştirmenizi sağlar, `throw()` aynı anda kodu.

Derleyici de artık daha fazla eşleşmeyen özel durum belirtimleri bildirimlerden C ++ 17 modunda veya ile tanılar **/ izin veren-** C5043 yeni uyarı.

Aşağıdaki kod C5043 ve C5040 Visual Studio 2017 sürüm 15,5 oluşturur, / Std: c ++ 17 anahtar uygulanır:

```cpp
void f() throw(); // equivalent to void f() noexcept;
void f() {} // warning C5043
void g() throw(); // warning C5040

struct A {
    virtual void f() throw();
};

struct B : A {
    virtual void f() { } // error C2694
};
```
Hala kullanırken hataları kaldırmak için **/Std: c ++ 17**, ekleyip ya da **/Zc:noexceptTypes-** geçiş için komut satırını, aksi takdirde kullanmak için kodunuzu güncelleştirin `noexcept`, aşağıdaki örnekte gösterildiği gibi:

```cpp
void f() noexcept;
void f() noexcept { }
void g() noexcept(false);

struct A {
    virtual void f() noexcept;
};

struct B : A {
    virtual void f() noexcept { }
};
```
### <a name="inline-variables"></a>Satır içi değişkenleri
Statik constexpr veri üyeleri kendi bildirimi bir sınıf içinde artık kendi tanımı anlamına gelir satır içi örtük olarak sunulmuştur. Statik constexpr veri üyesi için bir satır sonu tanımı kullanılarak yedekli ve artık kullanım dışı. Visual Studio 2017 sürüm 15,5 içinde olduğunda / Std: c ++ 17 anahtar uygulandığında, aşağıdaki kod artık uyarı C5041 üreten *'boyutu': satır dışı tanım constexpr statik veri üyesi için gerekli değildir ve C ++ 17'de kullanım dışı*:

```cpp
struct X {
    static constexpr int size = 3;
};
const int X::size; // C5041
```
### <a name="extern-c-declspec-warning-c4768-now-on-by-default"></a>extern "C" __declspec(...) C4768 şimdi üzerinde varsayılan olarak uyarı
Uyarı, Visual Studio 2017 sürüm 15.3 eklendi ancak varsayılan olarak kapalı olan. Visual Studio 2017 sürüm 15,5 varsayılan olarak açıktır. Bkz: [declspec özniteliklerinde yeni uyarı](#declspec) daha fazla bilgi için.

### <a name="defaulted-functions-and-declspecnothrow"></a>Varsayılan işlevler ve __declspec(nothrow)
Derleyici önceden ile bildirilmesi varsayılan işlevleri izin verilen `__declspec(nothrow)` karşılık gelen taban/üye işlevleri özel durumlara ne zaman izin verilir. Bu davranış C++ Standart aykırı ve çalışma zamanında tanımsız davranış neden olabilir. Standart bir özel durum belirtimi uyuşmazlığı ise silindi olarak tanımlanması için bu tür işlevler gerektirir.  Altında/Std: c ++ 17, aşağıdaki kod başlatır C2280 *silinen işlevi başvuru girişimi. Açık özel durum belirtimi, örtük bildirimi ile uyumlu olmadığı için işlevi örtük olarak silindi.* :


```cpp
struct A {
    A& operator=(const A& other) { // No exception specification; this function may throw.
        ...
    }
};

struct B : public A {
    __declspec(nothrow) B& operator=(const B& other) = default;
};

int main()
{
    B b1, b2;
    b2 = b1; // error C2280
}
```

Bu kod düzeltmek için varsayılan işlevinden __declspec(nothrow) kaldırın ya da kaldırma `= default` ve tüm gerekli özel durum işleme birlikte işlevi için bir tanım girin:

```cpp
struct A {
    A& operator=(const A& other) {
        ...
    }
};

struct B : public A {
    B& operator=(const B& other) = default;
};

int main()
{
    B b1, b2;
    b2 = b1;
}
```
### <a name="noexcept-and-partial-specializations"></a>noexcept ve kısmi özelleştirmeleri
Türü sistemindeki noexcept ile eşleşen belirli "aranabilir" türleri için kısmi özelleştirmeleri derleme veya İşlevler noexcept işaretçileri için eksik bir kısmi uzmanlığı nedeniyle birincil şablon seçmek başarısız olabilir.

Böyle durumlarda, noexcept işlev işaretçileri ve üye işlevleri noexcept işaretçileri işlemek için ek kısmi özelleştirmeleri eklemeniz gerekebilir. Bu aşırı yalnızca yasal / Std: c ++ 17 modu. Geriye dönük uyumluluk C ++ 14 ile tutulan gerekir ve diğerleri tüketir kod yazma olduğunuz durumunda bu yeni aşırı içinde koruması `#ifdef` yönergeleri. Kendi içinde bulunan modülü ve ardından kullanmak yerine çalışıyorsanız `#ifdef` yalnızca derleyebileceğiniz ile koruyucuları **/Zc:noexceptTypes-** geçin. 

/ Std: c altında aşağıdaki kodu derler ++ 14 ancak başarısız altında/Std: c ++ 17 C2027 hatasıyla:*tanımsız türünü kullanın ' A<T>'*:

```cpp
template <typename T> struct A;

template <>
struct A<void(*)()>
{
    static const bool value = true;
};

template <typename T>
bool g(T t)
{
    return A<T>::value;
}

void f() noexcept {}

int main()
{
    return g(&f) ? 0 : 1; // C2027
}
```

Aşağıdaki kod başarılı altında/Std: c ++ 17 derleyici yeni kısmi uzmanlığı seçtiği için `A<void (*)() noexcept>`:

```cpp
template <typename T> struct A;

template <>
struct A<void(*)()>
{
    static const bool value = true;
};

template <>
struct A<void(*)() noexcept>
{
    static const bool value = true;
};

template <typename T>
bool g(T t)
{
    return A<T>::value;
}

void f() noexcept {}

int main()
{
    return g(&f) ? 0 : 1; // OK
}
```

## <a name="see-also"></a>Ayrıca Bkz.  
[Visual C++ Dil Uyumluluğu](visual-cpp-language-conformance.md)  
