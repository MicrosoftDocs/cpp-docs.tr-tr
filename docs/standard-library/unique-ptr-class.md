---
title: unique_ptr Sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory/std::unique_ptr
- memory/std::unique_ptr::deleter_type
- memory/std::unique_ptr::element_type
- memory/std::unique_ptr::pointer
- memory/std::unique_ptr::get
- memory/std::unique_ptr::get_deleter
- memory/std::unique_ptr::release
- memory/std::unique_ptr::reset
- memory/std::unique_ptr::swap
helpviewer_keywords:
- std::unique_ptr [C++]
- std::unique_ptr [C++], deleter_type
- std::unique_ptr [C++], element_type
- std::unique_ptr [C++], pointer
- std::unique_ptr [C++], get
- std::unique_ptr [C++], get_deleter
- std::unique_ptr [C++], release
- std::unique_ptr [C++], reset
- std::unique_ptr [C++], swap
ms.assetid: acdf046b-831e-4a4a-83aa-6d4ee467db9a
ms.openlocfilehash: 694ea94ac0e9dcd31d89a3a83bd3400bac3e8e4f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222192"
---
# <a name="unique_ptr-class"></a>unique_ptr Sınıfı

Bir işaretçiyi sahip bir nesne veya diziye depolar. Nesne/dizi başka hiçbir değildir `unique_ptr` . Nesne/dizi yok edildiğinde yok edilir `unique_ptr` .

## <a name="syntax"></a>Söz dizimi

```cpp
class unique_ptr {
public:
    unique_ptr();
    unique_ptr(nullptr_t Nptr);
    explicit unique_ptr(pointer Ptr);
    unique_ptr(pointer Ptr,
        typename conditional<is_reference<Del>::value, Del,
        typename add_reference<const Del>::type>::type Deleter);
    unique_ptr(pointer Ptr,
        typename remove_reference<Del>::type&& Deleter);
    unique_ptr(unique_ptr&& Right);
    template <class T2, Class Del2>
    unique_ptr(unique_ptr<T2, Del2>&& Right);
    unique_ptr(const unique_ptr& Right) = delete;
    unique_ptr& operator=(const unique_ptr& Right) = delete;
};

//Specialization for arrays:
template <class T, class D>
class unique_ptr<T[], D> {
public:
    typedef pointer;
    typedef T element_type;
    typedef D deleter_type;
    constexpr unique_ptr() noexcept;
    template <class U>
    explicit unique_ptr(U p) noexcept;
    template <class U>
    unique_ptr(U p, see below d) noexcept;
    template <class U>
    unique_ptr(U p, see below d) noexcept;
    unique_ptr(unique_ptr&& u) noexcept;
    constexpr unique_ptr(nullptr_t) noexcept : unique_ptr() { }     template <class U, class E>
        unique_ptr(unique_ptr<U, E>&& u) noexcept;
    ~unique_ptr();
    unique_ptr& operator=(unique_ptr&& u) noexcept;
    template <class U, class E>
    unique_ptr& operator=(unique_ptr<U, E>&& u) noexcept;
    unique_ptr& operator=(nullptr_t) noexcept;
    T& operator[](size_t i) const;

    pointer get() const noexcept;
    deleter_type& get_deleter() noexcept;
    const deleter_type& get_deleter() const noexcept;
    explicit operator bool() const noexcept;
    pointer release() noexcept;
    void reset(pointer p = pointer()) noexcept;
    void reset(nullptr_t = nullptr) noexcept;
    template <class U>
    void reset(U p) noexcept = delete;
    void swap(unique_ptr& u) noexcept;  // disable copy from lvalue unique_ptr(const unique_ptr&) = delete;
    unique_ptr& operator=(const unique_ptr&) = delete;
};
```

### <a name="parameters"></a>Parametreler

*Right*\
Bir `unique_ptr`.

*Nptr*\
Bir `rvalue` tür `std::nullptr_t` .

*Kaydetmeye*\
Bir `pointer`.

*Silici*\
`deleter`Bir öğesine bağlanan bir işlev `unique_ptr` .

## <a name="exceptions"></a>Özel durumlar

Tarafından hiçbir özel durum oluşturulmaz `unique_ptr` .

## <a name="remarks"></a>Açıklamalar

`unique_ptr`Sınıfı yerine geçer `auto_ptr` ve C++ standart kitaplık kapsayıcılarının bir öğesi olarak kullanılabilir.

Yeni örneklerini etkin bir şekilde oluşturmak için [make_unique](../standard-library/memory-functions.md#make_unique) yardımcı işlevini kullanın `unique_ptr` .

`unique_ptr`bir kaynağı benzersiz bir şekilde yönetir. Her `unique_ptr` nesne, sahip olduğu veya bir null işaretçiyi depolayan nesnesine bir işaretçi depolar. Bir kaynak, birden fazla nesneye sahip olamaz `unique_ptr` ;  `unique_ptr`belirli bir kaynağa sahip bir nesne yok edildiğinde, kaynak serbest bırakılır. Bir `unique_ptr` nesne taşınabilir, ancak kopyalanmayabilir;  daha fazla bilgi için bkz. [rvalue başvuru bildirimci:  &&](../cpp/rvalue-reference-declarator-amp-amp.md).

Kaynak, `deleter` `Del` kaynakların belirli bir için nasıl ayrıldığını bilen bir depolanmış nesne çağırarak serbest bırakılır `unique_ptr` . Varsayılan değer, `deleter` `default_delete<T>` tarafından işaret `ptr` edilen kaynağın ile ayrıldığı **`new`** ve çağırarak boşaltılabileceği varsayılmaktadır `delete _Ptr` . (Kısmi bir özelleşme `unique_ptr<T[]>` , ile ayrılmış dizi nesnelerini yönetir `new[]` ve varsayılan olan `deleter` `default_delete<T[]>` , delete [] çağrısı için özelleşmiş bir değer içerir `ptr` .)

Sahip olunan bir kaynağa ait saklı işaretçi `stored_ptr` türü `pointer` . `Del::pointer`Tanımlıysa ve yoksa `T *` . Saklı `deleter` nesne, `stored_deleter` durum bilgisiz ise nesnede boş alan kaplar `deleter` . `Del`Bir başvuru türü olabileceğini unutmayın.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[unique_ptr](#unique_ptr)|İçin yedi Oluşturucu vardır `unique_ptr` .|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[deleter_type](#deleter_type)|Şablon parametresi için bir eş anlamlı `Del` .|
|[element_type](#element_type)|Şablon parametresi için bir eş anlamlı `T` .|
|[pointer](#pointer)|Tanımlanmışsa için bir eş anlamlı `Del::pointer` , aksi durumda `T *` .|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[Al](#get)|`stored_ptr` döndürür.|
|[get_deleter](#get_deleter)|Öğesine bir başvuru döndürür `stored_deleter` .|
|[Yayın](#release)|`pointer()`' de depolar `stored_ptr` ve önceki içeriğini döndürür.|
|[döndürmek](#reset)|Şu anda sahip olunan kaynağı yayınlar ve yeni bir kaynağı kabul eder.|
|[Kur](#swap)|Kaynak ve ile birlikte değiş tokuş eder `deleter` `unique_ptr` .|

### <a name="operators"></a>İşleçler

|||
|-|-|
|**işleç bool**|İşleci, dönüştürülebilir bir türün değerini döndürür **`bool`** . Dönüştürmenin sonucu **`bool`** **`true`** `get() != pointer()` , aksi durumda olur **`false`** .|
|`operator->`|Üye işlevi döndürür `stored_ptr` .|
|`operator*`|Üye işlevi döndürür `*stored_ptr` .|
|[işleç =](#unique_ptr_operator_eq)|`unique_ptr`Geçerli bir (veya a `pointer-type` ) değerini geçerli olacak şekilde atar `unique_ptr` .|

### <a name="deleter_type"></a><a name="deleter_type"></a>deleter_type

Tür, şablon parametresi için bir eş anlamlı `Del` .

```cpp
typedef Del deleter_type;
```

#### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Del` .

### <a name="element_type"></a><a name="element_type"></a>element_type

Tür, şablon parametresi için bir eş anlamlı `Type` .

```cpp
typedef Type element_type;
```

#### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Ty` .

### <a name="get"></a><a name="get"></a>Al

`stored_ptr` döndürür.

```cpp
pointer get() const;
```

#### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `stored_ptr` .

### <a name="get_deleter"></a><a name="get_deleter"></a>get_deleter

Öğesine bir başvuru döndürür `stored_deleter` .

```cpp
Del& get_deleter();

const Del& get_deleter() const;
```

#### <a name="remarks"></a>Açıklamalar

Üye işlevi öğesine bir başvuru döndürür `stored_deleter` .

### <a name="operator"></a><a name="unique_ptr_operator_eq"></a>işleç =

Belirtilen adresini geçerli bir adrese atar `unique_ptr` .

```cpp
unique_ptr& operator=(unique_ptr&& right);
template <class U, Class Del2>
unique_ptr& operator=(unique_ptr<Type, Del>&& right);
unique_ptr& operator=(pointer-type);
```

#### <a name="parameters"></a>Parametreler

`unique_ptr`Değerini geçerli değere atamak için kullanılan bir başvuru `unique_ptr` .

#### <a name="remarks"></a>Açıklamalar

Üye işlevleri çağırır `reset(right.release())` ve öğesine taşınır `right.stored_deleter` `stored_deleter` , ardından döndürülür **`*this`** .

### <a name="pointer"></a><a name="pointer"></a>çağrısı

Tanımlanmışsa için bir eş anlamlı `Del::pointer` , aksi durumda `Type *` .

```cpp
typedef T1 pointer;
```

#### <a name="remarks"></a>Açıklamalar

Tür tanımlandıysa için bir eş anlamlı `Del::pointer` , aksi durumda `Type *` .

### <a name="release"></a><a name="release"></a>Yayın

Döndürülen saklı işaretçinin sahipliğini çağırana yayınlar ve saklı işaretçi değerini olarak ayarlar **`nullptr`** .

```cpp
pointer release();
```

#### <a name="remarks"></a>Açıklamalar

`release`Tarafından depolanan ham işaretçinin sahipliğini devralmak için kullanın `unique_ptr` . Çağıran, döndürülen işaretçinin silinmesinden sorumludur. , `unique-ptr` Boş varsayılan olarak oluşturulmuş duruma ayarlanır. ' A yapılan çağrıdan sonra uyumlu türde başka bir işaretçi atayabilirsiniz `unique_ptr` `release` .

#### <a name="example"></a>Örnek

Bu örnek, bir yayın çağıranın döndürülen nesneden nasıl sorumlu olduğunu gösterir:

```cpp
// stl_release_unique.cpp
// Compile by using: cl /W4 /EHsc stl_release_unique.cpp
#include <iostream>
#include <memory>

struct Sample {
   int content_;
   Sample(int content) : content_(content) {
      std::cout << "Constructing Sample(" << content_ << ")" << std::endl;
   }
   ~Sample() {
      std::cout << "Deleting Sample(" << content_ << ")" << std::endl;
   }
};

void ReleaseUniquePointer() {
   // Use make_unique function when possible.
   auto up1 = std::make_unique<Sample>(3);
   auto up2 = std::make_unique<Sample>(42);

   // Take over ownership from the unique_ptr up2 by using release
   auto ptr = up2.release();
   if (up2) {
      // This statement does not execute, because up2 is empty.
      std::cout << "up2 is not empty." << std::endl;
   }
   // We are now responsible for deletion of ptr.
   delete ptr;
   // up1 deletes its stored pointer when it goes out of scope.
}

int main() {
   ReleaseUniquePointer();
}
```

```Output
Constructing Sample(3)
Constructing Sample(42)
Deleting Sample(42)
Deleting Sample(3)
```

### <a name="reset"></a><a name="reset"></a>döndürmek

İşaretçi parametresinin sahipliğini alır ve ardından özgün saklı işaretçiyi siler. Yeni işaretçi özgün saklı işaretçiyle aynıysa, `reset` işaretçiyi siler ve saklı işaretçiyi olarak ayarlar **`nullptr`** .

```cpp
void reset(pointer ptr = pointer());
void reset(nullptr_t ptr);
```

#### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Sahipliğini alacak kaynağa yönelik bir işaretçi.

#### <a name="remarks"></a>Açıklamalar

`reset`' In ' a ait saklı [işaretçiyi](#pointer) değiştirmek için `unique_ptr` kullanın *ptr* ve ardından özgün saklı işaretçiyi silin. `unique_ptr`Boş değilse, `reset` özgün saklı İşaretçisinde [get_deleter](#get_deleter) tarafından döndürülen silici işlevini çağırır.

`reset`İlk olarak yeni işaretçiyi *PTR*'yi sakladığı ve özgün saklı işaretçiyi sildiği için, `reset` özgün saklı işaretçiyle aynı ise *PTR* 'yi hemen silmek mümkündür.

### <a name="swap"></a><a name="swap"></a>Kur

İki nesne arasında işaretçiler değiş tokuş eder `unique_ptr` .

```cpp
void swap(unique_ptr& right);
```

#### <a name="parameters"></a>Parametreler

*Right*\
`unique_ptr`İşaretçileri değiştirmek için kullanılır.

#### <a name="remarks"></a>Açıklamalar

Üye işlevi ile `stored_ptr` `right.stored_ptr` ve ile değiştirir `stored_deleter` `right.stored_deleter` .

### <a name="unique_ptr"></a><a name="unique_ptr"></a>unique_ptr

İçin yedi Oluşturucu vardır `unique_ptr` .

```cpp
unique_ptr();

unique_ptr(nullptr_t);
explicit unique_ptr(pointer ptr);

unique_ptr(
    Type* ptr,
    typename conditional<
    is_reference<Del>::value,
    Del,
    typename add_reference<const Del>::type>::type _Deleter);

unique_ptr(pointer ptr, typename remove_reference<Del>::type&& _Deleter);
unique_ptr(unique_ptr&& right);
template <class Ty2, Class Del2>
    unique_ptr(unique_ptr<Ty2, Del2>&& right);
```

#### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Kendisine atanacak kaynağa yönelik bir işaretçi `unique_ptr` .

*_Deleter*\
Bir `deleter` öğesine atanacak bir `unique_ptr` .

*Right*\
`rvalue reference`Yeni oluşturulan ' a ait olan bir ' a `unique_ptr` ait `unique_ptr` alanları `unique_ptr` .

#### <a name="remarks"></a>Açıklamalar

İlk iki Oluşturucu kaynağı yöneten bir nesne oluşturur. Üçüncü Oluşturucu, içindeki *PTR* 'yi depolar `stored_ptr` . Dördüncü Oluşturucu *PTR* 'yi ve içinde `stored_ptr` depolar `deleter` `stored_deleter` .

Beşinci Oluşturucu içinde *PTR* depolar `stored_ptr` ve içine gider `deleter` `stored_deleter` . ' Deki altıncı ve yedinci oluşturucular ' `right.release()` de depolar `stored_ptr` ve ' a gider `right.get_deleter()` `stored_deleter` .

### <a name="unique_ptr"></a><a name="dtorunique_ptr"></a>~ unique_ptr

Yok edicisi, `unique_ptr` bir nesneyi yok eder `unique_ptr` .

```cpp
~unique_ptr();
```

#### <a name="remarks"></a>Açıklamalar

Yıkıcı çağırır `get_deleter()(stored_ptr)` .
