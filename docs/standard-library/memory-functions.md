---
description: 'Daha fazla bilgi edinin: &lt; bellek &gt; işlevleri'
title: '&lt;bellek &gt; işlevleri'
ms.date: 08/05/2019
f1_keywords:
- memory/std::addressof
- memory/std::align
- memory/std::allocate_shared
- memory/std::const_pointer_cast
- memory/std::declare_no_pointers
- memory/std::declare_reachable
- memory/std::dynamic_pointer_cast
- memory/std::get_deleter
- memory/std::get_pointer_safety
- memory/std::get_temporary_buffer
- xmemory/std::get_temporary_buffer
- memory/std::make_shared
- memory/std::make_unique
- memory/std::owner_less
- memory/std::reinterpret_pointer_cast
- memory/std::return_temporary_buffer
- xmemory/std::return_temporary_buffer
- memory/std::static_pointer_cast
- memory/std::swap
- memory/std::undeclare_no_pointers
- memory/std::undeclare_reachable
- memory/std::uninitialized_copy
- memory/std::uninitialized_copy_n
- memory/std::uninitialized_fill
- memory/std::uninitialized_fill_n
ms.assetid: 3e1898c2-44b7-4626-87ce-84962e4c6f1a
helpviewer_keywords:
- std::addressof [C++]
- std::align [C++]
- std::allocate_shared [C++]
- std::const_pointer_cast [C++]
- std::declare_no_pointers [C++]
- std::declare_reachable [C++]
- std::default_delete [C++]
- std::dynamic_pointer_cast [C++]
- std::get_deleter [C++]
- std::get_pointer_safety [C++]
- std::get_temporary_buffer [C++]
- std::make_shared [C++]
- std::make_unique [C++]
- std::owner_less [C++]
- std::return_temporary_buffer [C++]
- std::static_pointer_cast [C++]
- std::swap [C++]
- std::undeclare_no_pointers [C++]
- std::undeclare_reachable [C++]
- std::uninitialized_copy [C++]
- std::uninitialized_copy_n [C++]
- std::uninitialized_fill [C++]
- std::uninitialized_fill_n [C++]
- std::addressof [C++]
- std::align [C++]
- std::allocate_shared [C++]
- std::const_pointer_cast [C++]
- std::declare_no_pointers [C++]
- std::declare_reachable [C++]
- std::default_delete [C++]
- std::dynamic_pointer_cast [C++]
- std::get_deleter [C++]
- std::get_pointer_safety [C++]
- std::get_temporary_buffer [C++]
- std::make_shared [C++]
- std::make_unique [C++]
- std::owner_less [C++]
- std::return_temporary_buffer [C++]
- std::static_pointer_cast [C++]
- std::undeclare_no_pointers [C++]
- std::undeclare_reachable [C++]
- std::uninitialized_copy [C++]
- std::uninitialized_copy_n [C++]
- std::uninitialized_fill [C++]
- std::uninitialized_fill_n [C++]
ms.openlocfilehash: 13c18ce754a3e88d7ad2ae47ead522bc21cec718
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183977"
---
# <a name="ltmemorygt-functions"></a>&lt;bellek &gt; işlevleri

## <a name="addressof"></a><a name="addressof"></a> AddressOf

Bir nesnenin doğru adresini alır.

```cpp
template <class T>
T* addressof(
    T& value) noexcept;    // before C++17

template <class T>
constexpr T* addressof(
    T& value) noexcept;    // C++17

template <class T>
const T* addressof(
    const T&& value) = delete;   // C++17
```

### <a name="parameters"></a>Parametreler

*deeri*\
Doğru adresi alacak nesne veya işlev.

### <a name="return-value"></a>Dönüş Değeri

Aşırı yüklenmiş olsa bile, *değer* tarafından başvurulan nesnenin veya işlevin gerçek adresi `operator&()` .

### <a name="remarks"></a>Açıklamalar

## <a name="align"></a><a name="align"></a> acaktır

Verilen boyutun depolamasına, belirtilen hizalama belirtimine göre, verilen depolamanın ilk olası adresine uyar.

```cpp
void* align(
    size_t alignment, // input
    size_t size,      // input
    void*& ptr,       // input/output
    size_t& space     // input/output
);
```

### <a name="parameters"></a>Parametreler

*hizalar*\
Denenecek hizalama sınırı.

*boyutla*\
Hizalanmış depolama için bayt cinsinden boyut.

*kaydetmeye*\
Kullanılacak mevut bitişik depolama havuzunun başlangıç adresi. Bu parametre aynı zamanda bir çıktı parametresidir ve hizalama başarılı olursa yeni başlangıç adresini içerecek şekilde ayarlanır. `align()`Başarısız olursa, bu parametre değiştirilmez.

*boşlu*\
`align()`Hizalanmış depolamayı oluştururken kullanılabilecek Toplam alan. Bu parametre aynı zamanda bir çıktı parametresidir ve hizalanmış depolamanın ve herhangi ilişkili ek yükün çıkarılmasının ardından depolama arabelleğinde kalan düzenlenmiş alanı içerir.

`align()`Başarısız olursa, bu parametre değiştirilmez.

### <a name="return-value"></a>Dönüş Değeri

İstenen hizalanmış arabelleğin kullanılabilir alana sığmadığı durumlarda boş bir işaretçi; Aksi halde, yeni *PTR* değeri.

### <a name="remarks"></a>Açıklamalar

Değiştirilen *PTR* ve *Space* parametreleri, `align()` büyük olasılıkla *Hizalama* ve *Boyut* için farklı değerlerle aynı arabellekte sürekli olarak çağrı etkinleştirmenizi sağlar. Aşağıdaki kod parçacığı bir kullanımını gösterir `align()` .

```cpp
#include <type_traits> // std::alignment_of()
#include <memory>
//...
char buffer[256]; // for simplicity
size_t alignment = std::alignment_of<int>::value;
void * ptr = buffer;
std::size_t space = sizeof(buffer); // Be sure this results in the true size of your buffer

while (std::align(alignment, sizeof(MyObj), ptr, space)) {
    // You now have storage the size of MyObj, starting at ptr, aligned on
    // int boundary. Use it here if you like, or save off the starting address
    // contained in ptr for later use.
    // ...
    // Last, move starting pointer and decrease available space before
    // the while loop restarts.
    ptr = reinterpret_cast<char*>(ptr) + sizeof(MyObj);
    space -= sizeof(MyObj);
}
// At this point, align() has returned a null pointer, signaling it is not
// possible to allow more aligned storage in this buffer.
```

## <a name="allocate_shared"></a><a name="allocate_shared"></a> allocate_shared

Belirtilen ayırıcı kullanılarak belirli bir tür için ayrılan ve oluşturulan nesnelere bir [shared_ptr](shared-ptr-class.md) oluşturur. Döndürür `shared_ptr` .

```cpp
template <class T, class Allocator, class... Args>
shared_ptr<T> allocate_shared(
    Allocator alloc,
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

*tahsis*\
Nesneleri oluşturmak için kullanılan ayırıcı.

*args*\
Nesneler haline gelen sıfır veya daha fazla bağımsız değişken.

### <a name="remarks"></a>Açıklamalar

İşlevi `shared_ptr<T>` , `T(args...)` ayrılan ve *ayırma* tarafından oluşturulan bir işaretçi olan nesnesini oluşturur.

## <a name="atomic_compare_exchange_strong"></a><a name="atomic_compare_exchange_strong"></a> atomic_compare_exchange_strong

```cpp
template<class T>
bool atomic_compare_exchange_strong(
    shared_ptr<T>* u,
    shared_ptr<T>* v,
    shared_ptr<T> w);
```

## <a name="atomic_compare_exchange_weak"></a><a name="atomic_compare_exchange_weak"></a> atomic_compare_exchange_weak

```cpp
template<class T>
bool atomic_compare_exchange_weak(
    shared_ptr<T>* u,
    shared_ptr<T>* v,
    shared_ptr<T> w);
```

## <a name="atomic_compare_exchange_strong_explicit"></a><a name="atomic_compare_exchange_strong_explicit"></a> atomic_compare_exchange_strong_explicit

```cpp
template<class T>
bool atomic_compare_exchange_strong_explicit(
    shared_ptr<T>* u,
    shared_ptr<T>* v,
    shared_ptr<T> w,
    memory_order success,
    memory_order failure);
```

## <a name="atomic_compare_exchange_weak_explicit"></a><a name="atomic_compare_exchange_weak_explicit"></a> atomic_compare_exchange_weak_explicit

```cpp
template<class T>
bool atomic_compare_exchange_weak_explicit(
    shared_ptr<T>* u,
    shared_ptr<T>* v,
    shared_ptr<T> w,
    memory_order success,
    memory_order failure);
```

## <a name="atomic_exchange"></a><a name="atomic_exchange"></a> atomic_exchange

```cpp
template<class T>
shared_ptr<T> atomic_exchange(
    shared_ptr<T>* u,
    shared_ptr<T> r);
```

## <a name="atomic_exchange_explicit"></a><a name="atomic_exchange_explicit"></a> atomic_exchange_explicit

```cpp
template<class T>
shared_ptr<T> atomic_exchange_explicit(
    shared_ptr<T>* u,
    shared_ptr<T> r,
    memory_order mo);
```

## <a name="atomic_is_lock_free"></a><a name="atomic_is_lock_free"></a> atomic_is_lock_free

```cpp
template<class T>
bool atomic_is_lock_free(
    const shared_ptr<T>* u);
```

## <a name="atomic_load"></a><a name="atomic_load"></a> atomic_load

```cpp
template<class T>
shared_ptr<T> atomic_load(
    const shared_ptr<T>* u);
```

## <a name="atomic_load_explicit"></a><a name="atomic_load_explicit"></a> atomic_load_explicit

```cpp
template<class T>
shared_ptr<T> atomic_load_explicit(
    const shared_ptr<T>* u,
    memory_order mo);
```

## <a name="atomic_store"></a><a name="atomic_store"></a> atomic_store

```cpp
template<class T>
void atomic_store(
    shared_ptr<T>* u,
    shared_ptr<T> r);
```

## <a name="atomic_store_explicit"></a><a name="atomic_store_explicit"></a> atomic_store_explicit

```cpp
template<class T>
void atomic_store_explicit(
    shared_ptr<T>* u,
    shared_ptr<T> r,
    memory_order mo);
```

## <a name="const_pointer_cast"></a><a name="const_pointer_cast"></a> const_pointer_cast

[Shared_ptr](shared-ptr-class.md)için const cast.

```cpp
template <class T, class Other>
shared_ptr<T> const_pointer_cast(
    const shared_ptr<Other>& sp) noexcept;

template <class T, class Other>
shared_ptr<T> const_pointer_cast(
    shared_ptr<Other>&& sp) noexcept;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Döndürülen paylaşılan işaretçi tarafından denetlenen tür.

*Farklı*\
Bağımsız değişken paylaşılan işaretçisi tarafından denetlenen tür.

*SP2*\
Bağımsız değişken paylaşılan işaretçisi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `shared_ptr` `const_cast<T*>(sp.get())` null bir işaretçi döndürürse boş bir nesne döndürür; Aksi takdirde `shared_ptr<T>` , *SP*'nin sahip olduğu kaynağa sahip bir nesne döndürür. İfade `const_cast<T*>(sp.get())` geçerli olmalıdır.

### <a name="example"></a>Örnek

```cpp
// std__memory__const_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int);
    std::shared_ptr<const int> sp1 =
        std::const_pointer_cast<const int>(sp0);

    *sp0 = 3;
    std::cout << "sp1 == " << *sp1 << std::endl;

    return (0);
}
```

```Output
sp1 == 3
```

## <a name="declare_no_pointers"></a><a name="declare_no_pointers"></a> declare_no_pointers

Bir temel adres işaretçisi ve blok boyutu tarafından tanımlanan bellek bloğundaki karakterlerin izlenebilen işaretçiler içermediğini belirten bir atık toplayıcıya bildirir.

```cpp
void declare_no_pointers(
    char* ptr,
    size_t size);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Artık izlenebilecek işaretçiler içermeyen ilk karakterin adresi.

*boyutla*\
İzlenebilen işaretçiler içermeyen *PTR* 'de başlayan bloğun boyutu.

### <a name="remarks"></a>Açıklamalar

İşlevi, aralıktaki adreslerin `[ ptr, ptr + size)` artık izlenebilecek işaretçiler içermediği tüm çöp toplayıcıyı bilgilendirir. (Ayrılan depolamaya yönelik işaretçilere, erişilebilir olmadığı müddetçe başvurulmamalıdır.)

## <a name="declare_reachable"></a><a name="declare_reachable"></a> declare_reachable

Belirtilen adresin ayrılmış depolama alanını ve erişilebilir olduğunu atık toplamaya bildirir.

```cpp
void declare_reachable(
    void* ptr);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Erişilebilir, ayrılmış, geçerli bir depolama alanına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

*PTR* null değilse, işlev, *PTR* 'nin artık ulaşılabilir olduğunu, yani geçerli ayrılmış depolamayı işaret ettiğini bildiren tüm çöp toplayıcıyı bilgilendirir.

## <a name="default_delete"></a><a name="default_delete"></a> default_delete

**New işleciyle** ayrılan nesneleri siler. [Unique_ptr](unique-ptr-class.md)ile kullanım için uygun.

```cpp
struct default_delete
{
    constexpr default_delete() noexcept = default;

    template <class Other, class = typename enable_if<is_convertible<Other*, T*>::value, void>::type>>
    default_delete(const default_delete<Other>&) noexcept;

    void operator()(T* ptr) const noexcept;
};
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Silinecek nesnenin işaretçisi.

*Farklı*\
Silinecek dizideki öğelerin türü.

### <a name="remarks"></a>Açıklamalar

Sınıf şablonu, **New işleci** ile ayrılmış skaler nesneleri silen ve sınıf şablonuyla kullanım için uygun olan bir silici tanımlar `unique_ptr` . Ayrıca, açık özelleşmeye de sahiptir `default_delete<T[]>` .

## <a name="destroy_at"></a><a name="destroy_at"></a> destroy_at

```cpp
template <class T>
void destroy_at(
    T* location);
```

Aynı `location->~T()` .

## <a name="destroy"></a><a name="destroy"></a> kaldırılır

```cpp
template <class ForwardIterator>
void destroy(
    ForwardIterator first,
    ForwardIterator last);
```

Aynı:

```cpp
for (; first != last; ++first)
    destroy_at(addressof(*first));
```

## <a name="destroy_n"></a><a name="destroy_n"></a> destroy_n

```cpp
template <class ForwardIterator, class Size>
ForwardIterator destroy_n(
    ForwardIterator first,
    Size count);
```

Aynı:

```cpp
for (; count > 0; (void)++first, --count)
    destroy_at(addressof(*first));
return first;
```

## <a name="dynamic_pointer_cast"></a><a name="dynamic_pointer_cast"></a> dynamic_pointer_cast

[Shared_ptr](shared-ptr-class.md)için dinamik atama.

```cpp
template <class T, class Other>
shared_ptr<T> dynamic_pointer_cast(
    const shared_ptr<Other>& sp) noexcept;

template <class T, class Other>
shared_ptr<T> dynamic_pointer_cast(
    shared_ptr<Other>&& sp) noexcept;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Döndürülen paylaşılan işaretçi tarafından denetlenen tür.

*Farklı*\
Bağımsız değişken paylaşılan işaretçisi tarafından denetlenen tür.

*SP2*\
Bağımsız değişken paylaşılan işaretçisi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `shared_ptr` `dynamic_cast<T*>(sp.get())` null bir işaretçi döndürürse boş bir nesne döndürür; Aksi takdirde `shared_ptr<T>` , *SP*'nin sahip olduğu kaynağa sahip bir nesne döndürür. İfade `dynamic_cast<T*>(sp.get())` geçerli olmalıdır.

### <a name="example"></a>Örnek

```cpp
// std__memory__dynamic_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    virtual ~base() {}
    int value;
};

struct derived
    : public base
{
};

int main()
{
    std::shared_ptr<base> sp0(new derived);
    std::shared_ptr<derived> sp1 =
        std::dynamic_pointer_cast<derived>(sp0);

    sp0->value = 3;
    std::cout << "sp1->value == " << sp1->value << std::endl;

    return (0);
}
```

```Output
sp1->value == 3
```

## <a name="get_deleter"></a><a name="get_deleter"></a> get_deleter

[Shared_ptr](shared-ptr-class.md)silici alın.

```cpp
template <class Deleter, class T>
Deleter* get_deleter(
    const shared_ptr<T>& sp) noexcept;
```

### <a name="parameters"></a>Parametreler

*Silici*\
Deleter türü.

*Şı*\
Paylaşılan işaretçi tarafından denetlenen tür.

*SP2*\
Paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, SP nesnesine ait olan tür *silici* için bir işaretçi döndürür `shared_ptr` .  *SP* 'nin hiç bir silici yoksa veya silici tür *silici* değilse, işlev 0 döndürür.

### <a name="example"></a>Örnek

```cpp
// std__memory__get_deleter.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    int value;
};

struct deleter
{
    void operator()(base *pb)
    {
        delete pb;
    }
};

int main()
{
    std::shared_ptr<base> sp0(new base);

    sp0->value = 3;
    std::cout << "get_deleter(sp0) != 0 == " << std::boolalpha
        << (std::get_deleter<deleter>(sp0) != 0) << std::endl;

    std::shared_ptr<base> sp1(new base, deleter());

    sp0->value = 3;
    std::cout << "get_deleter(sp1) != 0 == " << std::boolalpha
        << (std::get_deleter<deleter>(sp1) != 0) << std::endl;

    return (0);
}
```

```Output
get_deleter(sp0) != 0 == false
get_deleter(sp1) != 0 == true
```

## <a name="get_pointer_safety"></a><a name="get_pointer_safety"></a> get_pointer_safety

Herhangi bir atık toplayıcısı tarafından kabul edilen işaretçi güvenlik türünü döndürür.

```cpp
pointer_safety get_pointer_safety() noexcept;
```

### <a name="remarks"></a>Açıklamalar

İşlevi, herhangi bir otomatik çöp toplayıcı tarafından kabul edilen işaretçi güvenlik türünü döndürür.

## <a name="get_temporary_buffer"></a><a name="get_temporary_buffer"></a> get_temporary_buffer

Belirtilen sayıda öğeyi aşmayan öğe dizisi için geçici depolamayı ayırır.

```cpp
template <class T>
pair<T *, ptrdiff_t> get_temporary_buffer(
    ptrdiff_t count);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Ayrılan bellek için istenen en fazla öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

`pair`İlk bileşeni ayrılan belleğe yönelik bir işaretçidir ve ikinci bileşen, depolayabileceği en büyük öğe sayısını belirten arabelleğin boyutunu verir.

### <a name="remarks"></a>Açıklamalar

İşlev, bellek için bir istek yapar ve başarısız olabilir. Hiçbir arabellek ayrılıyorsa, işlev bir çift döndürür ve ikinci bileşen sıfıra eşit ve ilk bileşen null işaretçisine eşittir.

Bu işlevi yalnızca geçici bellek için kullanın.

### <a name="example"></a>Örnek

```cpp
// memory_get_temp_buf.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

int main( )
{
    // Create an array of ints
    int intArray [] = { 10, 20, 30, 40, 100, 200, 300, 1000, 2000 };
    int count = sizeof ( intArray ) / sizeof ( int );
    cout << "The number of integers in the array is: "
        << count << "." << endl;

    pair<int *, ptrdiff_t> resultPair;
    resultPair = get_temporary_buffer<int>( count );

    cout << "The number of elements that the allocated memory\n"
        << "could store is given by: resultPair.second = "
        << resultPair.second << "." << endl;
}
```

```Output
The number of integers in the array is: 9.
The number of elements that the allocated memory
could store is given by: resultPair.second = 9.
```

## <a name="make_shared"></a><a name="make_shared"></a> make_shared

Varsayılan ayırıcıyı kullanarak sıfır veya daha fazla bağımsız değişken tarafından oluşturulan ayrılmış nesneleri işaret eden bir [shared_ptr](shared-ptr-class.md) oluşturur ve döndürür. Nesnenin paylaşılan sahipliğini yönetmek için hem belirtilen türdeki hem de bir nesnesini ayırır ve oluşturur `shared_ptr` ve döndürür `shared_ptr` .

```cpp
template <class T, class... Args>
shared_ptr<T> make_shared(
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

*args*\
Sıfır veya daha fazla Oluşturucu bağımsız değişkeni. İşlevi, sunulan bağımsız değişkenlere dayanarak hangi Oluşturucu aşırı yüklemesinin çağrılmasını sağlar.

### <a name="remarks"></a>Açıklamalar

Bir `make_shared` nesne oluşturmak için basit ve daha verimli bir yol ve `shared_ptr` aynı zamanda nesneye paylaşılan erişimi yönetmek için kullanın. Anlamsal olarak, bu iki deyim eşdeğerdir:

```cpp
auto sp = std::shared_ptr<Example>(new Example(argument));
auto msp = std::make_shared<Example>(argument);
```

Ancak, ilk ifade iki ayırma yapar ve `shared_ptr` nesnenin ayrılması sonrasında başarısız olursa, `Example` adlandırılmamış `Example` nesne sızdırılmaz. Öğesinin kullanıldığı ifade, `make_shared` yalnızca bir işlev çağrısı olduğundan daha basittir. Kitaplık hem nesne hem de akıllı işaretçi için tek bir ayırma yapabildiğinden daha etkilidir. Bu işlev hem daha hızlıdır hem de daha az bellek parçalanması sağlar ve bir ayırma üzerinde bir özel durum değildir ancak diğeri değildir. Performans, nesneye başvuran kod için daha iyi konum tarafından geliştirilmiştir ve akıllı işaretçisindeki başvuru sayılarını günceller.

Nesneye paylaşılan erişim gerekmiyorsa [make_unique](memory-functions.md#make_unique) kullanmayı düşünün. Nesne için özel bir ayırıcı belirtmeniz gerekiyorsa [allocate_shared](memory-functions.md#allocate_shared) kullanın. `make_shared`Nesneniz bir bağımsız değişken olarak geçirmenin bir yolu olmadığından, nesneniz özel bir silici gerektiriyorsa kullanamazsınız.

Aşağıdaki örnek, belirli bir Oluşturucu aşırı yüklerini çağırarak bir tür için paylaşılan işaretçiler oluşturmayı gösterir.

### <a name="example"></a>Örnek

```cpp
// stl_make_shared.cpp
// Compile by using: cl /W4 /EHsc stl_make_shared.cpp
#include <iostream>
#include <string>
#include <memory>
#include <vector>

class Song {
public:
    std::wstring title_;
    std::wstring artist_;

    Song(std::wstring title, std::wstring artist) : title_(title), artist_(artist) {}
    Song(std::wstring title) : title_(title), artist_(L"Unknown") {}
};

void CreateSharedPointers()
{
    // Okay, but less efficient to have separate allocations for
    // Song object and shared_ptr control block.
    auto song = new Song(L"Ode to Joy", L"Beethoven");
    std::shared_ptr<Song> sp0(song);

    // Use make_shared function when possible. Memory for control block
    // and Song object are allocated in the same call:
    auto sp1 = std::make_shared<Song>(L"Yesterday", L"The Beatles");
    auto sp2 = std::make_shared<Song>(L"Blackbird", L"The Beatles");

    // make_shared infers which constructor to use based on the arguments.
    auto sp3 = std::make_shared<Song>(L"Greensleeves");

    // The playlist vector makes copies of the shared_ptr pointers.
    std::vector<std::shared_ptr<Song>> playlist;
    playlist.push_back(sp0);
    playlist.push_back(sp1);
    playlist.push_back(sp2);
    playlist.push_back(sp3);
    playlist.push_back(sp1);
    playlist.push_back(sp2);
    for (auto&& sp : playlist)
    {
        std::wcout << L"Playing " << sp->title_ <<
            L" by " << sp->artist_ << L", use count: " <<
            sp.use_count() << std::endl;
    }
}

int main()
{
    CreateSharedPointers();
}
```

Örnek bu çıktıyı üretir:

```Output
Playing Ode to Joy by Beethoven, use count: 2
Playing Yesterday by The Beatles, use count: 3
Playing Blackbird by The Beatles, use count: 3
Playing Greensleeves by Unknown, use count: 2
Playing Yesterday by The Beatles, use count: 3
Playing Blackbird by The Beatles, use count: 3
```

## <a name="make_unique"></a><a name="make_unique"></a> make_unique

Belirtilen bağımsız değişkenler kullanılarak oluşturulan belirtilen türdeki bir nesneye [unique_ptr](unique-ptr-class.md) oluşturur ve döndürür.

```cpp
// make_unique<T>
template <class T, class... Args>
unique_ptr<T> make_unique(Args&&... args);

// make_unique<T[]>
template <class T>
unique_ptr<T> make_unique(size_t size);

// make_unique<T[N]> disallowed
template <class T, class... Args>
/* unspecified */ make_unique(Args&&...) = delete;
```

### <a name="parameters"></a>Parametreler

*Şı*\
`unique_ptr`Öğesinin işaret edecek nesnenin türü.

*Args*\
*Bağımsız değişkenler tarafından belirtilen* Oluşturucu bağımsız değişkenlerinin türleri.

*args*\
*T* türünde nesnenin oluşturucusuna geçirilecek bağımsız değişkenler.

*ög*\
*T* türünde öğelerin dizisi.

*boyutla*\
Yeni dizide boşluk ayrılacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

İlk aşırı yükleme tek nesneler için kullanılır. İkinci aşırı yükleme diziler için çağrılır. Üçüncü aşırı yükleme, tür bağımsız değişkeninde bir dizi boyutu belirtmekten (make_unique) engel olur \<T[N]> ; Bu oluşturma geçerli standart tarafından desteklenmez. `make_unique`Bir diziye bir oluşturmak için kullandığınızda `unique_ptr` , dizi öğelerini ayrı olarak başlatmalısınız. Bu aşırı yüklemeyi kullanmak yerine, bir [std:: vector](vector-class.md)kullanmak daha iyi bir seçimdir.

`make_unique`Özel durum güvenliği için dikkatle uygulandığından, `make_unique` oluşturucuları doğrudan çağırmak yerine kullanmanızı öneririz `unique_ptr` .

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını göstermektedir `make_unique` . Daha fazla örnek için bkz. [nasıl yapılır: oluşturma ve Unique_ptr örnekleri kullanma](../cpp/how-to-create-and-use-unique-ptr-instances.md).

[!code-cpp[stl_smart_pointers#214](../cpp/codesnippet/CPP/memory-functions_1.cpp)]

Bir ile bağlantılı olarak hata C2280 gördüğünüzde `unique_ptr` , bu, silinmiş bir işlev olan kopya oluşturucusunu çağırmaya çalışırken neredeyse kesinlikle olur.

## <a name="owner_less"></a><a name="owner_less"></a> owner_less

Paylaşılan ve zayıf işaretçilerin sahiplik temelli karışık karşılaştırmalarını sağlar. **`true`** Sol parametrenin, üye işlevi tarafından sağdaki parametreye göre sıralı olup olmadığını döndürür `owner_before` .

```cpp
template <class T>
    struct owner_less; // not defined

template <class T>
struct owner_less<shared_ptr<T>>
{
    bool operator()(
        const shared_ptr<T>& left,
        const shared_ptr<T>& right) const noexcept;

    bool operator()(
        const shared_ptr<T>& left,
        const weak_ptr<T>& right) const noexcept;

    bool operator()(
        const weak_ptr<T>& left,
        const shared_ptr<T>& right) const noexcept;
};

template <class T>
struct owner_less<weak_ptr<T>>
    bool operator()(
        const weak_ptr<T>& left,
        const weak_ptr<T>& right) const noexcept;

    bool operator()(
        const weak_ptr<T>& left,
        const shared_ptr<T>& right) const noexcept;

    bool operator()(
        const shared_ptr<T>& left,
        const weak_ptr<T>& right) const noexcept;
};

template<> struct owner_less<void>
{
    template<class T, class U>
    bool operator()(
        const shared_ptr<T>& left,
        const shared_ptr<U>& right) const noexcept;

    template<class T, class U>
    bool operator()(
        const shared_ptr<T>& left,
        const weak_ptr<U>& right) const noexcept;

    template<class T, class U>
    bool operator()(
        const weak_ptr<T>& left,
        const shared_ptr<U>& right) const noexcept;

    template<class T, class U>
    bool operator()(
        const weak_ptr<T>& left,
        const weak_ptr<U>& right) const noexcept;
};
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Paylaşılan veya zayıf bir işaretçi.

*Right*\
Paylaşılan veya zayıf bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Sınıf şablonları, tüm üye işleçlerini döndüren olarak tanımlar `left.owner_before(right)` .

## <a name="reinterpret_pointer_cast"></a><a name="reinterpret_pointer_cast"></a> reinterpret_pointer_cast

`shared_ptr`Bir dönüştürme kullanarak var olan bir paylaşılan işaretçiden yeni bir oluşturur.

```cpp
template<class T, class U>
shared_ptr<T> reinterpret_pointer_cast(
    const shared_ptr<U>& ptr) noexcept;

template<class T, class U>
shared_ptr<T> reinterpret_pointer_cast(
    shared_ptr<U>&& ptr) noexcept;
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Bir başvurusu `shared_ptr<U>` .

### <a name="remarks"></a>Açıklamalar

*PTR* boş ise, yeni `shared_ptr` de boş olur, aksi takdirde, bir sahipliği *PTR* ile paylaşır. Yeni paylaşılan işaretçi, `reinterpret_cast<Y*>(ptr.get())` nerede olduğu değerlendirmesi sonucudur `Y` `typename std::shared_ptr<T>::element_type` . Doğru biçimlendirilmemiş ise davranış tanımsızdır `reinterpret_cast<T*>((U*)nullptr)` .

Lvalue başvurusunu alan şablon işlevi C++ 17 ' de yenidir. Rvalue başvurusunu alan şablon işlevi C++ 20 ' de yenidir.

## <a name="return_temporary_buffer"></a><a name="return_temporary_buffer"></a> return_temporary_buffer

Şablon işlevi kullanılarak ayrılan geçici belleği kaldırır `get_temporary_buffer` .

```cpp
template <class T>
void return_temporary_buffer(
    T* buffer);
```

### <a name="parameters"></a>Parametreler

*arabelleğin*\
Serbest bırakmak için belleğe yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlevi yalnızca geçici bellek için kullanın.

### <a name="example"></a>Örnek

```cpp
// memory_ret_temp_buf.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

int main( )
{
    // Create an array of ints
    int intArray [] = { 10, 20, 30, 40, 100, 200, 300 };
    int count = sizeof ( intArray ) / sizeof ( int );
    cout << "The number of integers in the array is: "
         << count << "." << endl;

    pair<int *, ptrdiff_t> resultPair;
    resultPair = get_temporary_buffer<int>( count );

    cout << "The number of elements that the allocated memory\n"
         << " could store is given by: resultPair.second = "
         << resultPair.second << "." << endl;

    int* tempBuffer = resultPair.first;

    // Deallocates memory allocated with get_temporary_buffer
    return_temporary_buffer( tempBuffer );
}
```

```Output
The number of integers in the array is: 7.
The number of elements that the allocated memory
could store is given by: resultPair.second = 7.
```

## <a name="static_pointer_cast"></a><a name="static_pointer_cast"></a> static_pointer_cast

[Shared_ptr](shared-ptr-class.md)için statik atama.

```cpp
template <class T, class Other>
shared_ptr<T> static_pointer_cast(
    const shared_ptr<Other>& sp) noexcept;

template <class T, class Other>
shared_ptr<T> static_pointer_cast(
    shared_ptr<Other>&& sp) noexcept;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Döndürülen paylaşılan işaretçi tarafından denetlenen tür.

*Farklı*\
Bağımsız değişken paylaşılan işaretçisi tarafından denetlenen tür.

*SP2*\
Bağımsız değişken paylaşılan işaretçisi.

### <a name="remarks"></a>Açıklamalar

`shared_ptr` *SP* boş bir nesnese şablon işlevi boş bir nesne döndürür `shared_ptr` ; Aksi takdirde, `shared_ptr<T>` *SP*'nin sahip olduğu kaynağa sahip bir nesne döndürür. İfade `static_cast<T*>(sp.get())` geçerli olmalıdır.

### <a name="example"></a>Örnek

```cpp
// std__memory__static_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    int value;
};

struct derived
    : public base
{
};

int main()
{
    std::shared_ptr<base> sp0(new derived);
    std::shared_ptr<derived> sp1 =
        std::static_pointer_cast<derived>(sp0);

    sp0->value = 3;
    std::cout << "sp1->value == " << sp1->value << std::endl;

    return (0);
}
```

```Output
sp1->value == 3
```

## <a name="swap"></a><a name="swap"></a> Kur

İki [shared_ptr](shared-ptr-class.md), [unique_ptr](unique-ptr-class.md)veya [weak_ptr](weak-ptr-class.md) nesneleri takas edin.

```cpp
template <class T>
void swap(
    shared_ptr<T>& left,
    shared_ptr<T>& right) noexcept;

template <class T, class Deleter>
void swap(
    unique_ptr<T, Deleter>& left,
    unique_ptr<T, Deleter>& right) noexcept;

template <class T>
void swap(
    weak_ptr<T>& left,
    weak_ptr<T>& right) noexcept;

```

### <a name="parameters"></a>Parametreler

*Şı*\
Bağımsız değişken işaretçisi tarafından denetlenen tür.

*Silici*\
Benzersiz işaretçi türünün silici.

*tarafta*\
Sol işaretçi.

*Right*\
Sağ işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevleri çağırır `left.swap(right)` .

### <a name="example"></a>Örnek

```cpp
// std__memory__swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::shared_ptr<int> sp2(new int(10));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    sp1.swap(sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;

    swap(sp1, sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << std::endl;

    std::weak_ptr<int> wp1(sp1);
    std::weak_ptr<int> wp2(sp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    wp1.swap(wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    swap(wp1, wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*sp1 == 5
*sp1 == 10
*sp1 == 5

*wp1 == 5
*wp1 == 10
*wp1 == 5
```

## <a name="undeclare_no_pointers"></a><a name="undeclare_no_pointers"></a> undeclare_no_pointers

Taban adresi işaretçisi ve blok boyutu tarafından bellek bloğuna tanımlanan Bellek bloğu karakterlerin artık izlenebilir işaretçileri içerebileceğini atık toplayıcıya bildirir.

```cpp
void undeclare_no_pointers(
    char* ptr,
    size_t size);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Daha önce [declare_no_pointers](#declare_no_pointers)kullanılarak işaretlenen bellek adresine yönelik bir işaretçi.

*boyutla*\
Bellek aralığındaki bayt sayısı. Bu değer, çağrıda kullanılan sayıya eşit olmalıdır `declare_no_pointers` .

### <a name="remarks"></a>Açıklamalar

İşlev, adres aralığının `[ptr, ptr + size)` artık izlenebilecek işaretçiler içerebileceğini belirten tüm çöp toplayıcıyı bilgilendirir.

## <a name="undeclare_reachable"></a><a name="undeclare_reachable"></a> undeclare_reachable

Belirtilen bellek konumu için ulaşılabilirlik bildirimini iptal eder.

```cpp
template <class T>
T *undeclare_reachable(
    T* ptr);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Daha önce [declare_reachable](#declare_reachable)kullanılarak işaretlenen bellek adresine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

*PTR* yoksa **`nullptr`** , işlev, *PTR* 'nin artık ulaşılamaz olduğu tüm çöp toplayıcısına bildirir. Bu, *PTR* ile eşit bir şekilde karşılaştıran bir güvenli türetilmiş işaretçi döndürür.

## <a name="uninitialized_copy"></a><a name="uninitialized_copy"></a> uninitialized_copy

Nesneleri belirli bir kaynak aralığından başlatılmamış hedef aralığına kopyalar.

```cpp
template <class InputIterator, class ForwardIterator>
ForwardIterator uninitialized_copy(
    InputIterator first,
    InputIterator last,
    ForwardIterator dest);

template <class ExecutionPolicy, class InputIterator, class ForwardIterator>
ForwardIterator uninitialized_copy(
    ExecutionPolicy&& policy,
    InputIterator first,
    InputIterator last,
    ForwardIterator dest);
```

### <a name="parameters"></a>Parametreler

*ilkesinin*\
Kullanılacak yürütme ilkesi.

*adı*\
Kaynak aralıktaki ilk öğeyi ele alan bir giriş yineleyici.

*soyadına*\
Kaynak aralıktaki son öğeyi ele alan bir giriş yineleyici.

*HD*\
Hedef aralıktaki ilk öğeyi bulan ileriye doğru yineleyici.

### <a name="return-value"></a>Dönüş Değeri

Kaynak aralığı boş olmadığı takdirde, hedef aralığın ötesinde ilk konumu ele alarak ileriye doğru bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bu algoritma, nesne oluşumundaki bellek tahsisinin bağlantısının kesilmesini sağlar.

Şablon işlevi etkin şekilde şunları yürütür:

```cpp
while (first != last)
{
    new (static_cast<void*>(&* dest++))
        typename iterator_traits<InputIterator>::value_type(*first++);
}
return dest;
```

Kod bir özel durum oluşturmadıkça. Bu durumda, tüm oluşturulmuş nesneler yok edilir ve özel durum yeniden oluşur.

Yürütme ilkesiyle birlikte yükleme, C++ 17 ' de yenidir.

### <a name="example"></a>Örnek

```cpp
// memory_uninit_copy.cpp
// compile with: /EHsc /W3
#include <memory>
#include <iostream>

using namespace std;

class Integer
{
public:
    Integer(int x) : value(x) {}
    int get() { return value; }
private:
    int value;
};

int main()
{
    int Array[] = { 10, 20, 30, 40 };
    const int N = sizeof(Array) / sizeof(int);

    cout << "The initialized Array contains " << N << " elements: ";
    for (int i = 0; i < N; i++)
    {
        cout << " " << Array[i];
    }
    cout << endl;

    Integer* ArrayPtr = (Integer*)malloc(N * sizeof(int));
    Integer* LArrayPtr = uninitialized_copy(
        Array, Array + N, ArrayPtr);  // C4996

    cout << "Address of position after the last element in the array is: "
        << &Array[0] + N << endl;
    cout << "The iterator returned by uninitialized_copy addresses: "
        << (void*)LArrayPtr << endl;
    cout << "The address just beyond the last copied element is: "
        << (void*)(ArrayPtr + N) << endl;

    if ((&Array[0] + N) == (void*)LArrayPtr)
        cout << "The return value is an iterator "
        << "pointing just beyond the original array." << endl;
    else
        cout << "The return value is an iterator "
        << "not pointing just beyond the original array." << endl;

    if ((void*)LArrayPtr == (void*)(ArrayPtr + N))
        cout << "The return value is an iterator "
        << "pointing just beyond the copied array." << endl;
    else
        cout << "The return value is an iterator "
        << "not pointing just beyond the copied array." << endl;

    free(ArrayPtr);

    cout << "Note that the exact addresses returned will vary\n"
        << "with the memory allocation in individual computers."
        << endl;
}
```

## <a name="uninitialized_copy_n"></a><a name="uninitialized_copy_n"></a> uninitialized_copy_n

Bir girdi yineleyicisinde belirtilen öğe sayısının bir kopyasını oluşturur. Kopyalar ileri doğru bir yineleyicinin içine yerleştirilir.

```cpp
template <class InputIterator, class Size, class ForwardIterator>
ForwardIterator uninitialized_copy_n(
    InputIterator first,
    Size count,
    ForwardIterator dest);

template <class ExecutionPolicy, class InputIterator, class Size, class ForwardIterator>
ForwardIterator uninitialized_copy_n(
    ExecutionPolicy&& policy,
    InputIterator first,
    Size count,
    ForwardIterator dest);
```

### <a name="parameters"></a>Parametreler

*ilkesinin*\
Kullanılacak yürütme ilkesi.

*adı*\
Kopyalanacak nesneye başvuran Bir girdi yineleyicisi.

*biriktirme*\
Nesnenin kaç defa kopyalanacağını belirten işaretli veya işaretsiz tamsayı türü.

*HD*\
Yeni kopyanın gideceği yere başvuran ileri doğru yineleyici.

### <a name="return-value"></a>Dönüş Değeri

Hedefin ötesindeki ilk konuma yönelen ileri doğru yineleyici. Kaynak aralığı boşsa, yineleyici *ilk* olarak ele alınmaktadır.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi aşağıdaki kodu etkin bir şekilde yürütür:

```cpp
    for (; 0 < count; --count)
        new (static_cast<void*>(&* dest++))
            typename iterator_traits<InputIterator>::value_type(*first++);
    return dest;
```

Kod bir özel durum oluşturmadıkça. Bu durumda, tüm oluşturulmuş nesneler yok edilir ve özel durum yeniden oluşur.

Yürütme ilkesiyle birlikte yükleme, C++ 17 ' de yenidir.

## <a name="uninitialized_default_construct"></a><a name="uninitialized_default_construct"></a> uninitialized_default_construct

Varsayılan, belirtilen aralıktaki yineleyicilerin nesnelerini oluşturur `value_type` .

```cpp
template <class ForwardIterator>
void uninitialized_default_construct(
    ForwardIterator first,
    ForwardIterator last);

template <class ExecutionPolicy, class ForwardIterator>
void uninitialized_default_construct(
    ExecutionPolicy&& policy,
    ForwardIterator first,
    ForwardIterator last);
```

### <a name="parameters"></a>Parametreler

*ilkesinin*\
Kullanılacak yürütme ilkesi.

*adı*\
Oluşturmak için aralıktaki ilk öğeyi adresleyen bir yineleyici.

*soyadına*\
Oluşturmak için aralıktaki son öğeyi geçen bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Yürütme ilkesi olmayan sürüm, şu şekilde etkili olur:

```cpp
for (; first != last; ++first)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type;
```

Bir özel durum oluşturulursa, önceden oluşturulmuş nesneler belirtilmemiş sırada yok edilir.

Yürütme ilkesi olan sürüm aynı sonuca sahiptir, ancak belirtilen *ilkeye* göre yürütülür.

Bu işlevler C++ 17 ' de yenidir.

## <a name="uninitialized_default_construct_n"></a><a name="uninitialized_default_construct_n"></a> uninitialized_default_construct_n

Varsayılan değer, belirtilen konumdan başlayarak Yineleyici için belirtilen sayıda nesne oluşturur `value_type` .

```cpp
template <class ForwardIterator, class Size>
ForwardIterator uninitialized_default_construct_n(
    ForwardIterator first,
    Size count);

template <class ExecutionPolicy, class ForwardIterator, class Size>
ForwardIterator uninitialized_default_construct_n(
    ExecutionPolicy&& policy,
    ForwardIterator first,
    Size count);
```

### <a name="parameters"></a>Parametreler

*ilkesinin*\
Kullanılacak yürütme ilkesi.

*adı*\
Hedef aralıktaki ilk öğeyi oluşturmak için adresleyen bir yineleyici.

*biriktirme*\
Yapı için hedef aralıktaki öğelerin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Kaynak aralığı boş olmadığı takdirde, hedef aralığın ötesinde ilk konumu ele alarak ileriye doğru bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Yürütme ilkesi olmayan sürüm, şu şekilde etkili olur:

```cpp
for (; count>0; (void)++first, --count)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type;
return first;
```

Bir özel durum oluşturulursa, önceden oluşturulmuş nesneler belirtilmemiş sırada yok edilir.

Yürütme ilkesi olan sürüm aynı sonuca sahiptir, ancak belirtilen *ilkeye* göre yürütülür.

Bu işlevler C++ 17 ' de yenidir.

## <a name="uninitialized_fill"></a><a name="uninitialized_fill"></a> uninitialized_fill

Belirli bir değerin nesnelerini başlatılmamış hedef aralığına kopyalar.

```cpp
template <class ForwardIterator, class T>
void uninitialized_fill(
    ForwardIterator first,
    ForwardIterator last,
    const T& value);

template <class ExecutionPolicy, class ForwardIterator, class T>
void uninitialized_fill(
    ExecutionPolicy&& policy,
    ForwardIterator first,
    ForwardIterator last,
    const T& value);
```

### <a name="parameters"></a>Parametreler

*ilkesinin*\
Kullanılacak yürütme ilkesi.

*adı*\
Hedef aralıktaki ilk öğeyi başlatmak için bir ileriye doğru yineleyici.

*soyadına*\
Hedef aralıktaki son öğeyi başlatmak için bir ileriye doğru yineleyici.

*deeri*\
Hedef aralığı başlatmak için kullanılacak değer.

### <a name="remarks"></a>Açıklamalar

Bu algoritma, nesne oluşumundaki bellek tahsisinin bağlantısının kesilmesini sağlar.

Şablon işlevi etkin şekilde şunları yürütür:

```cpp
while (first != last)
    new (static_cast<void*>(&* first ++))
        typename iterator_traits<ForwardIterator>::value_type (value);
```

Kod bir özel durum oluşturmadıkça. Bu durumda, tüm oluşturulmuş nesneler yok edilir ve özel durum yeniden oluşur.

Yürütme ilkesiyle birlikte yükleme, C++ 17 ' de yenidir.

### <a name="example"></a>Örnek

```cpp
// memory_uninit_fill.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

class Integer
{
public:
    // No default constructor
    Integer( int x ) : value( x ) {}
    int get() { return value; }
private:
    int value;
};

int main()
{
    const int N = 10;
    Integer value ( 25 );
    Integer* Array = ( Integer* ) malloc( N * sizeof( int ) );
    uninitialized_fill( Array, Array + N, value );
    cout << "The initialized Array contains: ";
    for ( int i = 0; i < N; i++ )
        {
            cout << Array[ i ].get() << " ";
        }
    cout << endl;
}
```

```Output
The initialized Array contains: 25 25 25 25 25 25 25 25 25 25
```

## <a name="uninitialized_fill_n"></a><a name="uninitialized_fill_n"></a> uninitialized_fill_n

Belirtilen bir değerin nesnelerini, başlatılmamış bir hedef aralığın belirtilen sayıda öğesine kopyalar.

```cpp
template <class ForwardIterator, class Size, class T>
ForwardIterator uninitialized_fill_n(
    ForwardIterator first,
    Size count,
    const T& value);

template <class ExecutionPolicy, class ForwardIterator, class Size, class T>
ForwardIterator uninitialized_fill_n(
    ExecutionPolicy&& policy,
    ForwardIterator first,
    Size count,
    const T& value);
```

### <a name="parameters"></a>Parametreler

*ilkesinin*\
Kullanılacak yürütme ilkesi.

*adı*\
Hedef aralıktaki ilk öğeyi başlatmak için bir ileriye doğru yineleyici.

*biriktirme*\
Başlatılacak öğe sayısı.

*deeri*\
Hedef aralığı başlatmak için kullanılacak değer.

### <a name="remarks"></a>Açıklamalar

Bu algoritma, nesne oluşumundaki bellek tahsisinin bağlantısının kesilmesini sağlar.

Şablon işlevi etkin şekilde şunları yürütür:

```cpp
while (0 < count--)
    new (static_cast<void*>(&* first++))
        typename iterator_traits<ForwardIterator>::value_type(value);
return first;
```

Kod bir özel durum oluşturmadıkça. Bu durumda, tüm oluşturulmuş nesneler yok edilir ve özel durum yeniden oluşur.

Yürütme ilkesiyle birlikte yükleme, C++ 17 ' de yenidir.

### <a name="example"></a>Örnek

```cpp
// memory_uninit_fill_n.cpp
// compile with: /EHsc /W3
#include <memory>
#include <iostream>

using namespace std;

class Integer
{
public:
    // No default constructor
    Integer( int x ) : value( x ) {}
    int get() { return value; }
private:
    int value;
};

int main()
{
    const int N = 10;
    Integer value( 60 );
    Integer* Array = ( Integer* ) malloc( N * sizeof( int ) );
    uninitialized_fill_n( Array, N, value );  // C4996
    cout << "The uninitialized Array contains: ";
    for ( int i = 0; i < N; i++ )
        cout << Array[ i ].get() <<  " ";
}
```

## <a name="uninitialized_move"></a><a name="uninitialized_move"></a> uninitialized_move

Öğeleri bir kaynak aralığından başlatılmamış hedef bellek alanına kaydırır.

```cpp
template <class InputIterator, class ForwardIterator>
ForwardIterator uninitialized_move(
    InputIterator first,
    InputIterator last,
    ForwardIterator dest);

template <class ExecutionPolicy, class InputIterator, class ForwardIterator>
ForwardIterator uninitialized_move(
    ExecutionPolicy&& policy,
    InputIterator first,
    InputIterator last,
    ForwardIterator dest);
```

### <a name="parameters"></a>Parametreler

*ilkesinin*\
Kullanılacak yürütme ilkesi.

*adı*\
Kaynak aralıktaki taşınacak ilk öğeyi ele almak için bir giriş Yineleyici.

*soyadına*\
Kaynak aralıktaki son öğeden geçen ve taşınacak bir giriş Yineleyici.

*HD*\
Hedef aralığın başlangıcı.

### <a name="remarks"></a>Açıklamalar

Yürütme ilkesi olmayan sürüm, şu şekilde etkili olur:

```cpp
for (; first != last; (void)++dest, ++first)
    ::new (static_cast<void*>(addressof(*dest)))
        typename iterator_traits<ForwardIterator>::value_type(std::move(*first));
return dest;
```

Bir özel durum oluşturulursa, kaynak aralıktaki bazı nesneler geçerli ancak belirtilmeyen bir durumda kalabilir. Önceden oluşturulmuş nesneler belirtilmemiş sırada yok edilir.

Yürütme ilkesi olan sürüm aynı sonuca sahiptir, ancak belirtilen *ilkeye* göre yürütülür.

Bu işlevler C++ 17 ' de yenidir.

## <a name="uninitialized_move_n"></a><a name="uninitialized_move_n"></a> uninitialized_move_n

Belirli sayıda öğeyi bir kaynak aralığından başlatılmamış hedef bellek alanına kaydırır.

```cpp
template <class InputIterator, class Size, class ForwardIterator>
pair<InputIterator, ForwardIterator> uninitialized_move_n(
    InputIterator first,
    Size count,
    ForwardIterator dest);

template <class ExecutionPolicy, class InputIterator, class Size, class ForwardIterator>
pair<InputIterator, ForwardIterator> uninitialized_move_n(
    ExecutionPolicy&& policy,
    InputIterator first,
    Size count,
    ForwardIterator dest);
```

### <a name="parameters"></a>Parametreler

*ilkesinin*\
Kullanılacak yürütme ilkesi.

*adı*\
Kaynak aralıktaki taşınacak ilk öğeyi ele almak için bir giriş Yineleyici.

*biriktirme*\
Taşınacak kaynak aralıktaki öğelerin sayısı.

*HD*\
Hedef aralığın başlangıcı.

### <a name="remarks"></a>Açıklamalar

Yürütme ilkesi olmayan sürüm, şu şekilde etkili olur:

```cpp
for (; count > 0; ++dest, (void) ++first, --count)
    ::new (static_cast<void*>(addressof(*dest)))
        typename iterator_traits<ForwardIterator>::value_type(std::move(*first));
return {first, dest};
```

Bir özel durum oluşturulursa, kaynak aralıktaki bazı nesneler geçerli ancak belirtilmeyen bir durumda kalabilir. Önceden oluşturulmuş nesneler belirtilmemiş sırada yok edilir.

Yürütme ilkesi olan sürüm aynı sonuca sahiptir, ancak belirtilen *ilkeye* göre yürütülür.

Bu işlevler C++ 17 ' de yenidir.

## <a name="uninitialized_value_construct"></a><a name="uninitialized_value_construct"></a> uninitialized_value_construct

`value_type`Belirtilen aralıkta değer başlatmaya göre yineleyicilerin nesnelerini oluşturur.

```cpp
template <class ForwardIterator>
void uninitialized_value_construct(
    ForwardIterator first,
    ForwardIterator last);

template <class ExecutionPolicy, class ForwardIterator>
void uninitialized_value_construct(
    ExecutionPolicy&& policy,
    ForwardIterator first,
    ForwardIterator last);
```

### <a name="parameters"></a>Parametreler

*ilkesinin*\
Kullanılacak yürütme ilkesi.

*adı*\
Değer yapısına göre aralıktaki ilk öğeyi adresleyen bir yineleyici.

*soyadına*\
Değer yapısına olan aralıktaki son öğeyi aşan bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Yürütme ilkesi olmayan sürüm, şu şekilde etkili olur:

```cpp
for (; first != last; ++first)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type();
```

Bir özel durum oluşturulursa, önceden oluşturulmuş nesneler belirtilmemiş sırada yok edilir.

Yürütme ilkesi olan sürüm aynı sonuca sahiptir, ancak belirtilen *ilkeye* göre yürütülür.

Bir bellek ayırma hatası oluşursa, bir `std::bad_alloc` özel durum oluşturulur.

Bu işlevler C++ 17 ' de yenidir.

## <a name="uninitialized_value_construct_n"></a><a name="uninitialized_value_construct_n"></a> uninitialized_value_construct_n

`value_type`Belirtilen konumdan başlayarak, yineleyicinin değer başlatmasına göre belirtilen sayıda nesnesini oluşturur.

```cpp
template <class ForwardIterator, class Size>
ForwardIterator uninitialized_value_construct_n(
    ForwardIterator first,
    Size count);

template <class ExecutionPolicy, class ForwardIterator, class Size>
ForwardIterator uninitialized_value_construct_n(
    ExecutionPolicy&& policy,
    ForwardIterator first,
    Size count);
```

### <a name="parameters"></a>Parametreler

*ilkesinin*\
Kullanılacak yürütme ilkesi.

*adı*\
Hedef aralıktaki ilk öğeyi oluşturmak için adresleyen bir yineleyici.

*biriktirme*\
Yapı için hedef aralıktaki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Yürütme ilkesi olmayan sürüm, şu şekilde etkili olur:

```cpp
for (; count > 0; (void)++first, --count)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type();
return first;
```

Bir özel durum oluşturulursa, önceden oluşturulmuş nesneler belirtilmemiş sırada yok edilir.

Yürütme ilkesi olan sürüm aynı sonuca sahiptir, ancak belirtilen *ilkeye* göre yürütülür.

Bir bellek ayırma hatası oluşursa, bir `std::bad_alloc` özel durum oluşturulur.

Bu işlevler C++ 17 ' de yenidir.

## <a name="uses_allocator_v"></a><a name="uses_allocator_v"></a> uses_allocator_v

Şablonun değerine erişmek için bir yardımcı değişken şablonu `uses_allocator` .

```cpp
template <class T, class Alloc>
inline constexpr bool uses_allocator_v = uses_allocator<T, Alloc>::value;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<memory>](memory.md)
