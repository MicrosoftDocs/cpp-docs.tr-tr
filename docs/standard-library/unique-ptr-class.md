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
ms.openlocfilehash: b0751d7716e2f8587ab410e57c2bea17c5dd3e21
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51520978"
---
# <a name="uniqueptr-class"></a>unique_ptr Sınıfı

Sahip olunan bir nesne veya dizi için bir işaretçi depolar. Nesne/dizisi başka hiçbir işaretçinin sahibi `unique_ptr`. Nesne/dizisi kaldırıldığı zaman `unique_ptr` yok.

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

*sağ*<br/>
A `unique_ptr`.

*Nptr*<br/>
Bir `rvalue` türü `std::nullptr_t`.

*PTR*<br/>
A `pointer`.

*Silici*<br/>
A `deleter` bağlı işlevi bir `unique_ptr`.

## <a name="exceptions"></a>Özel Durumlar

Hiçbir özel durum tarafından oluşturulan `unique_ptr`.

## <a name="remarks"></a>Açıklamalar

`unique_ptr` Sınıfı yerine geçen `auto_ptr`ve bir C++ Standart Kitaplığı kapsayıcıları öğesi olarak kullanılabilir.

Kullanım [make_unique](../standard-library/memory-functions.md#make_unique) verimli bir şekilde yeni bir örneğini oluşturmak için yardımcı işlevini `unique_ptr`.

`unique_ptr` bir kaynağı benzersiz şekilde yönetir. Her `unique_ptr` nesnesi sahip olduğu veya null bir işaretçi depolayan nesneyi bir işaretçi depolar. Bir kaynak en fazla biri tarafından sahiplenilebilir `unique_ptr` nesne;  olduğunda bir `unique_ptr` belirli bir kaynağa sahip nesnesi yok edildiğinde, kaynak serbest bırakılır. A `unique_ptr` nesnesi taşınabilir, ancak kopyalanmaz;  Daha fazla bilgi için [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

Kaynak bir saklı çağırarak serbest `deleter` türündeki nesne `Del` belirli bir için kaynakların nasıl ayrılacağını bilir `unique_ptr`. Varsayılan `deleter` `default_delete<T>` kaynağı işaret ettiği olduğunu varsayar `ptr` atanan `new`, ve onu çağrılarak serbest bırakılabileceğini `delete _Ptr`. (Kısmi özelleştirmede `unique_ptr<T[]>`ile ayrılan dizi nesnelerini yönetir `new[]`, ve varsayılan `deleter` `default_delete<T[]>`delete [] çağırmak için uzmanlaşmış `ptr`.)

Sahip olunan bir kaynakta depolanan işaretçide `stored_ptr` türünde `pointer`. Bu `Del::pointer` tanımlı değilse ve `T *` Aksi takdirde. Depolanan `deleter` nesne `stored_deleter` , nesnede boşluk kapladığı `deleter` durum bilgisi yoktur. Unutmayın `Del` bir başvuru türü olabilir.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[unique_ptr](#unique_ptr)|İçin yedi Oluşturucu vardır `unique_ptr`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[deleter_type](#deleter_type)|Şablon parametresi için bir eşanlamlı `Del`.|
|[element_type](#element_type)|Şablon parametresi için bir eşanlamlı `T`.|
|[İşaretçi](#pointer)|İçin bir eşanlamlı `Del::pointer` tanımlanmış, aksi takdirde, `T *`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[get](#get)|Döndürür `stored_ptr`.|
|[get_deleter](#get_deleter)|Bir başvuru döndürür `stored_deleter`.|
|[Yayın](#release)|depolar `pointer()` içinde `stored_ptr` ve önceki içeriğini döndürür.|
|[Sıfırlama](#reset)|Şu anda sahip olunan kaynağı yayınlar ve yeni bir kaynağı kabul eder.|
|[değiştirme](#swap)|Kaynak birbiriyle değiştirir ve `deleter` ile sağlanan `unique_ptr`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|**bool işleci**|İşleç dönüştürülebilen bir türde bir değer döndürür **bool**. Dönüştürme sonucunu **bool** olduğu **true** olduğunda `get() != pointer()`, aksi takdirde **false**.|
|`operator->`|Üye işlevinin döndürdüğü `stored_ptr`.|
|`operator*`|Üye işlevinin döndürdüğü `*stored_ptr`.|
|[unique_ptr işleç =](#unique_ptr_operator_eq)|Değerini atar bir `unique_ptr` (veya `pointer-type`) geçerli `unique_ptr`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="deleter_type"></a>  deleter_type

Şablon parametresi için bir eşanlamlı türüdür `Del`.

```cpp
typedef Del deleter_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Del`.

## <a name="element_type"></a>  ELEMENT_TYPE

Şablon parametresi için bir eşanlamlı türüdür `Type`.

```cpp
typedef Type element_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Ty`.

## <a name="get"></a>  unique_ptr::get

Döndürür `stored_ptr`.

```cpp
pointer get() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `stored_ptr`.

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

A `unique_ptr` geçerli değerini atamak için kullanılan başvuru `unique_ptr`.

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrısı `reset(right.release())` ve taşıma `right.stored_deleter` için `stored_deleter`, ardından dönüş `*this`.

## <a name="pointer"></a>  İşaretçi

İçin bir eşanlamlı `Del::pointer` tanımlanmış, aksi takdirde, `Type *`.

```cpp
typedef T1 pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `Del::pointer` tanımlanmış, aksi takdirde, `Type *`.

## <a name="release"></a>  unique_ptr::Release

Çağırana döndürülen depolanmış işaretçiyi in sahipliğini bırakır ve depolanan işaretçi değerine ayarlar **nullptr**.

```cpp
pointer release();
```

### <a name="remarks"></a>Açıklamalar

Kullanım `release` tarafından depolanan ham işaretçi sahipliğini üzerinde gerçekleştirilecek `unique_ptr`. Çağıran, döndürülen işaretçi silinmek sorumludur. `unique-ptr` Boş varsayılan oluşturulmuş durumuna ayarlanır. Başka bir işaretçi, uyumlu tür atayabilirsiniz `unique_ptr` çağrısından sonra `release`.

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

İşaretçi parametresi sahipliğini alır ve ardından özgün depolanan işaretçide siler. Özgün depolanan işaretçide, aynı yeni işaretçi ise `reset` işaretçi siler ve depolanmış bir işaretçiyle ayarlar **nullptr**.

```cpp
void reset(pointer ptr = pointer());
void reset(nullptr_t ptr);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ptr*|Kaynağın sahipliğini almak için bir işaretçi.|

### <a name="remarks"></a>Açıklamalar

Kullanım `reset` saklı değiştirmek için [işaretçi](#pointer) tarafından sahip olunan `unique_ptr` için *ptr* ve özgün depolanan işaretçide silin. Varsa `unique_ptr` boş değildi `reset` Silici işlevi tarafından döndürülen çağıran [get_deleter](#get_deleter) özgün depolanan işaretçinin.

Çünkü `reset` önce yeni bir işaretçi depolar *ptr*ve ardından özgün depolanmış işaretçiyi siler mümkündür `reset` hemen silinecek *ptr* orijinal ile aynı olduğunda depolanmış bir işaretçiyle.

## <a name="swap"></a>  unique_ptr::Swap

Birbiriyle değiştirir, ikisi arasında işaretçileri `unique_ptr` nesneleri.

```cpp
void swap(unique_ptr& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
A `unique_ptr` işaretçileri takas etmek için kullanılır.

### <a name="remarks"></a>Açıklamalar

Üye işlevi değiştirir `stored_ptr` ile `right.stored_ptr` ve `stored_deleter` ile `right.stored_deleter`.

## <a name="unique_ptr"></a>  unique_ptr::unique_ptr

İçin yedi Oluşturucu vardır `unique_ptr`.

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
|*ptr*|Kaynağına atanan bir işaretçi bir `unique_ptr.`|
|*_Deleter*|A `deleter` atanacak bir `unique_ptr`.|
|*sağ*|Bir `rvalue reference` için bir `unique_ptr` içinden `unique_ptr` alanları yeni oluşturulmuş atanan taşıma `unique_ptr`.|

### <a name="remarks"></a>Açıklamalar

İlk iki Oluşturucu hiçbir kaynak yöneten bir nesne oluşturur. Üçüncü Oluşturucu depoları *ptr* içinde `stored_ptr`. Dördüncü Oluşturucu depoları *ptr* içinde `stored_ptr` ve `deleter` içinde `stored_deleter`.

Beşinci Oluşturucu depoları *ptr* içinde `stored_ptr` ve taşır `deleter` içine `stored_deleter`. Altıncı ve yedinci oluşturucular deponun `right.release()` içinde `stored_ptr` ve taşır `right.get_deleter()` içine `stored_deleter`.

## <a name="dtorunique_ptr"></a>  unique_ptr ~ unique_ptr

Yok Edicisi `unique_ptr`, yok eder bir `unique_ptr` nesne.

```cpp
~unique_ptr();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çağrıları `get_deleter()(stored_ptr)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<bellek >](../standard-library/memory.md)<br/>
