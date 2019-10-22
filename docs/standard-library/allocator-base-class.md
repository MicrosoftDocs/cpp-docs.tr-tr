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
ms.openlocfilehash: cbc1a9eb9432a454ca5dc04205b9d0c7b631a430
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72690098"
---
# <a name="allocator_base-class"></a>allocator_base Sınıfı

Bir eşitleme filtresinden Kullanıcı tanımlı bir ayırıcı oluşturmak için gereken temel sınıfı ve ortak işlevleri tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type, class Sync>
class allocator_base
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Türüyle*|Ayırıcı tarafından ayrılan öğelerin türü.|
|*Eşitleme*|Ayırıcı için [Sync_none Class](../standard-library/sync-none-class.md), [sync_per_container Class](../standard-library/sync-per-container-class.md), [sync_per_thread Class](../standard-library/sync-per-thread-class.md)veya [sync_shared sınıfı](../standard-library/sync-shared-class.md)olan eşitleme ilkesi.|

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[allocator_base](#allocator_base)|@No__t_0 türünde bir nesne oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[const_pointer](#const_pointer)|Ayırıcı tarafından yönetilen nesne türüne sabit bir işaretçi sağlayan bir tür.|
|[const_reference](#const_reference)|Ayırıcı tarafından yönetilen nesne türüne sabit bir başvuru sağlayan bir tür.|
|[difference_type](#difference_type)|Ayırıcı tarafından yönetilen nesne türüne yönelik işaretçilerin değerleri arasındaki farkı temsil eden, işaretli bir tamsayı türü.|
|[çağrısı](#pointer)|Ayırıcı tarafından yönetilen nesne türüne işaretçi sağlayan bir tür.|
|[başvurunun](#reference)|Ayırıcı tarafından yönetilen nesne türüne başvuru sağlayan bir tür.|
|[size_type](#size_type)|@No__t_0 türünde bir nesnenin ayırabilecek herhangi bir dizinin uzunluğunu temsil eden işaretsiz bir tamsayı türü.|
|[value_type](#value_type)|Ayırıcı tarafından yönetilen bir tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[_Charayırma](#charalloc)|**Char**türünde bir dizi için depolamayı ayırır.|
|[_Chardeayırma](#chardealloc)|**Char**türünde öğeleri içeren dizi için depolamayı boşaltır.|
|[adrestir](#address)|Değeri belirtilen bir nesnenin adresini bulur.|
|[allocate](#allocate)|En az bazı sayıda öğe depolamak için yeterince büyük bir bellek bloğu ayırır.|
|[oluşturma](#construct)|Belirtilen bir değer ile başlatılan belirli bir adreste belirli bir nesne türü oluşturur.|
|[kaldırmak](#deallocate)|Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.|
|[kaldırılır](#destroy)|Nesnenin depolandığı belleği ayırmayı kaldırmadan bir nesne yıkıcısı çağırır.|
|[max_size](#max_size)|Boş bellek kullanılmadan önce sınıf ayırıcı nesnesi tarafından *ayrılabilecek tür türünde* öğelerin sayısını döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<allocators >

**Ad alanı:** stdext

## <a name="charalloc"></a>allocator_base:: _Charayırma

**Char**türünde bir dizi için depolamayı ayırır.

```cpp
char *_Charalloc(size_type count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*biriktirme*|Ayrılacak dizideki öğelerin sayısı.|

### <a name="return-value"></a>Dönüş Değeri

Ayrılan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, yeniden bağlama Derlenemeyen bir derleyici ile derlendikleri zaman kapsayıcı tarafından kullanılır. Eşitleme filtresinin `allocate` işlevine yapılan çağrının sonucunu döndürerek Kullanıcı tanımlı ayırıcı için `_Charalloc` uygular.

## <a name="chardealloc"></a>allocator_base:: _Chardeayırma

**Char**türünde öğeleri içeren dizi için depolamayı boşaltır.

```cpp
void _Chardealloc(void* ptr, size_type count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ptr*|Depolamadan serbest bırakmak için ilk nesneye yönelik bir işaretçi.|
|*biriktirme*|Depolamadan serbest bırakmak için nesne sayısı.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, yeniden bağlama Derlenemeyen bir derleyici ile derlendikleri zaman kapsayıcı tarafından kullanılır. Eşitleme filtresinin `deallocate` işlevini çağırarak Kullanıcı tanımlı ayırıcı için `_Chardealloc` uygular. İşaretçi PTR, aynı boyut ve türden bir dizi nesnesi ayırarak, `*this` eşit ile karşılaştıran bir ayırıcı nesnesi için `_Charalloc` çağrısıyla önceden Döndürülmüş olmalıdır. `_Chardealloc` hiçbir şekilde özel durum oluşturmaz.

## <a name="address"></a>allocator_base:: Address

Değeri belirtilen bir nesnenin adresini bulur.

```cpp
pointer address(reference val);

const_pointer address(const_reference val);
```

### <a name="parameters"></a>Parametreler

*val* \
Adresi aranmakta olan nesnenin const veya nonconst değeri.

### <a name="return-value"></a>Dönüş Değeri

, Sırasıyla const veya nonconst değeri bulunan nesnenin const veya nonconst bir işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, `&val` döndürerek Kullanıcı tanımlı ayırıcı için uygulanır.

## <a name="allocate"></a>allocator_base:: allocate

En az bazı sayıda öğe depolamak için yeterince büyük bir bellek bloğu ayırır.

```cpp
template <class Other>
pointer allocate(size_type _Nx, const Other* _Hint = 0);

pointer allocate(size_type _Nx);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Nx*|Ayrılacak dizideki öğelerin sayısı.|
|*_Ipucu*|Bu parametre yoksayıldı.|

### <a name="return-value"></a>Dönüş Değeri

Ayrılan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, Kullanıcı tanımlı ayırıcı için, `_Nx == 1` `*` tür türü `allocate` işlevine yapılan çağrının sonucunu döndürerek Kullanıcı tanımlı ayırıcı için bellek ayırmayı uygular, aksi takdirde, `operator new(_Nx * sizeof(Type))` cast tür türü `*`.

## <a name="allocator_base"></a>allocator_base::allocator_base

@No__t_0 türünde bir nesne oluşturur.

```cpp
allocator_base();

template <class Other>
allocator_base(const allocator_base<Other, Sync>& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Right*|Kopyalanacak ayırıcı nesne.|

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu bir [allocator_base](../standard-library/allocator-base-class.md) örneği oluşturur. İkinci Oluşturucu, `allocator_base<Type, Sync>(allocator_base<Other, Sync>(a)) == a` `a` `allocator_base<Type, _Sync>` örneği için `allocator_base` bir örnek oluşturur.

## <a name="const_pointer"></a>allocator_base::const_pointer

Ayırıcı tarafından yönetilen nesne türüne sabit bir işaretçi sağlayan bir tür.

```cpp
typedef const Type *const_pointer;
```

## <a name="const_reference"></a>allocator_base::const_reference

Ayırıcı tarafından yönetilen nesne türüne sabit bir başvuru sağlayan bir tür.

```cpp
typedef const Type& const_reference;
```

## <a name="construct"></a>allocator_base:: yapısı

Belirtilen bir değer ile başlatılan belirli bir adreste belirli bir nesne türü oluşturur.

```cpp
void construct(pointer ptr, const Type& val);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ptr*|Nesnenin oluşturulması gereken konuma yönelik bir işaretçi.|
|*Acil*|Oluşturulan nesnenin başlatılacağı değer.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, `new((void*)ptr Type(val)` çağırarak Kullanıcı tanımlı ayırıcı için uygulanır.

## <a name="deallocate"></a>allocator_base::d eallocate

Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.

```cpp
void deallocate(pointer ptr, size_type _Nx);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ptr*|Depolamadan serbest bırakmak için ilk nesneye yönelik bir işaretçi.|
|*_Nx*|Depolamadan serbest bırakmak için nesne sayısı.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, `_Nx == 1` `Sync` eşitleme filtresine `deallocate(ptr)` çağırarak Kullanıcı tanımlı ayırıcı için uygulanır, aksi takdirde `operator delete(_Nx * ptr)` çağırır.

## <a name="destroy"></a>allocator_base::d estroy

Nesnenin depolandığı belleği ayırmayı kaldırmadan bir nesne yıkıcısı çağırır.

```cpp
void destroy(pointer ptr);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ptr*|Yok edilecek nesnenin adresini atayarak bir işaretçi.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, `ptr->~Type()` çağırarak Kullanıcı tanımlı ayırıcı için uygulanır.

## <a name="difference_type"></a>allocator_base::d ifference_type

Ayırıcı tarafından yönetilen nesne türüne yönelik işaretçilerin değerleri arasındaki farkı temsil eden, işaretli bir tamsayı türü.

```cpp
typedef std::ptrdiff_t difference_type;
```

## <a name="max_size"></a>allocator_base::max_size

Boş bellek kullanılmadan önce sınıf ayırıcı nesnesi tarafından ayrılabilecek `Type` türündeki öğe sayısını döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılabilen öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, `0 < (size_t)-1 / sizeof(Type)`, aksi takdirde `1` `(size_t)-1 / sizeof(Type)` döndürerek Kullanıcı tanımlı ayırıcı için uygulanır.

## <a name="pointer"></a>allocator_base::p oınter

Ayırıcı tarafından yönetilen nesne türüne işaretçi sağlayan bir tür.

```cpp
typedef Type *pointer;
```

## <a name="reference"></a>allocator_base:: Reference

Ayırıcı tarafından yönetilen nesne türüne başvuru sağlayan bir tür.

```cpp
typedef Type& reference;
```

## <a name="size_type"></a>allocator_base::size_type

@No__t_0 türünde bir nesnenin ayırabilecek herhangi bir dizinin uzunluğunu temsil eden işaretsiz bir tamsayı türü.

```cpp
typedef std::size_t size_type;
```

## <a name="value_type"></a>allocator_base::value_type

Ayırıcı tarafından yönetilen bir tür.

```cpp
typedef Type value_type;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators >](../standard-library/allocators-header.md)
