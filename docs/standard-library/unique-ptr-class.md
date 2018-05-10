---
title: unique_ptr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08e2505a77643053c60c4ce1a164dc89cc1e0952
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="uniqueptr-class"></a>unique_ptr Sınıfı

Bir işaretçi ait nesne veya dizi depolar. Nesne/dizisi tarafından başka ait `unique_ptr`. Nesne/dizisinin kaldırıldığı zaman `unique_ptr` yok.

## <a name="syntax"></a>Sözdizimi

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

`Right` A `unique_ptr`.

`Nptr` Bir `rvalue` türü `std::nullptr_t`.

`Ptr` A `pointer`.

`Deleter` A `deleter` bağlı işlevi bir `unique_ptr`.

## <a name="exceptions"></a>Özel Durumlar

Hiçbir özel durum tarafından oluşturulan `unique_ptr`.

## <a name="remarks"></a>Açıklamalar

`unique_ptr` Sınıfı yerini `auto_ptr`ve C++ Standart Kitaplığı kapsayıcıların bir öğe kullanılabilir.

Kullanım [make_unique](../standard-library/memory-functions.md#make_unique) verimli bir şekilde yeni örneklerini oluşturmak için yardımcı işlevini `unique_ptr`.

`unique_ptr` benzersiz bir kaynak yönetir. Her `unique_ptr` nesne sahibi veya null işaretçi depolar nesnesine bir işaretçi depolar. Bir kaynak en fazla bir sahip olabileceği `unique_ptr` nesne;  zaman bir `unique_ptr` belirli bir kaynak sahibi nesnesi yok, kaynak serbest bırakılır. A `unique_ptr` nesnesi taşınır, ancak kopyalanmaz;  Daha fazla bilgi için bkz: [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

Kaynak bir saklı çağırarak serbest `deleter` nesne türü `Del` için belirli bir kaynaklarının nasıl ayrıldığını bilir `unique_ptr`. Varsayılan `deleter` `default_delete<T>` kaynak gösterdiği olduğunu varsayar `ptr` ile ayrılan `new`, ve çağırarak boşaltılması `delete _Ptr`. (Kısmi uzmanlığı `unique_ptr<T[]>`ile ayrılmış dizi nesneleri yönetir `new[]`, ve varsayılan `deleter` `default_delete<T[]>`, özelleştirilmiş çağrılacak delete [] `ptr`.)

Saklı işaretçinin ait bir kaynağa `stored_ptr` türüne sahip `pointer`. Bu `Del::pointer` tanımlanmışsa, ve `T *` değilse. Saklı `deleter` nesne `stored_deleter` varsa nesnesindeki hiçbir yer kaplar `deleter` durum bilgisiz mi. Unutmayın `Del` bir başvuru türü olabilir.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[unique_ptr](#unique_ptr)|Yedi oluşturucuları için vardır `unique_ptr`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[deleter_type](#deleter_type)|Şablon parametresi için bir eş anlamlı `Del`.|
|[element_type](#element_type)|Şablon parametresi için bir eş anlamlı `T`.|
|[İşaretçi](#pointer)|Eşanlamlısı `Del::pointer` , aksi takdirde tanımlanmışsa `T *`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[get](#get)|Döndürür `stored_ptr`.|
|[get_deleter](#get_deleter)|Bir başvuru döndürür `stored_deleter`.|
|[Sürüm](#release)|depolar `pointer()` içinde `stored_ptr` ve önceki içeriğini döndürür.|
|[Sıfırla](#reset)|Şu anda sahip olunan kaynağı yayınlar ve yeni bir kaynağı kabul eder.|
|[Değiştirme](#swap)|Kaynak alış verişleri ve `deleter` sağlanan ile `unique_ptr`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|`operator bool`|İşleç parametresinin bir türde bir değer döndürür `bool`. Dönüştürme sonucu `bool` olan `true` zaman `get() != pointer()`, aksi takdirde `false`.|
|`operator->`|Üye işlevi döndürür `stored_ptr`.|
|`operator*`|Üye işlevi döndürür `*stored_ptr`.|
|[unique_ptr işleç =](#unique_ptr_operator_eq)|Değeri atar bir `unique_ptr` (veya bir `pointer-type`) geçerli `unique_ptr`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="deleter_type"></a>  deleter_type

Şablon parametresi için bir eş anlamlı türüdür `Del`.

```cpp
typedef Del deleter_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür `Del`.

## <a name="element_type"></a>  ELEMENT_TYPE

Şablon parametresi için bir eş anlamlı türüdür `Type`.

```cpp
typedef Type element_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür `Ty`.

## <a name="get"></a>  unique_ptr::get

Döndürür `stored_ptr`.

```cpp
pointer get() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `stored_ptr`.

## <a name="get_deleter"></a>  unique_ptr::get_deleter

Bir başvuru döndürür `stored_deleter`.

```cpp
Del& get_deleter();

const Del& get_deleter() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi bir başvuru döndürür `stored_deleter`.

## <a name="unique_ptr_operator_eq"></a>  unique_ptr işleç =

Sağlanan adresini atar `unique_ptr` geçerli bir.

```cpp
unique_ptr& operator=(unique_ptr&& right);
template <class U, Class Del2>
unique_ptr& operator=(unique_ptr<Type, Del>&& right);
unique_ptr& operator=(pointer-type);
```

### <a name="parameters"></a>Parametreler

A `unique_ptr` geçerli değeri atamak için kullanılan başvuru `unique_ptr`.

### <a name="remarks"></a>Açıklamalar

Üye işlevlerini çağrısı `reset(right.release())` ve taşıma `right.stored_deleter` için `stored_deleter`, ardından dönüş `*this`.

## <a name="pointer"></a>  İşaretçi

Eşanlamlısı `Del::pointer` , aksi takdirde tanımlanmışsa `Type *`.

```cpp
typedef T1 pointer;
```

### <a name="remarks"></a>Açıklamalar

Eşanlamlısı türüdür `Del::pointer` , aksi takdirde tanımlanmışsa `Type *`.

## <a name="release"></a>  unique_ptr::Release

Çağırana döndürülen saklı işaretçi sahipliğini serbest bırakır ve saklı işaretçi değeri ayarlar `nullptr`.

```cpp
pointer release();
```

### <a name="remarks"></a>Açıklamalar

Kullanım `release` tarafından depolanan ham işaretçi sahipliğini üzerinden yapılacak `unique_ptr`. Döndürülen işaretçi silinmek üzere çağıran sorumludur. `unique-ptr` Boş varsayılan oluşturulan durumuna ayarlanır. Uyumlu türünde başka bir işaretçi atayabilirsiniz `unique_ptr` çağrısından sonra `release`.

### <a name="example"></a>Örnek

Bu örnek nasıl döndürülen nesne için yayın çağıran sorumludur gösterir:

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

Bilgisayar çıkışı:

```Output
Constructing Sample(3)
Constructing Sample(42)
Deleting Sample(42)
Deleting Sample(3)

```

## <a name="reset"></a>  unique_ptr::reset

İşaretçi parametresi sahipliğini alır ve özgün saklı işaretçiyi siler. Yeni işaretçi özgün saklı işaretçiyi aynı olduğunda `reset` işaretçinin siler ve saklı işaretçi ayarlar `nullptr`.

```cpp
void reset(pointer ptr = pointer());
void reset(nullptr_t ptr);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`ptr`|Kaynak sahipliğini almak için bir işaretçi.|

### <a name="remarks"></a>Açıklamalar

Kullanım `reset` saklı değiştirmek için [işaretçi](#pointer) sahibi `unique_ptr` için `ptr` ve özgün saklı işaretçi silin. Varsa `unique_ptr` boş değildi `reset` tarafından döndürülen Silici işlevi çağırır [get_deleter](#get_deleter) özgün saklı işaretçi üzerinde.

Çünkü `reset` önce yeni işaretçi depolar `ptr`, özgün saklı işaretçiyi siler mümkündür `reset` hemen silinecek `ptr` özgün saklı işaretçisi ile aynı olduğunda.

## <a name="swap"></a>  unique_ptr::Swap

Alış verişleri iki arasında işaretçileri `unique_ptr` nesneleri.

```cpp
void swap(unique_ptr& right);
```

### <a name="parameters"></a>Parametreler

`right` A `unique_ptr` işaretçileri takas etmek için kullanılır.

### <a name="remarks"></a>Açıklamalar

Üye işlevini değiştirir `stored_ptr` ile `right.stored_ptr` ve `stored_deleter` ile `right.stored_deleter`.

## <a name="unique_ptr"></a>  unique_ptr::unique_ptr

Yedi oluşturucuları için vardır `unique_ptr`.

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

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`ptr`|Atanan kaynak için bir işaretçi bir `unique_ptr.`|
|`_Deleter`|A `deleter` atanacak bir `unique_ptr`.|
|`right`|Bir `rvalue reference` için bir `unique_ptr` içinden `unique_ptr` alanlardır yeni oluşturulan atanan taşıma `unique_ptr`.|

### <a name="remarks"></a>Açıklamalar

İlk iki oluşturucular hiçbir kaynak yöneten bir nesne oluşturur. Üçüncü Oluşturucusu depoları `ptr` içinde `stored_ptr`. Dördüncü Oluşturucusu depoları `ptr` içinde `stored_ptr` ve `deleter` içinde `stored_deleter`.

Beşinci Oluşturucusu depoları `ptr` içinde `stored_ptr` ve taşır `deleter` içine `stored_deleter`. Altıncı ve yedinci oluşturucular deposu `right.release()` içinde `stored_ptr` ve taşır `right.get_deleter()` içine `stored_deleter`.

## <a name="dtorunique_ptr"></a>  unique_ptr ~ unique_ptr

Yıkıcı için `unique_ptr`, bozar bir `unique_ptr` nesnesi.

```cpp
~unique_ptr();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çağrıları `get_deleter()(stored_ptr)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<bellek >](../standard-library/memory.md)<br/>
