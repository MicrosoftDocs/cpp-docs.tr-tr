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
ms.openlocfilehash: b55a7ec92787cb6b3103bf71b65d137d24ffff04
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617582"
---
# <a name="allocator_base-class"></a>allocator_base Sınıfı

Bir eşitleme filtresinden Kullanıcı tanımlı bir ayırıcı oluşturmak için gereken temel sınıfı ve ortak işlevleri tanımlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class Type, class Sync>
class allocator_base
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Tür*|Ayırıcı tarafından ayrılan öğelerin türü.|
|*Eşitle*|Ayırıcı için [Sync_none Class](sync-none-class.md), [Sync_per_container Class](sync-per-container-class.md) [sync_per_thread Class](sync-per-thread-class.md)veya [sync_shared sınıfı](sync-shared-class.md)olan eşitleme ilkesi.|

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[allocator_base](#allocator_base)|Türünde bir nesne oluşturur `allocator_base` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[const_pointer](#const_pointer)|Ayırıcı tarafından yönetilen nesne türüne sabit bir işaretçi sağlayan bir tür.|
|[const_reference](#const_reference)|Ayırıcı tarafından yönetilen nesne türüne sabit bir başvuru sağlayan bir tür.|
|[difference_type](#difference_type)|Ayırıcı tarafından yönetilen nesne türüne yönelik işaretçilerin değerleri arasındaki farkı temsil eden, işaretli bir tamsayı türü.|
|[pointer](#pointer)|Ayırıcı tarafından yönetilen nesne türüne işaretçi sağlayan bir tür.|
|[başvurunun](#reference)|Ayırıcı tarafından yönetilen nesne türüne başvuru sağlayan bir tür.|
|[size_type](#size_type)|Türünde bir nesnenin ayırabilecek herhangi bir dizinin uzunluğunu temsil eden işaretsiz bir tamsayı türü `allocator_base` .|
|[value_type](#value_type)|Ayırıcı tarafından yönetilen bir tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[_Charalloc](#charalloc)|**Char**türünde bir dizi için depolamayı ayırır.|
|[_Chardealloc](#chardealloc)|**Char**türünde öğeleri içeren dizi için depolamayı boşaltır.|
|[adrestir](#address)|Değeri belirtilen bir nesnenin adresini bulur.|
|[allocate](#allocate)|En az bazı sayıda öğe depolamak için yeterince büyük bir bellek bloğu ayırır.|
|[oluşturma](#construct)|Belirtilen bir değer ile başlatılan belirli bir adreste belirli bir nesne türü oluşturur.|
|[kaldırmak](#deallocate)|Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.|
|[kaldırılır](#destroy)|Nesnenin depolandığı belleği ayırmayı kaldırmadan bir nesne yıkıcısı çağırır.|
|[max_size](#max_size)|Boş bellek kullanılmadan önce sınıf ayırıcı nesnesi tarafından *ayrılabilecek tür türünde* öğelerin sayısını döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<allocators>

**Ad alanı:** stdext

## <a name="allocator_base_charalloc"></a><a name="charalloc"></a>allocator_base:: _Charalloc

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

Bu üye işlevi, yeniden bağlama Derlenemeyen bir derleyici ile derlendikleri zaman kapsayıcı tarafından kullanılır. `_Charalloc`Eşitleme filtresinin işlevine yapılan çağrının sonucunu döndürerek Kullanıcı tanımlı ayırıcıyı uygular `allocate` .

## <a name="allocator_base_chardealloc"></a><a name="chardealloc"></a>allocator_base:: _Chardealloc

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

Bu üye işlevi, yeniden bağlama Derlenemeyen bir derleyici ile derlendikleri zaman kapsayıcı tarafından kullanılır. `_Chardealloc`Eşitleme filtresinin işlevini çağırarak Kullanıcı tanımlı ayırıcıyı uygular `deallocate` . İşaretçi PTR, `_Charalloc` `*this` aynı boyut ve türden bir dizi nesnesi ayırarak, buna eşit olarak karşılaştırdığı bir ayırıcı nesnesi için çağrısı tarafından daha önce döndürülmüş olmalıdır. `_Chardealloc`hiçbir koşulda özel durum oluşturmaz.

## <a name="allocator_baseaddress"></a><a name="address"></a>allocator_base:: adres

Değeri belirtilen bir nesnenin adresini bulur.

```cpp
pointer address(reference val);

const_pointer address(const_reference val);
```

### <a name="parameters"></a>Parametreler

*Acil*\
Adresi aranmakta olan nesnenin const veya nonconst değeri.

### <a name="return-value"></a>Dönüş Değeri

, Sırasıyla const veya nonconst değeri bulunan nesnenin const veya nonconst bir işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, dönerek Kullanıcı tanımlı ayırıcı için uygulanır `&val` .

## <a name="allocator_baseallocate"></a><a name="allocate"></a>allocator_base:: ayır

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
|*_Hint*|Bu parametre yoksayıldı.|

### <a name="return-value"></a>Dönüş Değeri

Ayrılan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `allocate` `*` `_Nx == 1` , aksi takdirde tür türüne dönüştürme çağrısının sonucunu döndürerek Kullanıcı `operator new(_Nx * sizeof(Type))` tanımlı ayırıcı için bir çağrının sonucunu döndürerek Kullanıcı tanımlı ayırıcı için bellek ayırmayı uygular `*` .

## <a name="allocator_baseallocator_base"></a><a name="allocator_base"></a>allocator_base:: allocator_base

Türünde bir nesne oluşturur `allocator_base` .

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

İlk Oluşturucu bir [allocator_base](allocator-base-class.md) örneği oluşturur. İkinci Oluşturucu `allocator_base` , her örnek için gibi bir örnek oluşturur `allocator_base<Type, _Sync>` `a` `allocator_base<Type, Sync>(allocator_base<Other, Sync>(a)) == a` .

## <a name="allocator_baseconst_pointer"></a><a name="const_pointer"></a>allocator_base:: const_pointer

Ayırıcı tarafından yönetilen nesne türüne sabit bir işaretçi sağlayan bir tür.

```cpp
typedef const Type *const_pointer;
```

## <a name="allocator_baseconst_reference"></a><a name="const_reference"></a>allocator_base:: const_reference

Ayırıcı tarafından yönetilen nesne türüne sabit bir başvuru sağlayan bir tür.

```cpp
typedef const Type& const_reference;
```

## <a name="allocator_baseconstruct"></a><a name="construct"></a>allocator_base:: yapı

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

Bu üye işlevi, çağırarak Kullanıcı tanımlı ayırıcı için uygulanır `new((void*)ptr Type(val)` .

## <a name="allocator_basedeallocate"></a><a name="deallocate"></a>allocator_base::d eallocate

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

Bu üye işlevi, `deallocate(ptr)` `Sync` `_Nx == 1` Aksi takdirde çağırarak, eşitleme filtresini çağırarak Kullanıcı tanımlı ayırıcı için uygulanır `operator delete(_Nx * ptr)` .

## <a name="allocator_basedestroy"></a><a name="destroy"></a>allocator_base::d estroy

Nesnenin depolandığı belleği ayırmayı kaldırmadan bir nesne yıkıcısı çağırır.

```cpp
void destroy(pointer ptr);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ptr*|Yok edilecek nesnenin adresini atayarak bir işaretçi.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, çağırarak Kullanıcı tanımlı ayırıcı için uygulanır `ptr->~Type()` .

## <a name="allocator_basedifference_type"></a><a name="difference_type"></a>allocator_base::d ifference_type

Ayırıcı tarafından yönetilen nesne türüne yönelik işaretçilerin değerleri arasındaki farkı temsil eden, işaretli bir tamsayı türü.

```cpp
typedef std::ptrdiff_t difference_type;
```

## <a name="allocator_basemax_size"></a><a name="max_size"></a>allocator_base:: max_size

`Type`Boş bellek kullanılmadan önce sınıf ayırıcı nesnesi tarafından ayrılabilecek türdeki öğe sayısını döndürür.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ayrılabilen öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi `(size_t)-1 / sizeof(Type)` `0 < (size_t)-1 / sizeof(Type)` , tersi durumda, Kullanıcı tanımlı ayırıcı için uygulanır `1` .

## <a name="allocator_basepointer"></a><a name="pointer"></a>allocator_base::p oınter

Ayırıcı tarafından yönetilen nesne türüne işaretçi sağlayan bir tür.

```cpp
typedef Type *pointer;
```

## <a name="allocator_basereference"></a><a name="reference"></a>allocator_base:: Reference

Ayırıcı tarafından yönetilen nesne türüne başvuru sağlayan bir tür.

```cpp
typedef Type& reference;
```

## <a name="allocator_basesize_type"></a><a name="size_type"></a>allocator_base:: size_type

Türünde bir nesnenin ayırabilecek herhangi bir dizinin uzunluğunu temsil eden işaretsiz bir tamsayı türü `allocator_base` .

```cpp
typedef std::size_t size_type;
```

## <a name="allocator_basevalue_type"></a><a name="value_type"></a>allocator_base:: value_type

Ayırıcı tarafından yönetilen bir tür.

```cpp
typedef Type value_type;
```

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators>](allocators-header.md)
