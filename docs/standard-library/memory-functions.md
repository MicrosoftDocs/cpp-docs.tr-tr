---
title: '&lt;belleği&gt; işlevleri'
ms.date: 08/05/2019
f1_keywords:
- memory/std::addressof
- memory/std::align
- memory/std::allocate_shared
- memory/std::const_pointer_cast
- memory/std::declare_no_pointers
- memory/std::declare_reachable
- memory/std::default_delete
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
- memory/std::get_temporary_buffer
- memory/std::return_temporary_buffer
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
ms.openlocfilehash: 2aceb96fcda49df8a1fd40a1bd8011170dccd8ef
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79419940"
---
# <a name="ltmemorygt-functions"></a>&lt;belleği&gt; işlevleri

## <a name="addressof"></a>AddressOf

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

*değer*\
Doğru adresi alacak nesne veya işlev.

### <a name="return-value"></a>Dönüş Değeri

Aşırı yüklenmiş bir `operator&()` var olsa bile, *değer*tarafından başvurulan nesnenin veya işlevin gerçek adresi.

### <a name="remarks"></a>Açıklamalar

## <a name="align"></a>acaktır

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

*hizalama*\
Denenecek hizalama sınırı.

*boyut*\
Hizalanmış depolama için bayt cinsinden boyut.

*ptr*\
Kullanılacak mevut bitişik depolama havuzunun başlangıç adresi. Bu parametre aynı zamanda bir çıktı parametresidir ve hizalama başarılı olursa yeni başlangıç adresini içerecek şekilde ayarlanır. `align()` başarısız olursa, bu parametre değiştirilmez.

*boşluk*\
Hizalanmış depolama alanı oluşturulurken kullanılacak `align()` için kullanılabilir toplam alan. Bu parametre aynı zamanda bir çıktı parametresidir ve hizalanmış depolamanın ve herhangi ilişkili ek yükün çıkarılmasının ardından depolama arabelleğinde kalan düzenlenmiş alanı içerir.

`align()` başarısız olursa, bu parametre değiştirilmez.

### <a name="return-value"></a>Dönüş Değeri

İstenen hizalanmış arabelleğin kullanılabilir alana sığmadığı durumlarda boş bir işaretçi; Aksi halde, yeni *PTR*değeri.

### <a name="remarks"></a>Açıklamalar

Değiştirilen *PTR* ve *Space* parametreleri, büyük olasılıkla *Hizalama* ve *Boyut*için farklı değerlerle `align()`, aynı arabellekte sürekli olarak aramanızı sağlar. Aşağıdaki kod parçacığı bir `align()`kullanımını gösterir.

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

## <a name="allocate_shared"></a>allocate_shared

Belirtilen ayırıcı kullanılarak belirli bir tür için ayrılan ve oluşturulan nesnelere bir [shared_ptr](shared-ptr-class.md) oluşturur. `shared_ptr`döndürür.

```cpp
template <class T, class Allocator, class... Args>
shared_ptr<T> allocate_shared(
    Allocator alloc,
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

*ayırma*\
Nesneleri oluşturmak için kullanılan ayırıcı.

*bağımsız değişkenler*\
Nesneler haline gelen sıfır veya daha fazla bağımsız değişken.

### <a name="remarks"></a>Açıklamalar

İşlevi, ayrılan ve *ayırma*tarafından oluşturulan `T(args...)` bir işaretçi olan `shared_ptr<T>`nesnesini oluşturur.

## <a name="atomic_compare_exchange_strong"></a>atomic_compare_exchange_strong

```cpp
template<class T>
bool atomic_compare_exchange_strong(
    shared_ptr<T>* u,
    shared_ptr<T>* v,
    shared_ptr<T> w);
```

## <a name="atomic_compare_exchange_weak"></a>atomic_compare_exchange_weak

```cpp
template<class T>
bool atomic_compare_exchange_weak(
    shared_ptr<T>* u,
    shared_ptr<T>* v,
    shared_ptr<T> w);
```

## <a name="atomic_compare_exchange_strong_explicit"></a>atomic_compare_exchange_strong_explicit

```cpp
template<class T>
bool atomic_compare_exchange_strong_explicit(
    shared_ptr<T>* u,
    shared_ptr<T>* v,
    shared_ptr<T> w,
    memory_order success,
    memory_order failure);
```

## <a name="atomic_compare_exchange_weak_explicit"></a>atomic_compare_exchange_weak_explicit

```cpp
template<class T>
bool atomic_compare_exchange_weak_explicit(
    shared_ptr<T>* u,
    shared_ptr<T>* v,
    shared_ptr<T> w,
    memory_order success,
    memory_order failure);
```

## <a name="atomic_exchange"></a>atomic_exchange

```cpp
template<class T>
shared_ptr<T> atomic_exchange(
    shared_ptr<T>* u,
    shared_ptr<T> r);
```

## <a name="atomic_exchange_explicit"></a>atomic_exchange_explicit

```cpp
template<class T>
shared_ptr<T> atomic_exchange_explicit(
    shared_ptr<T>* u,
    shared_ptr<T> r,
    memory_order mo);
```

## <a name="atomic_is_lock_free"></a>atomic_is_lock_free

```cpp
template<class T>
bool atomic_is_lock_free(
    const shared_ptr<T>* u);
```

## <a name="atomic_load"></a>atomic_load

```cpp
template<class T>
shared_ptr<T> atomic_load(
    const shared_ptr<T>* u);
```

## <a name="atomic_load_explicit"></a>atomic_load_explicit

```cpp
template<class T>
shared_ptr<T> atomic_load_explicit(
    const shared_ptr<T>* u,
    memory_order mo);
```

## <a name="atomic_store"></a>atomic_store

```cpp
template<class T>
void atomic_store(
    shared_ptr<T>* u,
    shared_ptr<T> r);
```

## <a name="atomic_store_explicit"></a>atomic_store_explicit

```cpp
template<class T>
void atomic_store_explicit(
    shared_ptr<T>* u,
    shared_ptr<T> r,
    memory_order mo);
```

## <a name="const_pointer_cast"></a>const_pointer_cast

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

*T*\
Döndürülen paylaşılan işaretçi tarafından denetlenen tür.

*Diğer*\
Bağımsız değişken paylaşılan işaretçisi tarafından denetlenen tür.

*sp*\
Bağımsız değişken paylaşılan işaretçisi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `const_cast<T*>(sp.get())` null bir işaretçi döndürürse boş bir `shared_ptr` nesnesi döndürür; Aksi takdirde, *SP*tarafından sahip olunan kaynağın sahibi olan bir `shared_ptr<T>` nesnesi döndürür. `const_cast<T*>(sp.get())` ifadesi geçerli olmalıdır.

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

## <a name="declare_no_pointers"></a>declare_no_pointers

Bir temel adres işaretçisi ve blok boyutu tarafından tanımlanan bellek bloğundaki karakterlerin izlenebilen işaretçiler içermediğini belirten bir atık toplayıcıya bildirir.

```cpp
void declare_no_pointers(
    char* ptr,
    size_t size);
```

### <a name="parameters"></a>Parametreler

*ptr*\
Artık izlenebilecek işaretçiler içermeyen ilk karakterin adresi.

*boyut*\
İzlenebilen işaretçiler içermeyen *PTR* 'de başlayan bloğun boyutu.

### <a name="remarks"></a>Açıklamalar

İşlevi, aralıktaki adreslerin artık izlenebilecek işaretçiler içermediğini `[ ptr, ptr + size)` tüm çöp toplayıcıyı bilgilendirir. (Ayrılan depolamaya yönelik işaretçilere, erişilebilir olmadığı müddetçe başvurulmamalıdır.)

## <a name="declare_reachable"></a>declare_reachable

Belirtilen adresin ayrılmış depolama alanını ve erişilebilir olduğunu atık toplamaya bildirir.

```cpp
void declare_reachable(
    void* ptr);
```

### <a name="parameters"></a>Parametreler

*ptr*\
Erişilebilir, ayrılmış, geçerli bir depolama alanına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

*PTR* null değilse, işlev, *PTR* 'nin artık ulaşılabilir olduğunu, yani geçerli ayrılmış depolamayı işaret ettiğini bildiren tüm çöp toplayıcıyı bilgilendirir.

## <a name="default_delete"></a>default_delete

**New işleciyle**ayrılan nesneleri siler. [Unique_ptr](unique-ptr-class.md)ile kullanım için uygun.

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

*ptr*\
Silinecek nesnenin işaretçisi.

*Diğer*\
Silinecek dizideki öğelerin türü.

### <a name="remarks"></a>Açıklamalar

Sınıf şablonu, **New işleciyle**ayrılmış skalar nesneleri silen ve sınıf şablonuyla kullanım için uygun olan bir silici tanımlar `unique_ptr`. Ayrıca, açık özelleşmenin `default_delete<T[]>`de vardır.

## <a name="destroy_at"></a>destroy_at

```cpp
template <class T>
void destroy_at(
    T* location);
```

`location->~T()`ile aynı.

## <a name="destroy"></a>kaldırılır

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

## <a name="destroy_n"></a>destroy_n

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

## <a name="dynamic_pointer_cast"></a>dynamic_pointer_cast

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

*T*\
Döndürülen paylaşılan işaretçi tarafından denetlenen tür.

*Diğer*\
Bağımsız değişken paylaşılan işaretçisi tarafından denetlenen tür.

*sp*\
Bağımsız değişken paylaşılan işaretçisi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `dynamic_cast<T*>(sp.get())` null bir işaretçi döndürürse boş bir `shared_ptr` nesnesi döndürür; Aksi takdirde, *SP*tarafından sahip olunan kaynağın sahibi olan bir `shared_ptr<T>` nesnesi döndürür. `dynamic_cast<T*>(sp.get())` ifadesi geçerli olmalıdır.

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

## <a name="get_deleter"></a>get_deleter

[Shared_ptr](shared-ptr-class.md)silici alın.

```cpp
template <class Deleter, class T>
Deleter* get_deleter(
    const shared_ptr<T>& sp) noexcept;
```

### <a name="parameters"></a>Parametreler

*Silici*\
Deleter türü.

*T*\
Paylaşılan işaretçi tarafından denetlenen tür.

*sp*\
Paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, *sp*`shared_ptr` nesne türüne ait olan tür *silici* için bir işaretçi döndürür. *SP* 'nin hiç bir silici yoksa veya silici tür *silici*değilse, işlev 0 döndürür.

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

## <a name="get_pointer_safety"></a>get_pointer_safety

Herhangi bir atık toplayıcısı tarafından kabul edilen işaretçi güvenlik türünü döndürür.

```cpp
pointer_safety get_pointer_safety() noexcept;
```

### <a name="remarks"></a>Açıklamalar

İşlevi, herhangi bir otomatik çöp toplayıcı tarafından kabul edilen işaretçi güvenlik türünü döndürür.

## <a name="get_temporary_buffer"></a>get_temporary_buffer

Belirtilen sayıda öğeyi aşmayan öğe dizisi için geçici depolamayı ayırır.

```cpp
template <class T>
pair<T *, ptrdiff_t> get_temporary_buffer(
    ptrdiff_t count);
```

### <a name="parameters"></a>Parametreler

*sayı*\
Ayrılan bellek için istenen en fazla öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

İlk bileşeni ayrılan belleğe yönelik bir işaretçi ve ikinci bileşen, depolayabileceği en fazla öğe sayısını belirten arabelleğin boyutunu veren bir `pair`.

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

## <a name="make_shared"></a>make_shared

Varsayılan ayırıcıyı kullanarak sıfır veya daha fazla bağımsız değişken tarafından oluşturulan ayrılmış nesneleri işaret eden bir [shared_ptr](shared-ptr-class.md) oluşturur ve döndürür. Nesnenin paylaşılan sahipliğini yönetmek için belirtilen türdeki bir nesneyi ve bir `shared_ptr` ayırır ve `shared_ptr`döndürür.

```cpp
template <class T, class... Args>
shared_ptr<T> make_shared(
    Args&&... args);
```

### <a name="parameters"></a>Parametreler

*bağımsız değişkenler*\
Sıfır veya daha fazla Oluşturucu bağımsız değişkeni. İşlevi, sunulan bağımsız değişkenlere dayanarak hangi Oluşturucu aşırı yüklemesinin çağrılmasını sağlar.

### <a name="remarks"></a>Açıklamalar

Bir nesne oluşturmak için basit ve daha verimli bir yol olarak `make_shared` kullanın ve aynı zamanda nesneye paylaşılan erişimi yönetmek için `shared_ptr`. Anlamsal olarak, bu iki deyim eşdeğerdir:

```cpp
auto sp = std::shared_ptr<Example>(new Example(argument));
auto msp = std::make_shared<Example>(argument);
```

Ancak, ilk ifade iki ayırma yapar ve `shared_ptr` ayırması `Example` nesnesinin ayrılması başarılı olduktan sonra başarısız olursa, adlandırılmamış `Example` nesnesi sızdırılmaz. Yalnızca bir işlev çağrısı olduğundan `make_shared` kullanan ifade basittir. Kitaplık hem nesne hem de akıllı işaretçi için tek bir ayırma yapabildiğinden daha etkilidir. Bu işlev hem daha hızlıdır hem de daha az bellek parçalanması sağlar ve bir ayırma üzerinde bir özel durum değildir ancak diğeri değildir. Performans, nesneye başvuran kod için daha iyi konum tarafından geliştirilmiştir ve akıllı işaretçisindeki başvuru sayılarını günceller.

Nesneye paylaşılan erişim gerekmiyorsa [make_unique](memory-functions.md#make_unique) kullanmayı düşünün. Nesne için özel bir ayırıcı belirtmeniz gerekiyorsa [allocate_shared](memory-functions.md#allocate_shared) kullanın. Nesneniz bir bağımsız değişken olarak geçirmenin bir yolu olmadığından, nesneniz özel bir silici gerektiriyorsa `make_shared` kullanamazsınız.

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

## <a name="make_unique"></a>make_unique

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

*T*\
`unique_ptr` işaret edecek nesnenin türü.

*Bağımsız değişkenler*\
*Bağımsız değişkenler tarafından belirtilen*Oluşturucu bağımsız değişkenlerinin türleri.

*bağımsız değişkenler*\
*T*türünde nesnenin oluşturucusuna geçirilecek bağımsız değişkenler.

*öğe*\
*T*türünde öğelerin dizisi.

*boyut*\
Yeni dizide boşluk ayrılacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

İlk aşırı yükleme tek nesneler için kullanılır. İkinci aşırı yükleme diziler için çağrılır. Üçüncü aşırı yükleme, tür bağımsız değişkeninde bir dizi boyutu belirtmekten (make_unique\<T [N] >) izin vermez; Bu oluşturma geçerli standart tarafından desteklenmiyor. Bir diziye `unique_ptr` oluşturmak için `make_unique` kullandığınızda, dizi öğelerini ayrı olarak başlatmalısınız. Bu aşırı yüklemeyi kullanmak yerine, bir [std:: vector](vector-class.md)kullanmak daha iyi bir seçimdir.

`make_unique` özel durum güvenliği için dikkatle uygulandığından, `unique_ptr` oluşturucularını doğrudan çağırmak yerine `make_unique` kullanmanızı öneririz.

### <a name="example"></a>Örnek

Aşağıdaki örnek `make_unique`nasıl kullanacağınızı gösterir. Daha fazla örnek için bkz. [nasıl yapılır: oluşturma ve Unique_ptr örnekleri kullanma](../cpp/how-to-create-and-use-unique-ptr-instances.md).

[!code-cpp[stl_smart_pointers#214](../cpp/codesnippet/CPP/memory-functions_1.cpp)]

Bir `unique_ptr`bağlantı içinde hata C2280 gördüğünüzde, bu, silinmiş bir işlev olan kopya oluşturucusunu çağırmaya çalışırken neredeyse kesinlikle olur.

## <a name="owner_less"></a>owner_less

Paylaşılan ve zayıf işaretçilerin sahiplik temelli karışık karşılaştırmalarını sağlar. Sol parametre `owner_before`üye işlevi tarafından sağ parametreden önce sıralandıysa **true** döndürür.

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

*sol*\
Paylaşılan veya zayıf bir işaretçi.

*sağ*\
Paylaşılan veya zayıf bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Sınıf şablonları, `left.owner_before(right)`döndüren tüm üye operatörlerini tanımlar.

## <a name="reinterpret_pointer_cast"></a>reinterpret_pointer_cast

Bir dönüştürme kullanarak varolan bir paylaşılan işaretçiden yeni bir `shared_ptr` oluşturur.

```cpp
template<class T, class U>
shared_ptr<T> reinterpret_pointer_cast(
    const shared_ptr<U>& ptr) noexcept;

template<class T, class U>
shared_ptr<T> reinterpret_pointer_cast(
    shared_ptr<U>&& ptr) noexcept;
```

### <a name="parameters"></a>Parametreler

*ptr*\
Bir `shared_ptr<U>`başvurusu.

### <a name="remarks"></a>Açıklamalar

*PTR* boş ise, yeni `shared_ptr` de boştur, aksi takdirde bu, sahipliği *PTR*ile paylaşır. Yeni paylaşılan işaretçi, `Y` `typename std::shared_ptr<T>::element_type``reinterpret_cast<Y*>(ptr.get())`değerlendirilme sonucudur. `reinterpret_cast<T*>((U*)nullptr)` düzgün biçimlendirilmediyse davranış tanımsızdır.

Lvalue başvurusunu alan şablon işlevi C++ 17 ' de yenidir. Rvalue başvurusunu alan şablon işlevi C++ 20 ' de yenidir.

## <a name="return_temporary_buffer"></a>return_temporary_buffer

`get_temporary_buffer` Template işlevi kullanılarak ayrılan geçici belleği kaldırır.

```cpp
template <class T>
void return_temporary_buffer(
    T* buffer);
```

### <a name="parameters"></a>Parametreler

*arabellek*\
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

## <a name="static_pointer_cast"></a>static_pointer_cast

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

*T*\
Döndürülen paylaşılan işaretçi tarafından denetlenen tür.

*Diğer*\
Bağımsız değişken paylaşılan işaretçisi tarafından denetlenen tür.

*sp*\
Bağımsız değişken paylaşılan işaretçisi.

### <a name="remarks"></a>Açıklamalar

*SP* boş bir `shared_ptr` nesnese, şablon işlevi boş bir `shared_ptr` nesnesi döndürür; Aksi takdirde, *SP*tarafından sahip olunan kaynağın sahibi olan bir `shared_ptr<T>` nesnesi döndürür. `static_cast<T*>(sp.get())` ifadesi geçerli olmalıdır.

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

## <a name="swap"></a>Kur

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

*T*\
Bağımsız değişken işaretçisi tarafından denetlenen tür.

*Silici*\
Benzersiz işaretçi türünün silici.

*sol*\
Sol işaretçi.

*sağ*\
Sağ işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevleri `left.swap(right)`çağırır.

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

## <a name="undeclare_no_pointers"></a>undeclare_no_pointers

Taban adresi işaretçisi ve blok boyutu tarafından bellek bloğuna tanımlanan Bellek bloğu karakterlerin artık izlenebilir işaretçileri içerebileceğini atık toplayıcıya bildirir.

```cpp
void undeclare_no_pointers(
    char* ptr,
    size_t size);
```

### <a name="parameters"></a>Parametreler

*ptr*\
Daha önce [declare_no_pointers](#declare_no_pointers)kullanılarak işaretlenen bellek adresine yönelik bir işaretçi.

*boyut*\
Bellek aralığındaki bayt sayısı. Bu değer `declare_no_pointers` çağrısında kullanılan sayıya eşit olmalıdır.

### <a name="remarks"></a>Açıklamalar

İşlev, `[ptr, ptr + size)` adres aralığının artık izlenebilecek işaretçiler içerebileceğini belirten tüm çöp toplayıcıyı bilgilendirir.

## <a name="undeclare_reachable"></a>undeclare_reachable

Belirtilen bellek konumu için ulaşılabilirlik bildirimini iptal eder.

```cpp
template <class T>
T *undeclare_reachable(
    T* ptr);
```

### <a name="parameters"></a>Parametreler

*ptr*\
Daha önce [declare_reachable](#declare_reachable)kullanılarak işaretlenen bellek adresine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

*PTR* bir **nullptr**değilse, işlev, *PTR* 'nin artık erişilebilir olmadığı tüm atık toplayıcısına bildirir. Bu, *PTR*ile eşit bir şekilde karşılaştıran bir güvenli türetilmiş işaretçi döndürür.

## <a name="uninitialized_copy"></a>uninitialized_copy

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

*ilke*\
Kullanılacak yürütme ilkesi.

*ilk*\
Kaynak aralıktaki ilk öğeyi ele alan bir giriş yineleyici.

*son*\
Kaynak aralıktaki son öğeyi ele alan bir giriş yineleyici.

*hedef*\
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

## <a name="uninitialized_copy_n"></a>uninitialized_copy_n

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

*ilke*\
Kullanılacak yürütme ilkesi.

*ilk*\
Kopyalanacak nesneye başvuran Bir girdi yineleyicisi.

*sayı*\
Nesnenin kaç defa kopyalanacağını belirten işaretli veya işaretsiz tamsayı türü.

*hedef*\
Yeni kopyanın gideceği yere başvuran ileri doğru yineleyici.

### <a name="return-value"></a>Dönüş Değeri

Hedefin ötesindeki ilk konuma yönelen ileri doğru yineleyici. Kaynak aralığı boşsa, yineleyici *ilk*olarak ele alınmaktadır.

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

## <a name="uninitialized_default_construct"></a>uninitialized_default_construct

Varsayılan değer, belirtilen aralıktaki yineleyicilerin ' `value_type` nesnelerini oluşturur.

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

*ilke*\
Kullanılacak yürütme ilkesi.

*ilk*\
Oluşturmak için aralıktaki ilk öğeyi adresleyen bir yineleyici.

*son*\
Oluşturmak için aralıktaki son öğeyi geçen bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Yürütme ilkesi olmayan sürüm, şu şekilde etkili olur:

```cpp
for (; first != last; ++first)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type;
```

Bir özel durum oluşturulursa, önceden oluşturulmuş nesneler belirtilmemiş sırada yok edilir.

Yürütme ilkesi olan sürüm aynı sonuca sahiptir, ancak belirtilen *ilkeye*göre yürütülür.

Bu işlevler C++ 17 ' de yenidir.

## <a name="uninitialized_default_construct_n"></a>uninitialized_default_construct_n

Varsayılan değer, belirli bir konumdan başlayarak Yineleyici `value_type`nesnelerinin belirli bir sayısını oluşturur.

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

*ilke*\
Kullanılacak yürütme ilkesi.

*ilk*\
Hedef aralıktaki ilk öğeyi oluşturmak için adresleyen bir yineleyici.

*sayı*\
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

Yürütme ilkesi olan sürüm aynı sonuca sahiptir, ancak belirtilen *ilkeye*göre yürütülür.

Bu işlevler C++ 17 ' de yenidir.

## <a name="uninitialized_fill"></a>uninitialized_fill

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

*ilke*\
Kullanılacak yürütme ilkesi.

*ilk*\
Hedef aralıktaki ilk öğeyi başlatmak için bir ileriye doğru yineleyici.

*son*\
Hedef aralıktaki son öğeyi başlatmak için bir ileriye doğru yineleyici.

*değer*\
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

## <a name="uninitialized_fill_n"></a>uninitialized_fill_n

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

*ilke*\
Kullanılacak yürütme ilkesi.

*ilk*\
Hedef aralıktaki ilk öğeyi başlatmak için bir ileriye doğru yineleyici.

*sayı*\
Başlatılacak öğe sayısı.

*değer*\
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

## <a name="uninitialized_move"></a>uninitialized_move

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

*ilke*\
Kullanılacak yürütme ilkesi.

*ilk*\
Kaynak aralıktaki taşınacak ilk öğeyi ele almak için bir giriş Yineleyici.

*son*\
Kaynak aralıktaki son öğeden geçen ve taşınacak bir giriş Yineleyici.

*hedef*\
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

Yürütme ilkesi olan sürüm aynı sonuca sahiptir, ancak belirtilen *ilkeye*göre yürütülür.

Bu işlevler C++ 17 ' de yenidir.

## <a name="uninitialized_move_n"></a>uninitialized_move_n

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

*ilke*\
Kullanılacak yürütme ilkesi.

*ilk*\
Kaynak aralıktaki taşınacak ilk öğeyi ele almak için bir giriş Yineleyici.

*sayı*\
Taşınacak kaynak aralıktaki öğelerin sayısı.

*hedef*\
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

Yürütme ilkesi olan sürüm aynı sonuca sahiptir, ancak belirtilen *ilkeye*göre yürütülür.

Bu işlevler C++ 17 ' de yenidir.

## <a name="uninitialized_value_construct"></a>uninitialized_value_construct

Belirtilen aralıkta değer başlatmaya göre yineleyiciler ' `value_type` nesne oluşturur.

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

*ilke*\
Kullanılacak yürütme ilkesi.

*ilk*\
Değer yapısına göre aralıktaki ilk öğeyi adresleyen bir yineleyici.

*son*\
Değer yapısına olan aralıktaki son öğeyi aşan bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Yürütme ilkesi olmayan sürüm, şu şekilde etkili olur:

```cpp
for (; first != last; ++first)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type();
```

Bir özel durum oluşturulursa, önceden oluşturulmuş nesneler belirtilmemiş sırada yok edilir.

Yürütme ilkesi olan sürüm aynı sonuca sahiptir, ancak belirtilen *ilkeye*göre yürütülür.

Bir bellek ayırma hatası oluşursa, bir `std::bad_alloc` özel durumu oluşturulur.

Bu işlevler C++ 17 ' de yenidir.

## <a name="uninitialized_value_construct_n"></a>uninitialized_value_construct_n

Belirli bir konumdan başlayarak, yineleyici `value_type`, değer başlatmaya göre belirtilen sayıda nesne oluşturur.

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

*ilke*\
Kullanılacak yürütme ilkesi.

*ilk*\
Hedef aralıktaki ilk öğeyi oluşturmak için adresleyen bir yineleyici.

*sayı*\
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

Yürütme ilkesi olan sürüm aynı sonuca sahiptir, ancak belirtilen *ilkeye*göre yürütülür.

Bir bellek ayırma hatası oluşursa, bir `std::bad_alloc` özel durumu oluşturulur.

Bu işlevler C++ 17 ' de yenidir.

## <a name="uses_allocator_v"></a>uses_allocator_v

`uses_allocator` şablonun değerine erişmek için bir yardımcı değişken şablonu.

```cpp
template <class T, class Alloc>
inline constexpr bool uses_allocator_v = uses_allocator<T, Alloc>::value;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<belleği >](memory.md)
