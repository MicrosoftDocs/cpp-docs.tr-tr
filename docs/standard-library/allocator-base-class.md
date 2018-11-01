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
ms.openlocfilehash: 59d5834b941791a659815ff0a03f1c68c8ce68bd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591652"
---
# <a name="allocatorbase-class"></a>allocator_base Sınıfı

Eşitleme filtresi kullanıcı tarafından tanımlanan bir ayırıcı oluşturmak için gereken genel işlevler ve temel sınıf tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type, class Sync>
class allocator_base
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Türü*|Ayırıcı tarafından ayrılan öğelerin türü.|
|*Eşitleme*|Eşitleme ilkesi olan ayırıcı için [sync_none sınıfı](../standard-library/sync-none-class.md), [sync_per_kapsayıcı sınıfı](../standard-library/sync-per-container-class.md), [sync_per_thread sınıfı](../standard-library/sync-per-thread-class.md), veya [sync_shared Sınıf](../standard-library/sync-shared-class.md).|

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[allocator_base](#allocator_base)|Türünde bir nesne oluşturur `allocator_base`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[const_pointer](#const_pointer)|Ayırıcı tarafından yönetilen nesne türü için sabit bir işaretçi sağlayan bir tür.|
|[const_reference](#const_reference)|Ayırıcı tarafından yönetilen nesne türü için sabit bir başvuru sağlayan bir tür.|
|[difference_type](#difference_type)|İşaretçiler ayırıcısı tarafından yönetilen nesne türü için değer arasındaki farkı temsil edebilen imzalı bir tamsayı türü.|
|[İşaretçi](#pointer)|Ayırıcı tarafından yönetilen nesne türü için bir işaretçi sağlayan bir tür.|
|[Başvuru](#reference)|Ayırıcı tarafından yönetilen nesne türü bir başvuru sağlayan bir tür.|
|[size_type](#size_type)|Herhangi bir uzunluğunu temsil edebilen bir işaretsiz tamsayı türü dizisi şablon sınıfın bir nesnesi `allocator_base` ayırabilirsiniz.|
|[value_type](#value_type)|Ayırıcı tarafından yönetilen bir tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[_Charalloc](#charalloc)|Depolama türü için bir dizi ayırır **char**.|
|[_Chardealloc](#chardealloc)|Depolama türü öğeler içeren bir dizi için boşaltır **char**.|
|[Adresi](#address)|Değeri belirtilen bir nesnenin adresini bulur.|
|[allocate](#allocate)|En azından bazı belirtilen sayıda öğeyi depolamak için büyük bir bellek bloğu ayırır.|
|[Yapısı](#construct)|Belirli türde bir nesne belirli bir değerle başlatılır, belirtilen bir adresteki oluşturur.|
|[Serbest Bırak](#deallocate)|Belirtilen konumda depolama başından nesneleri belirtilen sayıda serbest bırakır.|
|[yok](#destroy)|Bir nesne yok Edicisi belleğini olmadan nesne saklandığı çağırır.|
|[max_size](#max_size)|Tür öğelerin sayısını döndürür *türü* , ayrılan bir nesnenin sınıf ayırıcısı tarafından boş bellek kullanılmadan önce.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ayırıcılar >

**Namespace:** stdext

## <a name="charalloc"></a>  allocator_base::_Charalloc

Depolama türü için bir dizi ayırır **char**.

```cpp
char *_Charalloc(size_type count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sayısı*|Ayrılacak dizideki öğelerin sayısı.|

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış bir nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini yeniden bağlamasını derlenemez bir derleyici ile derlendiğinde kapsayıcıları tarafından kullanılır. Bunu uygulayan `_Charalloc` için bir çağrı sonucunu döndürerek kullanıcı tanımlı ayırıcı `allocate` eşitleme filtre işlevi.

## <a name="chardealloc"></a>  allocator_base::_Chardealloc

Depolama türü öğeler içeren bir dizi için boşaltır **char**.

```cpp
void _Chardealloc(void* ptr, size_type count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ptr*|Depolama alanından serbest bırakılması ilk nesneye bir işaretçi.|
|*Sayısı*|Depolama alanından serbest bırakılması nesne sayısı.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini yeniden bağlamasını derlenemez bir derleyici ile derlendiğinde kapsayıcıları tarafından kullanılır. Bunu uygulayan `_Chardealloc` çağırarak kullanıcı tanımlı ayırıcı için `deallocate` eşitleme filtre işlevi. İşaretçi ptr önceki bir çağrı tarafından iade edilmiş gerekir `_Charalloc` eşit karşılaştıran bir ayırıcı nesnesinin `*this`, aynı büyüklük ve türdeki bir dizi nesne ayırma. `_Chardealloc` hiçbir zaman bir özel durum oluşturur.

## <a name="address"></a>  allocator_base::Address

Değeri belirtilen bir nesnenin adresini bulur.

```cpp
pointer address(reference val);

const_pointer address(const_reference val);
```

### <a name="parameters"></a>Parametreler

*VAL*<br/>
Const veya nonconst değeri nesnenin adresini aranır.

### <a name="return-value"></a>Dönüş Değeri

Const veya nonconst nesneye işaretçi, sırasıyla, const veya nonconst değeri bulundu.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi için kullanıcı tanımlı ayırıcı döndürerek uygulanan `&val`.

## <a name="allocate"></a>  allocator_base::allocate

En azından bazı belirtilen sayıda öğeyi depolamak için büyük bir bellek bloğu ayırır.

```cpp
template <class Other>
pointer allocate(size_type _Nx, const Other* _Hint = 0);

pointer allocate(size_type _Nx);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Ayrılacak dizideki öğelerin sayısı.|
|*_Hint*|Bu parametre yoksayıldı.|

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış bir nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi bir çağrı sonucunu döndürerek kullanıcı tanımlı ayırıcı için bellek ayırmayı uygulayan `allocate` eşitleme filtre türü, işlev `*` varsa `_Nx == 1`, aksi takdirde sonucu döndürerek bir çağrısı `operator new(_Nx * sizeof(Type))` atama türünü `*`.

## <a name="allocator_base"></a>  allocator_base::allocator_base

Türünde bir nesne oluşturur `allocator_base`.

```cpp
allocator_base();

template <class Other>
allocator_base(const allocator_base<Other, Sync>& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*sağ*|Kopyalanacak ayırıcı nesne.|

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu yapıları bir [allocator_base](../standard-library/allocator-base-class.md) örneği. İkinci oluşturucu yapıları bir `allocator_base` gibi örnek, tüm `allocator_base<Type, _Sync>` örneği `a`, `allocator_base<Type, Sync>(allocator_base<Other, Sync>(a)) == a`.

## <a name="const_pointer"></a>  allocator_base::const_pointer

Ayırıcı tarafından yönetilen nesne türü için sabit bir işaretçi sağlayan bir tür.

```cpp
typedef const Type *const_pointer;
```

## <a name="const_reference"></a>  allocator_base::const_reference

Ayırıcı tarafından yönetilen nesne türü için sabit bir başvuru sağlayan bir tür.

```cpp
typedef const Type& const_reference;
```

## <a name="construct"></a>  allocator_base::Construct

Belirli türde bir nesne belirli bir değerle başlatılır, belirtilen bir adresteki oluşturur.

```cpp
void construct(pointer ptr, const Type& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ptr*|Nesnenin oluşturulması olduğu yere bir işaretçi.|
|*VAL*|Yapılandırılan nesnesinin başlatılacak olduğu değeri.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini çağırarak için kullanıcı tanımlı ayırıcı uygulanan `new((void*)ptr Type(val)`.

## <a name="deallocate"></a>  allocator_base::deallocate

Belirtilen konumda depolama başından nesneleri belirtilen sayıda serbest bırakır.

```cpp
void deallocate(pointer ptr, size_type _Nx);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ptr*|Depolama alanından serbest bırakılması ilk nesneye bir işaretçi.|
|*_Nx*|Depolama alanından serbest bırakılması nesne sayısı.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini çağırarak için kullanıcı tanımlı ayırıcı uygulanan `deallocate(ptr)` eşitleme filtresini `Sync` varsa `_Nx == 1`, aksi takdirde çağırarak `operator delete(_Nx * ptr)`.

## <a name="destroy"></a>  allocator_base::Destroy

Bir nesne yok Edicisi belleğini olmadan nesne saklandığı çağırır.

```cpp
void destroy(pointer ptr);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ptr*|Yok edilecek nesnenin adresini gösteren bir işaretçi.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini çağırarak için kullanıcı tanımlı ayırıcı uygulanan `ptr->~Type()`.

## <a name="difference_type"></a>  allocator_base::difference_type

İşaretçiler ayırıcısı tarafından yönetilen nesne türü için değer arasındaki farkı temsil edebilen imzalı bir tamsayı türü.

```cpp
typedef std::ptrdiff_t difference_type;
```

## <a name="max_size"></a>  allocator_base::max_size

Tür öğelerin sayısını döndürür `Type` , ayrılan bir nesnenin sınıf ayırıcısı tarafından boş bellek kullanılmadan önce.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılamadı öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi için kullanıcı tanımlı ayırıcı döndürerek uygulanan `(size_t)-1 / sizeof(Type)` varsa `0 < (size_t)-1 / sizeof(Type)`, aksi takdirde `1`.

## <a name="pointer"></a>  allocator_base::pointer

Ayırıcı tarafından yönetilen nesne türü için bir işaretçi sağlayan bir tür.

```cpp
typedef Type *pointer;
```

## <a name="reference"></a>  allocator_base::Reference

Ayırıcı tarafından yönetilen nesne türü bir başvuru sağlayan bir tür.

```cpp
typedef Type& reference;
```

## <a name="size_type"></a>  allocator_base::size_type

Herhangi bir uzunluğunu temsil edebilen bir işaretsiz tamsayı türü dizisi şablon sınıfın bir nesnesi `allocator_base` ayırabilirsiniz.

```cpp
typedef std::size_t size_type;
```

## <a name="value_type"></a>  allocator_base::value_type

Ayırıcı tarafından yönetilen bir tür.

```cpp
typedef Type value_type;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<Ayırıcılar >](../standard-library/allocators-header.md)<br/>
