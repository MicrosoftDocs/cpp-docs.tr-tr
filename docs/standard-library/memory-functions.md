---
title: '&lt;bellek&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 3e1898c2-44b7-4626-87ce-84962e4c6f1a
author: corob-msft
ms.author: corob
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
ms.workload:
- cplusplus
ms.openlocfilehash: 676f6522a5625103a00310c6ce5353ce40da9359
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="ltmemorygt-functions"></a>&lt;bellek&gt; işlevleri

||||
|-|-|-|
|[addressof](#addressof)|[align](#align)|[allocate_shared](#allocate_shared)|
|[const_pointer_cast](#const_pointer_cast)|[declare_no_pointers](#declare_no_pointers)|[declare_reachable](#declare_reachable)|
|[default_delete](#default_delete)|[dynamic_pointer_cast](#dynamic_pointer_cast)|[get_deleter](#get_deleter)|
|[get_pointer_safety](#get_pointer_safety)|[get_temporary_buffer](#get_temporary_buffer)|[make_shared](#make_shared)|
|[make_unique](#make_unique)|[owner_less](#owner_less)|[return_temporary_buffer](#return_temporary_buffer)|
|[static_pointer_cast](#static_pointer_cast)|[Swap (C++ Standart Kitaplığı)](#swap)|[undeclare_no_pointers](#undeclare_no_pointers)|
|[undeclare_reachable](#undeclare_reachable)|[uninitialized_copy](#uninitialized_copy)|[uninitialized_copy_n](#uninitialized_copy_n)|
|[uninitialized_fill](#uninitialized_fill)|[uninitialized_fill_n](#uninitialized_fill_n)|

## <a name="addressof"></a>  AddressOf

Bir nesnenin doğru adresini alır.

```cpp
template <class T>
T* addressof(T& Val);
```

### <a name="parameters"></a>Parametreler

`Val` Nesne veya işlev için doğru adres edinileceği.

### <a name="return-value"></a>Dönüş Değeri

Nesne ya da başvurduğu işlevi gerçek adresini `Val`bir aşırı yüklenmiş durumunda bile `operator&()` bulunmaktadır.

### <a name="remarks"></a>Açıklamalar

## <a name="align"></a>  Hizalama

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

`Alignment` Girişiminde hizalama bağlı.

`Size` Hizalanmış depolama için bayt cinsinden boyutu.

`Ptr` Başlangıç adresi kullanılabilir bitişik depolama havuzunun kullanın. Bu parametre bir çıktı parametresi de olduğu ve hizalama başarılı olursa yeni başlangıç adresi içerecek şekilde ayarlayın. Varsa `align()` olduğu başarısız, bu parametre değiştirilmez.

`Space` Kullanılabilir toplam alanı `align()` hizalanmış depolama oluşturmada kullanılacak. Bu parametre aynı zamanda bir çıktı parametresidir ve hizalanmış depolamanın ve herhangi ilişkili ek yükün çıkarılmasının ardından depolama arabelleğinde kalan düzenlenmiş alanı içerir.

Varsa `align()` olduğu başarısız, bu parametre değiştirilmez.

### <a name="return-value"></a>Dönüş Değeri

İstenen hizalanmış arabellek, kullanılabilir alanı uygun değildir, boş bir işaretçi; Aksi takdirde yeni değeri `Ptr`.

### <a name="remarks"></a>Açıklamalar

Değiştirilen `Ptr` ve `Space` parametrelerini çağırmak etkinleştirme `align()` tekrar tekrar üzerinde büyük olasılıkla için farklı değerler ile aynı arabellek `Alignment` ve `Size`. Aşağıdaki kod parçacığını bir kullanımını göstermektedir `align()`.

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

## <a name="allocate_shared"></a>  allocate_shared

Oluşturur bir `shared_ptr` ayrılmış ve verilen bir tür için belirtilen ayırıcısı kullanılarak oluşturulan nesneler için. Döndürür `shared_ptr`.

```cpp
template <class Type, class Allocator, class... Types>
shared_ptr<Type>
allocate_shared(Allocator Alloc, Types&&... Args);
```

### <a name="parameters"></a>Parametreler

`Alloc` Nesneleri oluşturmak için kullanılan ayırıcısı.

`Args` Nesneleri hale sıfır veya daha fazla bağımsız değişkenler.

### <a name="remarks"></a>Açıklamalar

İşlev nesnesi oluşturur `shared_ptr<Type>`, bir işaretçi `Type(Args...)` olarak ayrılmış ve tarafından oluşturulan `Alloc`.

## <a name="const_pointer_cast"></a>  const_pointer_cast

Shared_ptr const dönüştürme.

```cpp
template <class Ty, class Other>
shared_ptr<Ty>
const_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parametreler

`Ty` Döndürülen paylaşılan işaretçiyi tarafından denetlenen türü.

`Other` Bağımsız değişken paylaşılan işaretçiyi tarafından denetlenen türü.

`Other` Bağımsız değişken paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi boş shared_ptr nesneyi döndürür `const_cast<Ty*>(sp.get())` null işaretçi; döndüren Aksi takdirde döndürür bir [shared_ptr sınıfı](../standard-library/shared-ptr-class.md)\<Ty > tarafından sahip olunan kaynağına sahip nesne `sp`. İfade `const_cast<Ty*>(sp.get())` geçerli olmalıdır.

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

## <a name="declare_no_pointers"></a>  declare_no_pointers

Bellek bloğu karakterleri taban adresi işaretçi tarafından tanımlanan bir atık toplayıcı bildirir ve blok boyutu hiçbir izlenebilir işaretçileri içerir.

```cpp
void declare_no_pointers(
    char* ptr,
    size_t _Size);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`ptr`|Artık izlenebilir işaretçileri içeren ilk karakter adresidir.|
|`_Size`|Başlar blok boyutunu `ptr` hiçbir izlenebilir işaretçileri içerir.|

### <a name="remarks"></a>Açıklamalar

Çöp toplayıcı işlevi bildirir, adres aralığını `[ ptr, ptr + _Size)` artık izlenebilir işaretçileri içerir. (Ayrılan depolama alanı için tüm işaretçiler ulaşılabilir kılmadığınız sürece başvuru yapıldı gereken değil.)

## <a name="declare_reachable"></a>  declare_reachable

Belirtilen adresin ayrılmış depolama alanını ve erişilebilir olduğunu atık toplamaya bildirir.

```cpp
void declare_reachable(void* ptr);
```

### <a name="parameters"></a>Parametreler

`ptr` Bir işaretçi ulaşılabilir, ayrılmış, geçerli bir depolama alanı.

### <a name="remarks"></a>Açıklamalar

Varsa `ptr` işlevi herhangi atık toplayıcı bildirir null değil, `ptr` bundan böyle erişilebilir (noktalarına geçerli ayrılan depolama alanı) değil.

## <a name="default_delete"></a>  default_delete

İle ayrılmış nesneleri siler `operator new`. İle kullanılmak üzere uygun `unique_ptr`.

```cpp
struct default_delete {
   constexpr default_delete() noexcept = default;
   template <class Other, class = typename enable_if<is_convertible<Other*, T*>::value, void>::type>>
   default_delete(const default_delete<Other>&) noexcept;
   void operator()(T* Ptr) const noexcept;
};
```

### <a name="parameters"></a>Parametreler

`Ptr` Silinecek nesne işaretçisi.

Diğer silinecek dizisindeki öğelerin türü.

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı açıklayan bir `deleter` ile ayrılmış skaler nesneleri siler `operator new`, Şablon sınıfı ile kullanım için uygun `unique_ptr`. Ayrıca açık uzmanlık sahip `default_delete<Type[]>`.

## <a name="dynamic_pointer_cast"></a>  dynamic_pointer_cast

Dinamik atama shared_ptr için.

```cpp
template <class Ty, class Other>
shared_ptr<Ty>
dynamic_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parametreler

`Ty` Döndürülen paylaşılan işaretçiyi tarafından denetlenen türü.

`Other` Bağımsız değişken paylaşılan işaretçiyi tarafından denetlenen türü.

`sp` Bağımsız değişken paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi boş shared_ptr nesneyi döndürür `dynamic_cast<Ty*>(sp.get())` null işaretçi; döndüren Aksi takdirde döndürür bir [shared_ptr sınıfı](../standard-library/shared-ptr-class.md)\<Ty > tarafından sahip olunan kaynağına sahip nesne `sp`. İfade `dynamic_cast<Ty*>(sp.get())` geçerli olmalıdır.

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

## <a name="get_deleter"></a>  get_deleter

Silici shared_ptr alın.

```cpp
template <class D, class Ty>
D* get_deleter(const shared_ptr<Ty>& sp);
```

### <a name="parameters"></a>Parametreler

`D` Silici türü.

`Ty` Paylaşılan işaretçiyi tarafından denetlenen türü.

`sp` Paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

İşaretçi türü Silici için şablon işlevi döndüren `D` ait olan [shared_ptr sınıfı](../standard-library/shared-ptr-class.md) nesne `sp`. Varsa `sp` hiçbir Silici sahip veya kendi Silici türü değilse `D` işlevi 0 değerini döndürür.

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

## <a name="get_pointer_safety"></a>  get_pointer_safety

Herhangi bir atık toplayıcısı tarafından kabul edilen işaretçi güvenlik türünü döndürür.

```cpp
pointer_safety get_pointer_safety();
```

### <a name="remarks"></a>Açıklamalar

İşlev işaretçisi güvenliği herhangi otomatik atık toplayıcısı tarafından kabul türünü döndürür.

## <a name="get_temporary_buffer"></a>  get_temporary_buffer

Belirli sayıda öğeyi aşmayan öğe dizisi için geçici depolamayı ayırır.

```cpp
template <class Type>
pair<Type *, ptrdiff_t> get_temporary_buffer(ptrdiff_t count);
```

### <a name="parameters"></a>Parametreler

`count` En fazla öğe sayısı için bellek tahsis edilecek olduğu istedi.

### <a name="return-value"></a>Dönüş Değeri

A `pair` , ilk bileşendir ayrılmış ve ikinci bileşeni verir depolamak öğelerin en büyük sayıyı gösteren arabelleğin boyutu bellek işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bellek için bir istek işlevi yapar ve başarılı olmayabilir. Hiçbir arabellek ayırdığınızda, işlevi sıfır olarak ikinci bileşen eşittir ve null işaretçinin ilk bileşen eşit bir çift döndürür.

Bu işlev yalnızca geçici bellek için kullanılmalıdır.

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

## <a name="make_shared"></a>  make_shared

Oluşturur ve döndüren bir `shared_ptr` varsayılan ayırıcıyı kullanarak sıfır veya daha fazla bağımsız değişkenlerden oluşturulan ayrılmış nesneleri işaret. Ayırır ve her iki bir nesne belirtilen türe ait oluşturur ve bir `shared_ptr` nesne ve döndürür paylaşılan sahipliğini yönetmek için `shared_ptr`.

```cpp
template <class Type, class... Types>
shared_ptr<Type>
make_shared(Types&&... _Args);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`_Args`|Sıfır veya daha fazla oluşturucu bağımsız değişkenleri. İşlevi çağırmak için hangi Oluşturucusu aşırı sağlanan bağımsız değişkenler temel oluşturur.|

### <a name="remarks"></a>Açıklamalar

Kullanım `make_shared` nesne oluşturmak için basit ve daha verimli bir yol olarak ve bir `shared_ptr` aynı zamanda paylaşılan erişim nesnesine yönetmek için. Anlam olarak, bu iki ifade eşdeğerdir:

```cpp
auto sp = std::shared_ptr<Example>(new Example(argument));
auto msp = std::make_shared<Example>(argument);
```

Ancak, ilk ifade iki ayırmaları yapar ve ayrılması `shared_ptr` sonra ayrılması başarısız `Example` nesne başarılı, ardından adlandırılmamış `Example` nesne sızmasını. Kullanan deyimi `make_shared` söz konusu yalnızca bir işlev çağrısı olduğundan daha kolaydır. Kitaplık nesnesi ve akıllı işaretçi için tek bir ayırma yapabilirsiniz olduğundan daha verimli olur. Bu hem de daha hızlı ve daha az bellek parçalanması müşteri adayları ve herhangi bir ayırma, ancak diğer özel durum olasılığı vardır. Performans nesnesi ve akıllı işaretçi başvuru sayılarını güncelleştirmeleri başvuran kodu daha iyi yerleşim yeri tarafından sunulur.

Kullanmayı [make_unique](../standard-library/memory-functions.md#make_unique) paylaşılan erişim nesnesine ihtiyacınız yoksa. Kullanım [allocate_shared](../standard-library/memory-functions.md#allocate_shared) nesne için özel bir ayırıcı belirtmeniz gerekiyorsa. Kullanamazsınız `make_shared` Silici bağımsız değişken olarak geçirmek için hiçbir şekilde olduğundan, nesne özel bir Silici gerektiriyorsa.

Aşağıdaki örnek, belirli Oluşturucusu aşırı çağırarak bir türü paylaşılan işaretçileri oluşturulacağını gösterir.

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

Örneğin bu çıkışı üretir:

```Output
Playing Ode to Joy by Beethoven, use count: 2
Playing Yesterday by The Beatles, use count: 3
Playing Blackbird by The Beatles, use count: 3
Playing Greensleeves by Unknown, use count: 2
Playing Yesterday by The Beatles, use count: 3
Playing Blackbird by The Beatles, use count: 3
```

## <a name="make_unique"></a>  make_unique

Oluşturur ve döndüren bir [unique_ptr](../standard-library/unique-ptr-class.md) belirtilen türe ait bir nesneye hangi yapılandırılmıştır belirtilen bağımsız değişkenler kullanarak.

```cpp
// make_unique<T>
template <class T, class... Types>
unique_ptr<T>
make_unique(Types&&... Args)
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
typename enable_if<extent<T>::value != 0, void>::type
make_unique(Types&&...) = delete;
```

### <a name="parameters"></a>Parametreler

`T` Nesne türü, `unique_ptr` işaret edecek.

`Types` Tarafından belirtilen bir oluşturucu bağımsız değişken türleri `Args`.

`Args` Nesne türünün oluşturucuya geçirilecek bağımsız değişkenler `T`.

`Elem` Bir dizi türündeki öğeler `T`.

`Size` Yeni bir dizi için alan ayırmak için öğe sayısı.

### <a name="remarks"></a>Açıklamalar

İlk aşırı tek nesneler için kullanılır, ikinci aşırı diziler için çağrılır ve üçüncü aşırı engeller tür bağımsız değişkeni bir dizi boyutu belirtmelerini engeller (make_unique\<T [N] >); bu yapım desteklenmiyor Geçerli standardına göre. Kullandığınızda `make_unique` oluşturmak için bir `unique_ptr` dizi öğeleri ayrı olarak başlatmak kullandığınız bir dizi için. Bu aşırı yüklemeyi düşünüyorsanız, belki de daha iyi bir seçim kullanmaktır bir [std::vector](../standard-library/vector-class.md).

Çünkü `make_unique` dikkatle olan özel durum güvenliği için uygulanan kullanmanızı öneririz `make_unique` doğrudan çağırmak yerine `unique_ptr` oluşturucular.

### <a name="example"></a>Örnek

Aşağıdaki örnekte nasıl kullanılacağını gösterir `make_unique`. Daha fazla örnek için bkz: [nasıl yapılır: unique_ptr örnekleri oluşturma ve kullanma](../cpp/how-to-create-and-use-unique-ptr-instances.md).

[!code-cpp[stl_smart_pointers#214](../cpp/codesnippet/CPP/memory-functions_1.cpp)]

Hata C2280 birlikte gördüğünüzde bir `unique_ptr`, neredeyse kesinlikle olduğu silinmiş bir işlevdir kopya kurucusu çağrılacak denediğinizden.

## <a name="owner_less"></a>  owner_less

Paylaşılan ve zayıf işaretçilerin sahiplik temelli karışık karşılaştırmalarını sağlar. Döndürür `true` sol parametre üye işlevi tarafından önce sağ parametre sıralı varsa `owner_before`.

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

`_left` Paylaşılan veya zayıf işaretçi.

`right` Paylaşılan veya zayıf işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon sınıfları döndürme olarak kendi üye işleçleri tanımlamak `left.owner_before(right)`.

## <a name="return_temporary_buffer"></a>  return_temporary_buffer

Kullanılarak ayrıldı geçici bellek kaldırır `get_temporary_buffer` şablon işlevi.

```cpp
template <class Type>
void return_temporary_buffer(Type* _Pbuf);
```

### <a name="parameters"></a>Parametreler

*_Pbuf* bırakılmasına bellek işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca geçici bellek için kullanılmalıdır.

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

## <a name="static_pointer_cast"></a>  static_pointer_cast

Shared_ptr statik dönüştürme.

```cpp
template <class Ty, class Other>
shared_ptr<Ty>
static_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parametreler

`Ty` Döndürülen paylaşılan işaretçiyi tarafından denetlenen türü.

`Other` Bağımsız değişken paylaşılan işaretçiyi tarafından denetlenen türü.

`Other` Bağımsız değişken paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi boş shared_ptr nesneyi döndürür `sp` bir boş `shared_ptr` nesne; Aksi halde döndürür bir [shared_ptr sınıfı](../standard-library/shared-ptr-class.md)\<Ty > tarafından aitkaynaksahibinesnesi`sp`. İfade `static_cast<Ty*>(sp.get())` geçerli olmalıdır.

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

## <a name="swap"></a>  Swap (C++ Standart Kitaplığı)

İki shared_ptr veya weak_ptr nesneleri değiştirme.

```cpp
template <class Ty, class Other>
void swap(shared_ptr<Ty>& left, shared_ptr<Other>& right);

template <class Ty, class Other>
void swap(weak_ptr<Ty>& left, weak_ptr<Other>& right);
```

### <a name="parameters"></a>Parametreler

`Ty` Sol paylaşılan zayıf işaretçiyi tarafından denetlenen türü.

`Other` Sağ paylaşılan/zayıf işaretçiyi tarafından denetlenen türü.

`left` Sol paylaşılan zayıf işaretçi.

`right` Sağ paylaşılan/zayıf işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevleri çağrı `left.swap(right)`.

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

## <a name="undeclare_no_pointers"></a>  undeclare_no_pointers

Taban adresi işaretçisi ve blok boyutu tarafından bellek bloğuna tanımlanan Bellek bloğu karakterlerin artık izlenebilir işaretçileri içerebileceğini atık toplayıcıya bildirir.

```cpp
void undeclare_no_pointers(
    char* ptr,
    size_t _Size);
```

### <a name="remarks"></a>Açıklamalar

Çöp toplayıcı işlevi bildirir, adres aralığını `[ptr, ptr + _Size)` izlenebilir işaretçileri şimdi içerebilir.

## <a name="undeclare_reachable"></a>  undeclare_reachable

Belirtilen bellek konumu için ulaşılabilirlik bildirimini iptal eder.

```cpp
template <class Type>
Type *undeclare_reachable(Type* ptr);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`ptr`|Erişilebilir değil belirtilecek bellek adresi için bir işaretçi.|

### <a name="remarks"></a>Açıklamalar

Varsa `ptr` değil `nullptr`, tüm atık toplayıcı işlevi bildirir, `ptr` artık erişilebilir değil. Karşılaştırır güvenle türetilmiş bir işaretçi eşit döndüren `ptr`.

## <a name="uninitialized_copy"></a>  uninitialized_copy

Nesneleri belirli bir kaynak aralığından başlatılmamış hedef aralığına kopyalar.

```cpp
template <class InputIterator, class ForwardIterator>
ForwardIterator uninitialized_copy(InputIterator first, InputIterator last, ForwardIterator dest);
```

### <a name="parameters"></a>Parametreler

`first` Kaynak aralığındaki ilk öğe adresleme giriş yineleyici.

`last` Kaynak aralığı son öğesi adresleme giriş yineleyici.

`dest` Hedef aralık ilk öğe adresleme iletme yineleyici.

### <a name="return-value"></a>Dönüş Değeri

Kaynak aralığı boş değilse hedef aralık ötesinde ilk konum adresleme iletme yineleyici.

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

## <a name="uninitialized_copy_n"></a>  uninitialized_copy_n

Bir girdi yineleyicisinde belirtilen öğe sayısının bir kopyasını oluşturur. Kopyalar ileri doğru bir yineleyicinin içine yerleştirilir.

```cpp
template <class InputIterator, class Size, class ForwardIterator>
ForwardIterator uninitialized_copy_n(
    InputIterator first,
    Size count,
    ForwardIterator dest);
```

### <a name="parameters"></a>Parametreler

`first` Bir giriş yineleyici kopyalamak için bir nesneye başvuruyor.

`count` Nesneyi kopyalamak için kaç kez yineleneceğini belirten bir işaretli veya işaretsiz tamsayı yazın.

`dest` Yeni kopya nereye başvuruyor iletme yineleyici.

### <a name="return-value"></a>Dönüş Değeri

Hedefin ötesindeki ilk konuma yönelen ileri doğru yineleyici. Kaynak aralığı boşsa, yineleyici adresleri `first`.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi etkin şekilde aşağıdakileri yürütür:

```cpp
    for (; 0 < count; --count)
        new (static_cast<void*>(&* dest++))
            typename iterator_traits<InputIterator>::value_type(*first++);
    return dest;
```

Kod bir özel durum oluşturmadıkça. Bu durumda, tüm oluşturulmuş nesneler yok edilir ve özel durum yeniden oluşur.

## <a name="uninitialized_fill"></a>  uninitialized_fill

Belirli bir değerin nesnelerini başlatılmamış hedef aralığına kopyalar.

```cpp
template <class ForwardIterator, class Type>
void uninitialized_fill(ForwardIterator first, ForwardIterator last, const Type& val);
```

### <a name="parameters"></a>Parametreler

`first` Başlatma için hedef aralık ilk öğe adresleme iletme yineleyici.

`last` Başlatma için hedef aralığın son öğesi adresleme iletme yineleyici.

`val` Hedef aralık başlatmak için kullanılan değer.

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

## <a name="uninitialized_fill_n"></a>  uninitialized_fill_n

Belirli bir değerin nesnelerini belirli sayıda öğenin başlatılmamış hedef aralığı içine kopyalar.

```cpp
template <class FwdIt, class Size, class Type>
void uninitialized_fill_n(ForwardIterator first, Size count, const Type& val);
```

### <a name="parameters"></a>Parametreler

`first` Başlatma için hedef aralık ilk öğe adresleme bir iletme yineleyici.

`count` Başlatılacak öğe sayısı.

`val` Hedef aralık başlatmak için kullanılan değer.

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

## <a name="see-also"></a>Ayrıca bkz.

[\<bellek >](../standard-library/memory.md)<br/>
