---
title: allocator_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_base
- allocators/stdext::allocators::allocator_base
- allocators/stdext::allocator_base::const_pointer
- allocators/stdext::allocator_base::const_reference
- allocators/stdext::allocator_base::difference_type
- allocators/stdext::allocator_base::pointer
- allocators/stdext::allocator_base::reference
- allocators/stdext::allocator_base::size_type
- allocators/stdext::allocator_base::value_type
- allocators/stdext::allocator_base::_Charalloc
- allocators/stdext::allocator_base::_Chardealloc
- allocators/stdext::allocator_base::address
- allocators/stdext::allocator_base::allocate
- allocators/stdext::allocator_base::construct
- allocators/stdext::allocator_base::deallocate
- allocators/stdext::allocator_base::destroy
- allocators/stdext::allocator_base::max_size
helpviewer_keywords:
- stdext::allocator_base [C++]
- stdext::allocators [C++], allocator_base
- stdext::allocator_base [C++], const_pointer
- stdext::allocator_base [C++], const_reference
- stdext::allocator_base [C++], difference_type
- stdext::allocator_base [C++], pointer
- stdext::allocator_base [C++], reference
- stdext::allocator_base [C++], size_type
- stdext::allocator_base [C++], value_type
- stdext::allocator_base [C++], _Charalloc
- stdext::allocator_base [C++], _Chardealloc
- stdext::allocator_base [C++], address
- stdext::allocator_base [C++], allocate
- stdext::allocator_base [C++], construct
- stdext::allocator_base [C++], deallocate
- stdext::allocator_base [C++], destroy
- stdext::allocator_base [C++], max_size
ms.assetid: f920b45f-2a88-4bb0-8ead-b6126b426ed4
ms.openlocfilehash: f93c8ff53452fc98415e194966960254e7b44143
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364992"
---
# <a name="allocator_base-class"></a>allocator_base Sınıfı

Eşitleme filtresinden kullanıcı tanımlı bir ayırıcı oluşturmak için gereken taban sınıf ve ortak işlevleri tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type, class Sync>
class allocator_base
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Tür*|Ayırıcı tarafından ayrılan öğelerin türü.|
|*Eşitle*|[Sınıf,](../standard-library/sync-none-class.md) [sync_per_container Sınıfı](../standard-library/sync-per-container-class.md), [sync_per_thread Sınıfı](../standard-library/sync-per-thread-class.md)veya sync_shared [Sınıfı](../standard-library/sync-shared-class.md)sync_none olan ayırıcı için eşitleme ilkesi.|

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[allocator_base](#allocator_base)|Türünde `allocator_base`bir nesne oluşturuyor.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Const_pointer](#const_pointer)|Ayırıcı tarafından yönetilen nesne türüne sabit bir işaretçi sağlayan bir tür.|
|[const_reference](#const_reference)|Ayırıcı tarafından yönetilen nesne türüne sabit bir başvuru sağlayan bir tür.|
|[difference_type](#difference_type)|Ayırıcı tarafından yönetilen nesne türüne işaretçilerin değerleri arasındaki farkı temsil eden imzalı bir integral türü.|
|[pointer](#pointer)|Ayırıcı tarafından yönetilen nesne türüne işaretçi sağlayan bir tür.|
|[Başvuru](#reference)|Ayırıcı tarafından yönetilen nesne türüne başvuru sağlayan bir tür.|
|[size_type](#size_type)|Bir tür `allocator_base` nesnenin ayırabileceği herhangi bir dizinin uzunluğunu temsil eden imzalanmamış bir integral türü.|
|[value_type](#value_type)|Ayırıcı tarafından yönetilen bir tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[_Charalloc](#charalloc)|Bir dizi **tür char**için depolama ayırır.|
|[_Chardealloc](#chardealloc)|Tür **char**öğeleriiçeren dizi için depolama boşaltıyor.|
|[Adres](#address)|Değeri belirtilen bir nesnenin adresini bulur.|
|[allocate](#allocate)|En az bazı belirli sayıda öğeyi depolayacak kadar büyük bir bellek bloğu ayırır.|
|[Oluşturmak](#construct)|Belirli bir değerle başharfe bürünen belirli bir adreste belirli bir nesne türü oluşturuyor.|
|[Ayırması](#deallocate)|Belirli bir konumdan başlayarak belirli sayıda nesneyi depolamadan serbest sağlar.|
|[destroy](#destroy)|Nesnenin depolandığı belleği ayırmadan nesneleri yıkıcı çağırır.|
|[max_size](#max_size)|Serbest bellek kullanılmadan önce sınıf ayırıcıbir nesne tarafından ayrılabilecek *tür türü* öğelerinin sayısını döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<tahsisörler>

**Ad alanı:** stdext

## <a name="allocator_base_charalloc"></a><a name="charalloc"></a>allocator_base:_Charalloc

Bir dizi **tür char**için depolama ayırır.

```cpp
char *_Charalloc(size_type count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sayısı*|Dizideki ayrılacak öğe sayısı.|

### <a name="return-value"></a>Dönüş Değeri

Ayrılan nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, rebind derleyemeyen bir derleyici ile derlendiğinde kapsayıcılar tarafından kullanılır. Eşitleme `_Charalloc` filtresinin `allocate` işlevine bir çağrının sonucunu döndürerek kullanıcı tanımlı ayırıcı için uygular.

## <a name="allocator_base_chardealloc"></a><a name="chardealloc"></a>allocator_base::_Chardealloc

Tür **char**öğeleriiçeren dizi için depolama boşaltıyor.

```cpp
void _Chardealloc(void* ptr, size_type count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Ptr*|Depolamadan ayrılacak ilk nesneye işaretçi.|
|*Sayısı*|Depolamadan ayrılacak nesne sayısı.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, rebind derleyemeyen bir derleyici ile derlendiğinde kapsayıcılar tarafından kullanılır. Senkronizasyon `_Chardealloc` filtresinin `deallocate` işlevini çağırarak kullanıcı tanımlı ayırıcı için uygular. İşaretçi ptr daha önce aynı boyut `_Charalloc` ve türde bir dizi `*this`nesnesi ayıran eşit karşılaştırır bir ayırıcı nesne için bir çağrı tarafından döndürülmüş olması gerekir. `_Chardealloc`asla bir istisna atmaz.

## <a name="allocator_baseaddress"></a><a name="address"></a>allocator_base::adres

Değeri belirtilen bir nesnenin adresini bulur.

```cpp
pointer address(reference val);

const_pointer address(const_reference val);
```

### <a name="parameters"></a>Parametreler

*Val*\
Adresi aranmakta olan nesnenin const veya nonconst değeri.

### <a name="return-value"></a>Dönüş Değeri

Bulunan nesneye const veya nonconst işaretçisi, sırasıyla, const veya nonconst değeri.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, kullanıcı tarafından tanımlanan ayırıcı `&val`için döndürülerek uygulanır.

## <a name="allocator_baseallocate"></a><a name="allocate"></a>allocator_base::allocate

En az bazı belirli sayıda öğeyi depolayacak kadar büyük bir bellek bloğu ayırır.

```cpp
template <class Other>
pointer allocate(size_type _Nx, const Other* _Hint = 0);

pointer allocate(size_type _Nx);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Dizideki ayrılacak öğe sayısı.|
|*_Hint*|Bu parametre yoksayıldı.|

### <a name="return-value"></a>Dönüş Değeri

Ayrılan nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlev, kullanıcı tanımlı ayırıcı için bellek ayırma yı uygular, `allocate` eğer `*` `_Nx == 1`türünde eşitleme filtresi işlevine bir çağrının sonucunu döndürerek , `*`aksi takdirde türüne `operator new(_Nx * sizeof(Type))` döküm için bir çağrının sonucunu döndürerek .

## <a name="allocator_baseallocator_base"></a><a name="allocator_base"></a>allocator_base::allocator_base

Türünde `allocator_base`bir nesne oluşturuyor.

```cpp
allocator_base();

template <class Other>
allocator_base(const allocator_base<Other, Sync>& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Doğru*|Kopyalanacak ayırıcı nesne.|

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu [allocator_base](../standard-library/allocator-base-class.md) bir örnek oluşturuyor. İkinci oluşturucu, herhangi `allocator_base` `allocator_base<Type, _Sync>` bir örnek `a`için `allocator_base<Type, Sync>(allocator_base<Other, Sync>(a)) == a`, .

## <a name="allocator_baseconst_pointer"></a><a name="const_pointer"></a>allocator_base:const_pointer

Ayırıcı tarafından yönetilen nesne türüne sabit bir işaretçi sağlayan bir tür.

```cpp
typedef const Type *const_pointer;
```

## <a name="allocator_baseconst_reference"></a><a name="const_reference"></a>allocator_base:const_reference

Ayırıcı tarafından yönetilen nesne türüne sabit bir başvuru sağlayan bir tür.

```cpp
typedef const Type& const_reference;
```

## <a name="allocator_baseconstruct"></a><a name="construct"></a>allocator_base::yapı

Belirli bir değerle başharfe bürünen belirli bir adreste belirli bir nesne türü oluşturuyor.

```cpp
void construct(pointer ptr, const Type& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Ptr*|Nesnenin oluşturulacağı konuma işaretçi.|
|*Val*|Oluşturulmakta olan nesnenin değeri başharfe atılmalıdır.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, kullanıcı tanımlı ayırıcı `new((void*)ptr Type(val)`için .

## <a name="allocator_basedeallocate"></a><a name="deallocate"></a>allocator_base::d

Belirli bir konumdan başlayarak belirli sayıda nesneyi depolamadan serbest sağlar.

```cpp
void deallocate(pointer ptr, size_type _Nx);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Ptr*|Depolamadan ayrılacak ilk nesneye işaretçi.|
|*_Nx*|Depolamadan ayrılacak nesne sayısı.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, kullanıcı tanımlı ayırıcı `deallocate(ptr)` için senkronizasyon `Sync` filtresini `_Nx == 1`çağırarak `operator delete(_Nx * ptr)`uygulanır, aksi takdirde .

## <a name="allocator_basedestroy"></a><a name="destroy"></a>allocator_base::destroy

Nesnenin depolandığı belleği ayırmadan nesneleri yıkıcı çağırır.

```cpp
void destroy(pointer ptr);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Ptr*|Yok edilecek nesnenin adresini atanan bir işaretçi.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlev, kullanıcı tanımlı ayırıcı `ptr->~Type()`için .

## <a name="allocator_basedifference_type"></a><a name="difference_type"></a>allocator_base::difference_type

Ayırıcı tarafından yönetilen nesne türüne işaretçilerin değerleri arasındaki farkı temsil eden imzalı bir integral türü.

```cpp
typedef std::ptrdiff_t difference_type;
```

## <a name="allocator_basemax_size"></a><a name="max_size"></a>allocator_base:max_size

Boş bellek kullanılmadan `Type` önce sınıf ayırıcıbir nesne tarafından ayrılabilecek tür öğelerinin sayısını verir.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılabilecek öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev kullanıcı tanımlı ayırıcı için `(size_t)-1 / sizeof(Type)` döndürülerek `1`uygulanır, aksi takdirde `0 < (size_t)-1 / sizeof(Type)`.

## <a name="allocator_basepointer"></a><a name="pointer"></a>allocator_base::pointer

Ayırıcı tarafından yönetilen nesne türüne işaretçi sağlayan bir tür.

```cpp
typedef Type *pointer;
```

## <a name="allocator_basereference"></a><a name="reference"></a>allocator_base::referans

Ayırıcı tarafından yönetilen nesne türüne başvuru sağlayan bir tür.

```cpp
typedef Type& reference;
```

## <a name="allocator_basesize_type"></a><a name="size_type"></a>allocator_base::size_type

Bir tür `allocator_base` nesnenin ayırabileceği herhangi bir dizinin uzunluğunu temsil eden imzalanmamış bir integral türü.

```cpp
typedef std::size_t size_type;
```

## <a name="allocator_basevalue_type"></a><a name="value_type"></a>allocator_base::value_type

Ayırıcı tarafından yönetilen bir tür.

```cpp
typedef Type value_type;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<tahsisat>](../standard-library/allocators-header.md)
