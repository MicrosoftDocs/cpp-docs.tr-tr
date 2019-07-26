---
title: '&lt;bellek&gt; işlevleri'
ms.date: 02/06/2019
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
- xmemory/std::get_temporary_buffer
- memory/std::make_shared
- memory/std::make_unique
- memory/std::owner_less
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
ms.openlocfilehash: 14818e93e79a0be9960ba67088f81d51d402b717
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448499"
---
# <a name="ltmemorygt-functions"></a>&lt;bellek&gt; işlevleri

## <a name="addressof"></a>AddressOf

Bir nesnenin doğru adresini alır.

```cpp
template <class T>
    T* addressof(T& Val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Doğru adresi alacak nesne veya işlev.

### <a name="return-value"></a>Dönüş Değeri

Aşırı yüklenmiş `operator&()` olsa bile, *değer*tarafından başvurulan nesnenin veya işlevin gerçek adresi.

### <a name="remarks"></a>Açıklamalar

## <a name="align"></a>acaktır

Verilen depolamanın ilk olası adresinde verilen, verilen hizalama belirtimine göre hizalanmış, boyutta depolamaya uyar.

```cpp
void* align(
    size_t Alignment, // input
    size_t Size,      // input
    void*& Ptr,        // input/output
    size_t& Space     // input/output
);
```

### <a name="parameters"></a>Parametreler

*Hizalar*\
Denenecek hizalama sınırı.

*Boyutla*\
Hizalanmış depolama için bayt cinsinden boyut.

*Kaydetmeye*\
Kullanılacak mevut bitişik depolama havuzunun başlangıç adresi. Bu parametre aynı zamanda bir çıktı parametresidir ve hizalama başarılı olursa yeni başlangıç adresini içerecek şekilde ayarlanır. Başarısız `align()` olursa, bu parametre değiştirilmez.

*Boşlu*\
Hizalanmış depolamayı oluştururken kullanılabilecek `align()` Toplam alan. Bu parametre aynı zamanda bir çıktı parametresidir ve hizalanmış depolamanın ve herhangi ilişkili ek yükün çıkarılmasının ardından depolama arabelleğinde kalan düzenlenmiş alanı içerir.

Başarısız `align()` olursa, bu parametre değiştirilmez.

### <a name="return-value"></a>Dönüş Değeri

İstenen hizalanmış arabelleğin kullanılabilir alana sığmadığı durumlarda boş bir işaretçi; Aksi halde, yeni *PTR*değeri.

### <a name="remarks"></a>Açıklamalar

Değiştirilen *PTR* ve *Space* parametreleri, büyük olasılıkla *Hizalama* ve `align()` *Boyut*için farklı değerlerle aynı arabellekte sürekli olarak çağrı etkinleştirmenizi sağlar. Aşağıdaki kod parçacığı bir kullanımını `align()`gösterir.

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

Belirtilen ayırıcı `shared_ptr` kullanılarak belirli bir tür için ayrılan ve oluşturulan nesneler için bir oluşturur. `shared_ptr`Döndürür.

```cpp
template <class Type, class Allocator, class... Types>
    shared_ptr<Type> allocate_shared(Allocator Alloc, Types&&... Args);
```

### <a name="parameters"></a>Parametreler

*Tahsis*\
Nesneleri oluşturmak için kullanılan ayırıcı.

*Args*\
Nesneler haline gelen sıfır veya daha fazla bağımsız değişken.

### <a name="remarks"></a>Açıklamalar

İşlevi, ayrılan ve `shared_ptr<Type>` *ayırma*tarafından oluşturulan bir `Type(Args...)` işaretçi olan nesnesini oluşturur.

## <a name="atomic_compare_exchange_strong"></a>atomic_compare_exchange_strong

```cpp
template<class T>
    bool atomic_compare_exchange_strong(shared_ptr<T>* p, shared_ptr<T>* v, shared_ptr<T> w);
```

## <a name="atomic_compare_exchange_weak"></a>atomic_compare_exchange_weak

```cpp
template<class T>
    bool atomic_compare_exchange_weak(shared_ptr<T>* p, shared_ptr<T>* v, shared_ptr<T> w);
```

## <a name="atomic_compare_exchange_strong_explicit"></a>atomic_compare_exchange_strong_explicit

```cpp
template<class T>
    bool atomic_compare_exchange_strong_explicit(shared_ptr<T>* p, shared_ptr<T>* v, shared_ptr<T> w, memory_order success, memory_order failure);
```

## <a name="atomic_compare_exchange_weak_explicit"></a>atomic_compare_exchange_weak_explicit

```cpp
template<class T>
    bool atomic_compare_exchange_weak_explicit(shared_ptr<T>* p, shared_ptr<T>* v, shared_ptr<T> w, memory_order success, memory_order failure);
```

## <a name="atomic_exchange"></a>atomic_exchange

```cpp
template<class T>
    shared_ptr<T> atomic_exchange(shared_ptr<T>* p, shared_ptr<T> r);
```

## <a name="atomic_exchange_explicit"></a>atomic_exchange_explicit

```cpp
template<class T>
    shared_ptr<T> atomic_exchange_explicit(shared_ptr<T>* p, shared_ptr<T> r, memory_order mo);
```

## <a name="atomic_is_lock_free"></a>atomic_is_lock_free

```cpp
template<class T>
    bool atomic_is_lock_free(const shared_ptr<T>* p);
```

## <a name="atomic_load"></a>atomic_load

```cpp
template<class T>
    shared_ptr<T> atomic_load(const shared_ptr<T>* p);
```

## <a name="atomic_load_explicit"></a>atomic_load_explicit

```cpp
template<class T>
    shared_ptr<T> atomic_load_explicit(const shared_ptr<T>* p, memory_order mo);
```

## <a name="atomic_store"></a>atomic_store

```cpp
template<class T>
    void atomic_store(shared_ptr<T>* p, shared_ptr<T> r);
```

## <a name="atomic_store_explicit"></a>atomic_store_explicit

```cpp
template<class T>
    void atomic_store_explicit(shared_ptr<T>* p, shared_ptr<T> r, memory_order mo);
```

## <a name="const_pointer_cast"></a>const_pointer_cast

Shared_ptr 'e const atama.

```cpp
template <class Ty, class Other>
    shared_ptr<Ty> const_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Döndürülen paylaşılan işaretçi tarafından denetlenen tür.

*Farklı*\
Bağımsız değişken paylaşılan işaretçisi tarafından denetlenen tür.

*Farklı*\
Bağımsız değişken paylaşılan işaretçisi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, null bir `const_cast<Ty*>(sp.get())` işaretçi döndürürse boş bir shared_ptr nesnesi döndürür; Aksi takdirde, tarafından `sp`sahip olunan kaynağa sahip olan [shared_ptr sınıf](../standard-library/shared-ptr-class.md)\<Ty > nesnesini döndürür. İfade `const_cast<Ty*>(sp.get())` geçerli olmalıdır.

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
void declare_no_pointers(char* ptr, size_t _Size);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Artık izlenebilecek işaretçiler içermeyen ilk karakterin adresi.

*_Boyut*\
İzlenebilen işaretçiler içermeyen *PTR* 'de başlayan bloğun boyutu.

### <a name="remarks"></a>Açıklamalar

İşlev, adres `[ ptr, ptr + _Size)` aralığının artık izlenebilecek işaretçiler içermediği tüm çöp toplayıcıyı bilgilendirir. (Ayrılan depolamaya yönelik işaretçilere, erişilebilir olmadığı müddetçe başvurulmamalıdır.)

## <a name="declare_reachable"></a>declare_reachable

Belirtilen adresin ayrılmış depolama alanını ve erişilebilir olduğunu atık toplamaya bildirir.

```cpp
void declare_reachable(void* ptr);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Erişilebilir, ayrılmış, geçerli bir depolama alanına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

*PTR* null değilse, işlev, *PTR* 'nin bundan sonra erişilebilen herhangi bir çöp toplayıcıyı bilgilendirir (geçerli ayrılmış depolamaya işaret eder).

## <a name="default_delete"></a>default_delete

**New işleciyle**ayrılan nesneleri siler. İle `unique_ptr`kullanım için uygundur.

```cpp
struct default_delete {
   constexpr default_delete() noexcept = default;
   template <class Other, class = typename enable_if<is_convertible<Other*, T*>::value, void>::type>>
        default_delete(const default_delete<Other>&) noexcept;
   void operator()(T* Ptr) const noexcept;
};
```

### <a name="parameters"></a>Parametreler

*Kaydetmeye*\
Silinecek nesnenin işaretçisi.

*Farklı*\
Silinecek dizideki öğelerin türü.

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı, **New işleci**ile ayrılmış skaler nesneleri silen ve şablon sınıfı `unique_ptr`ile kullanım için uygun olan bir `deleter` öğesini açıklar. Ayrıca, açık özelleşmeye `default_delete<Type[]>`de sahiptir.

## <a name="destroy_at"></a>destroy_at

```cpp
template <class T>
    void destroy_at(T* location);
```

`location->~T()`Aynı.

## <a name="destroy"></a>kaldırılır

```cpp
template <class ForwardIterator>
    void destroy(ForwardIterator first, ForwardIterator last);
```

`for (; first!=last; ++first) destroy_at(addressof(*first)); `Aynı.

## <a name="destroy_n"></a>destroy_n

```cpp
template <class ForwardIterator, class Size>
    ForwardIterator destroy_n(ForwardIterator first, Size n);
```

`for (; n > 0; (void)++first, --n) destroy_at(addressof(*first)); return first;`Aynı.

## <a name="dynamic_pointer_cast"></a>dynamic_pointer_cast

Shared_ptr 'e dinamik atama.

```cpp
template <class Ty, class Other>
    shared_ptr<Ty> dynamic_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Döndürülen paylaşılan işaretçi tarafından denetlenen tür.

*Farklı*\
Bağımsız değişken paylaşılan işaretçisi tarafından denetlenen tür.

*SP2*\
Bağımsız değişken paylaşılan işaretçisi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `dynamic_cast<Ty*>(sp.get())` , null bir işaretçi döndürürse boş bir shared_ptr nesnesi döndürür; Aksi takdirde, *SP*'nin sahip olduğu kaynağa sahip bir [shared_ptr sınıf](../standard-library/shared-ptr-class.md)\<Ty > nesnesi döndürür. İfade `dynamic_cast<Ty*>(sp.get())` geçerli olmalıdır.

### <a name="example"></a>Örnek

```cpp
// std__memory__dynamic_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    virtual ~base() {}
    int val;
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

    sp0->val = 3;
    std::cout << "sp1->val == " << sp1->val << std::endl;

    return (0);
}
```

```Output
sp1->val == 3
```

## <a name="get_deleter"></a>get_deleter

Shared_ptr 'ten silici alın.

```cpp
template <class D, class Ty>
    D* get_deleter(const shared_ptr<Ty>& sp);
```

### <a name="parameters"></a>Parametreler

*TID*\
Deleter türü.

*Kalite*\
Paylaşılan işaretçi tarafından denetlenen tür.

*SP2*\
Paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, [Shared_ptr sınıf](../standard-library/shared-ptr-class.md) nesne *SP*'sine ait olan *D* türünün silicilerine bir işaretçi döndürür. *SP* 'nin hiç bir silici yoksa veya silici tür *D* değilse, işlev 0 döndürür.

### <a name="example"></a>Örnek

```cpp
// std__memory__get_deleter.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    int val;
};

struct deleter
{
    void operator()(base *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<base> sp0(new base);

    sp0->val = 3;
    std::cout << "get_deleter(sp0) != 0 == " << std::boolalpha
        << (std::get_deleter<deleter>(sp0) != 0) << std::endl;

    std::shared_ptr<base> sp1(new base, deleter());

    sp0->val = 3;
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
pointer_safety get_pointer_safety();
```

### <a name="remarks"></a>Açıklamalar

İşlevi, herhangi bir otomatik çöp toplayıcı tarafından kabul edilen işaretçi güvenlik türünü döndürür.

## <a name="get_temporary_buffer"></a>get_temporary_buffer

Belirli sayıda öğeyi aşmayan öğe dizisi için geçici depolamayı ayırır.

```cpp
template <class Type>
    pair<Type *, ptrdiff_t> get_temporary_buffer(ptrdiff_t count);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Ayrılan bellek için istenen en fazla öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

`pair` İlk bileşeni ayrılan belleğe yönelik bir işaretçidir ve ikinci bileşen, depolayabileceği en büyük öğe sayısını belirten arabelleğin boyutunu verir.

### <a name="remarks"></a>Açıklamalar

İşlev, bellek için bir istek yapar ve başarısız olabilir. Hiçbir arabellek ayrılıyorsa, işlev bir çift döndürür ve ikinci bileşen sıfıra eşit ve ilk bileşen null işaretçisine eşittir.

Bu işlev yalnızca geçici olan bellek için kullanılmalıdır.

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
   int intArray [ ] = { 10, 20, 30, 40, 100, 200, 300, 1000, 2000 };
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

Varsayılan ayırıcıyı kullanarak sıfır `shared_ptr` veya daha fazla bağımsız değişken tarafından oluşturulan ayrılmış nesneleri işaret eden bir oluşturur ve döndürür. Nesnenin paylaşılan sahipliğini yönetmek için hem belirtilen türdeki hem de bir `shared_ptr` nesnesini ayırır ve oluşturur ve `shared_ptr`döndürür.

```cpp
template <class Type, class... Types>
    shared_ptr<Type> make_shared(Types&&... _Args);
```

### <a name="parameters"></a>Parametreler

*_Bağımsız değişkenler*\
Sıfır veya daha fazla Oluşturucu bağımsız değişkeni. İşlevi, sunulan bağımsız değişkenlere dayanarak hangi Oluşturucu aşırı yüklemesinin çağrılmasını sağlar.

### <a name="remarks"></a>Açıklamalar

Bir `make_shared` nesne oluşturmak için basit ve daha verimli bir yol `shared_ptr` ve aynı zamanda nesneye paylaşılan erişimi yönetmek için kullanın. Anlamsal olarak, bu iki deyim eşdeğerdir:

```cpp
auto sp = std::shared_ptr<Example>(new Example(argument));
auto msp = std::make_shared<Example>(argument);
```

Ancak, ilk ifade iki ayırma yapar ve `shared_ptr` `Example` nesnenin ayrılması sonrasında başarısız olursa, adlandırılmamış `Example` nesne sızdırılmaz. Öğesinin kullanıldığı `make_shared` ifade, yalnızca bir işlev çağrısı olduğundan daha basittir. Kitaplık hem nesne hem de akıllı işaretçi için tek bir ayırma yapabildiğinden daha etkilidir. Bu hem daha hızlıdır hem de daha az bellek parçalanması sağlar ve bir ayırma üzerinde bir özel durum değildir ancak diğeri değildir. Performans, nesneye başvuran kod için daha iyi konum tarafından geliştirilmiştir ve akıllı işaretçisindeki başvuru sayılarını günceller.

Nesnesine paylaşılan erişim gerekmiyorsa [make_unique](../standard-library/memory-functions.md#make_unique) kullanmayı düşünün. Nesne için özel bir ayırıcı belirtmeniz gerekiyorsa [allocate_shared](../standard-library/memory-functions.md#allocate_shared) kullanın. Nesneniz bir bağımsız `make_shared` değişken olarak geçirmenin bir yolu olmadığından, nesneniz özel bir silici gerektiriyorsa kullanamazsınız.

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

void CreateSharedPointers() {
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
   for (auto&& sp : playlist) {
      std::wcout << L"Playing " << sp->title_ <<
         L" by " << sp->artist_ << L", use count: " <<
         sp.use_count() << std::endl;
   }
}

int main() {
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

Belirtilen bağımsız değişkenler kullanılarak oluşturulan belirtilen türün nesnesine bir [unique_ptr](../standard-library/unique-ptr-class.md) oluşturur ve döndürür.

```cpp
// make_unique<T>
template <class T, class... Types>
    unique_ptr<T> make_unique(Types&&... Args)
    {
        return (unique_ptr<T>(new T(forward<Types>(Args)...)));
    }

// make_unique<T[]>
template <class T>
    make_unique(size_t Size)
    {
        return (unique_ptr<T>(new Elem[Size]()));
    }

// make_unique<T[N]> disallowed
template <class T, class... Types>
    typename enable_if<extent<T>::value != 0, void>::type make_unique(Types&&...) = delete;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Öğesinin işaret `unique_ptr` edecek nesnenin türü.

*Türü*\
Bağımsız *değişkenler tarafından belirtilen*Oluşturucu bağımsız değişkenlerinin türleri.

*Args*\
*T*türünde nesnenin oluşturucusuna geçirilecek bağımsız değişkenler.

*Elem*\
*T*türünde öğelerin dizisi.

*Boyutla*\
Yeni dizide boşluk ayrılacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

İlk aşırı yükleme tek nesneler için kullanılır, ikinci aşırı yükleme diziler için çağrılır ve üçüncü aşırı yükleme, tür bağımsız değişkeninde (make_unique\<T [N] >) bir dizi boyutu belirtmesini önler; bu oluşturma geçerli bir nesne tarafından desteklenmiyor Stand. Bir diziye bir `make_unique` `unique_ptr` oluşturmak için kullandığınızda, dizi öğelerini ayrı olarak başlatmalısınız. Bu aşırı yüklemeyi düşünüyorsanız, bir [std:: vector](../standard-library/vector-class.md)kullanmak daha iyi bir seçimdir.

Özel durum güvenliği için dikkatle uygulandığından, oluşturucuları doğrudan çağırmak `unique_ptr` yerine kullanmanızı `make_unique` öneririz. `make_unique`

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını `make_unique`göstermektedir. Daha fazla örnek için bkz [. nasıl yapılır: Unique_ptr örnekleri](../cpp/how-to-create-and-use-unique-ptr-instances.md)oluşturun ve kullanın.

[!code-cpp[stl_smart_pointers#214](../cpp/codesnippet/CPP/memory-functions_1.cpp)]

Bir `unique_ptr`ile bağlantılı olarak hata C2280 gördüğünüzde, bu, silinmiş bir işlev olan kopya oluşturucusunu çağırmaya çalışırken neredeyse kesinlikle olur.

## <a name="owner_less"></a>owner_less

Paylaşılan ve zayıf işaretçilerin sahiplik temelli karışık karşılaştırmalarını sağlar. Sol  parametre üye işlevin `owner_before`sağ parametresinden önce sipariş alıyorsa true değerini döndürür.

```cpp
template <class Type>
    struct owner_less; // not defined

template <class Type>
struct owner_less<shared_ptr<Type>> {
    bool operator()(
    const shared_ptr<Type>& left,
    const shared_ptr<Type>& right);

    bool operator()(
    const shared_ptr<Type>& left,
    const weak_ptr<Type>& right);

    bool operator()(
    const weak_ptr<Type>& left,
    const shared_ptr<Type>& right);
};

template <class Type>
struct owner_less<weak_ptr<Type>>
    bool operator()(
    const weak_ptr<Type>& left,
    const weak_ptr<Type>& right);

    bool operator()(
    const weak_ptr<Type>& left,
    const shared_ptr<Ty>& right);

    bool operator()(
    const shared_ptr<Type>& left,
    const weak_ptr<Type>& right);
};
```

### <a name="parameters"></a>Parametreler

*_sol*\
Paylaşılan veya zayıf bir işaretçi.

*Right*\
Paylaşılan veya zayıf bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon sınıfları, tüm üye işleçlerini döndüren `left.owner_before(right)`olarak tanımlar.

## <a name="return_temporary_buffer"></a>return_temporary_buffer

`get_temporary_buffer` Şablon işlevi kullanılarak ayrılan geçici belleği kaldırır.

```cpp
template <class Type>
    void return_temporary_buffer(Type* _Pbuf);
```

### <a name="parameters"></a>Parametreler

*_Parabelleğe*\
Serbest bırakmak için belleğe yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca geçici olan bellek için kullanılmalıdır.

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
   int intArray [ ] = { 10, 20, 30, 40, 100, 200, 300 };
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
   return_temporary_buffer ( tempBuffer );
}
```

```Output
The number of integers in the array is: 7.
The number of elements that the allocated memory
could store is given by: resultPair.second = 7.
```

## <a name="static_pointer_cast"></a>static_pointer_cast

Shared_ptr 'e statik atama.

```cpp
template <class Ty, class Other>
    shared_ptr<Ty> static_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Döndürülen paylaşılan işaretçi tarafından denetlenen tür.

*Farklı*\
Bağımsız değişken paylaşılan işaretçisi tarafından denetlenen tür.

*Farklı*\
Bağımsız değişken paylaşılan işaretçisi.

### <a name="remarks"></a>Açıklamalar

Şablon `sp` işlevi boş `shared_ptr` bir nesne ise boş bir shared_ptr nesnesi döndürür; Aksi takdirde, sahip olduğu kaynağa sahip olan [shared_ptr sınıf](../standard-library/shared-ptr-class.md)\<Ty `sp`> nesnesini döndürür. İfade `static_cast<Ty*>(sp.get())` geçerli olmalıdır.

### <a name="example"></a>Örnek

```cpp
// std__memory__static_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    int val;
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

    sp0->val = 3;
    std::cout << "sp1->val == " << sp1->val << std::endl;

    return (0);
}
```

```Output
sp1->val == 3
```

## <a name="swap"></a>Kur

İki shared_ptr veya weak_ptr nesnesini takas edin.

```cpp
template <class Ty, class Other>
    void swap(shared_ptr<Ty>& left, shared_ptr<Other>& right);

template <class Ty, class Other>
    void swap(weak_ptr<Ty>& left, weak_ptr<Other>& right);
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sol paylaşılan/zayıf işaretçi tarafından denetlenen tür.

*Farklı*\
Doğru paylaşılan/zayıf işaretçi tarafından denetlenen tür.

*tarafta*\
Sol paylaşılan/zayıf işaretçi.

*Right*\
Doğru paylaşılan/zayıf işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevleri çağırır `left.swap(right)`.

### <a name="example"></a>Örnek

```cpp
// std__memory__swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

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
void undeclare_no_pointers(char* ptr, size_t _Size);
```

### <a name="remarks"></a>Açıklamalar

İşlev, adres `[ptr, ptr + _Size)` aralığının artık izlenebilecek işaretçiler içerebileceğini belirten tüm çöp toplayıcıyı bilgilendirir.

## <a name="undeclare_reachable"></a>undeclare_reachable

Belirtilen bellek konumu için ulaşılabilirlik bildirimini iptal eder.

```cpp
template <class Type>
    Type *undeclare_reachable(Type* ptr);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Belirtilecek bellek adresine yönelik bir işaretçiye ulaşılamıyor.

### <a name="remarks"></a>Açıklamalar

*PTR* bir **nullptr**değilse, işlev, *PTR* 'nin artık erişilebilir olmadığı tüm atık toplayıcısına bildirir. Bu, *PTR*ile aynı karşılaştırması yapan güvenle türetilmiş bir işaretçi döndürür.

## <a name="uninitialized_copy"></a>uninitialized_copy

Nesneleri belirli bir kaynak aralığından başlatılmamış hedef aralığına kopyalar.

```cpp
template <class InputIterator, class ForwardIterator>
    ForwardIterator uninitialized_copy(InputIterator first, InputIterator last, ForwardIterator dest);
```

### <a name="parameters"></a>Parametreler

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
while (first != last) {
    new (static_cast<void*>(&* dest++))
        typename iterator_traits<InputIterator>::value_type(*first++);
}
return dest;
```

Kod bir özel durum oluşturmadıkça. Bu durumda, tüm oluşturulmuş nesneler yok edilir ve özel durum yeniden oluşur.

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
    Integer(int x) : val(x) {}
    int get() { return val; }
private:
    int val;
};

int main()
{
    int Array[] = { 10, 20, 30, 40 };
    const int N = sizeof(Array) / sizeof(int);

    int i;
    cout << "The initialized Array contains " << N << " elements: ";
    for (i = 0; i < N; i++)
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
```

### <a name="parameters"></a>Parametreler

*adı*\
Kopyalanacak nesneye başvuran Bir girdi yineleyicisi.

*biriktirme*\
Nesnenin kaç defa kopyalanacağını belirten işaretli veya işaretsiz tamsayı türü.

*HD*\
Yeni kopyanın gideceği yere başvuran ileri doğru yineleyici.

### <a name="return-value"></a>Dönüş Değeri

Hedefin ötesindeki ilk konuma yönelen ileri doğru yineleyici. Kaynak aralığı boşsa, yineleyici *ilk*olarak ele alınmaktadır.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi etkin şekilde aşağıdakileri yürütür:

```cpp
    for (; 0 < count; --count)
        new (static_cast<void*>(&* dest++))
            typename iterator_traits<InputIterator>::value_type(*first++);
    return dest;
```

Kod bir özel durum oluşturmadıkça. Bu durumda, tüm oluşturulmuş nesneler yok edilir ve özel durum yeniden oluşur.

## <a name="uninitialized_default_construct"></a>uninitialized_default_construct

```cpp
template <class ForwardIterator>
    void uninitialized_default_construct(ForwardIterator first, ForwardIterator last); 
```

### <a name="remarks"></a>Açıklamalar

Aynı:

```cpp
for (; first != last; ++first)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type;
```

## <a name="uninitialized_default_construct_n"></a>uninitialized_default_construct_n

```cpp
template <class ForwardIterator, class Size>
    ForwardIterator uninitialized_default_construct_n(ForwardIterator first, Size n)
```

### <a name="remarks"></a>Açıklamalar

Aynı:

```cpp
for (; n>0; (void)++first, --n)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type; return first;
```

## <a name="uninitialized_fill"></a>uninitialized_fill

Belirli bir değerin nesnelerini başlatılmamış hedef aralığına kopyalar.

```cpp
template <class ForwardIterator, class Type>
    void uninitialized_fill(ForwardIterator first, ForwardIterator last, const Type& val);
```

### <a name="parameters"></a>Parametreler

*adı*\
Başlatılacak hedef aralıktaki ilk öğeyi ele alan bir ileriye doğru yineleyici.

*soyadına*\
Başlatılacak hedef aralıktaki son öğeyi ele alan bir ileriye doğru yineleyici.

*Acil*\
Hedef aralığı başlatmak için kullanılacak değer.

### <a name="remarks"></a>Açıklamalar

Bu algoritma, nesne oluşumundaki bellek tahsisinin bağlantısının kesilmesini sağlar.

Şablon işlevi etkin şekilde şunları yürütür:

```cpp
while (first != last)
    new (static_cast<void*>(&* first ++))
        typename iterator_traits<ForwardIterator>::value_type (val);
```

Kod bir özel durum oluşturmadıkça. Bu durumda, tüm oluşturulmuş nesneler yok edilir ve özel durum yeniden oluşur.

### <a name="example"></a>Örnek

```cpp
// memory_uninit_fill.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

class Integer {         // No default constructor
   public:
      Integer( int x ) : val( x ) {}
      int get( ) { return val; }
   private:
      int val;
};

int main( )
{
   const int N = 10;
   Integer val ( 25 );
   Integer* Array = ( Integer* ) malloc( N * sizeof( int ) );
   uninitialized_fill( Array, Array + N, val );
   int i;
   cout << "The initialized Array contains: ";
      for ( i = 0 ; i < N; i++ )
      {
         cout << Array [ i ].get( ) << " ";
      }
   cout << endl;
}
```

```Output
The initialized Array contains: 25 25 25 25 25 25 25 25 25 25
```

## <a name="uninitialized_fill_n"></a>uninitialized_fill_n

Belirli bir değerin nesnelerini belirli sayıda öğenin başlatılmamış hedef aralığı içine kopyalar.

```cpp
template <class FwdIt, class Size, class Type>
    void uninitialized_fill_n(ForwardIterator first, Size count, const Type& val);
```

### <a name="parameters"></a>Parametreler

*adı*\
Başlatılacak hedef aralıktaki ilk öğeyi bulan ileriye doğru yineleyici.

*biriktirme*\
Başlatılacak öğe sayısı.

*Acil*\
Hedef aralığı başlatmak için kullanılacak değer.

### <a name="remarks"></a>Açıklamalar

Bu algoritma, nesne oluşumundaki bellek tahsisinin bağlantısının kesilmesini sağlar.

Şablon işlevi etkin şekilde şunları yürütür:

```cpp
while (0 < count--)
    new (static_cast<void*>(&* first++))
        typename iterator_traits<ForwardIterator>::value_type(val);
```

Kod bir özel durum oluşturmadıkça. Bu durumda, tüm oluşturulmuş nesneler yok edilir ve özel durum yeniden oluşur.

### <a name="example"></a>Örnek

```cpp
// memory_uninit_fill_n.cpp
// compile with: /EHsc /W3
#include <memory>
#include <iostream>

using namespace std;

class Integer {   // No default constructor
public:
   Integer( int x ) : val( x ) {}
   int get( ) { return val; }
private:
   int val;
};

int main() {
   const int N = 10;
   Integer val ( 60 );
   Integer* Array = ( Integer* ) malloc( N * sizeof( int ) );
   uninitialized_fill_n( Array, N, val );  // C4996
   int i;
   cout << "The uninitialized Array contains: ";
   for ( i = 0 ; i < N; i++ )
      cout << Array [ i ].get( ) <<  " ";
}
```

## <a name="uninitialized_move"></a>uninitialized_move

```cpp
template <class InputIterator, class ForwardIterator>
    ForwardIterator uninitialized_move(InputIterator first, InputIterator last, ForwardIterator result); 
```

### <a name="remarks"></a>Açıklamalar

Aynı:

```cpp
for (; first != last; (void)++result, ++first)
    ::new (static_cast<void*>(addressof(*result)))
        typename iterator_traits<ForwardIterator>::value_type(std::move(*first)); 
        return result;
```

Bir özel durum oluşturulursa, aralıktaki bazı nesneler geçerli ancak belirtilmeyen bir durumda kalabilir.

## <a name="uninitialized_move_n"></a>uninitialized_move_n

```cpp
template <class InputIterator, class Size, class ForwardIterator>
    pair<InputIterator, ForwardIterator> uninitialized_move_n(InputIterator first, Size n, ForwardIterator result);
```

### <a name="remarks"></a>Açıklamalar

Aynı:

```cpp
for (; n > 0; ++result, (void) ++first, --n)
    ::new (static_cast<void*>(addressof(*result)))
        typename iterator_traits<ForwardIterator>::value_type(std::move(*first)); return {first,result};
```

Bir özel durum oluşturulursa, aralıktaki bazı nesneler geçerli ancak belirtilmeyen bir durumda kalabilir.

## <a name="uninitialized_value_construct"></a>uninitialized_value_construct

```cpp
template <class ForwardIterator>
    void uninitialized_value_construct(ForwardIterator first, ForwardIterator last);
```

### <a name="remarks"></a>Açıklamalar

Aynı:

```cpp
for (; first != last; ++first)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type();
```

## <a name="uninitialized_value_construct_n"></a>uninitialized_value_construct_n

```cpp
template <class ForwardIterator, class Size>
    ForwardIterator uninitialized_value_construct_n(ForwardIterator first, Size n);
```

Aynı:
```cpp
for (; n>0; (void)++first, --n)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type(); return first;
```

## <a name="uses_allocator_v"></a>uses_allocator_v

```cpp
template <class T, class Alloc>
    inline constexpr bool uses_allocator_v = uses_allocator<T, Alloc>::value;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<bellek >](../standard-library/memory.md)
