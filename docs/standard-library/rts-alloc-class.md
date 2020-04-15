---
title: rts_alloc Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::rts_alloc
- allocators/stdext::rts_alloc::allocate
- allocators/stdext::rts_alloc::deallocate
- allocators/stdext::rts_alloc::equals
helpviewer_keywords:
- stdext::rts_alloc
- stdext::rts_alloc [C++], allocate
- stdext::rts_alloc [C++], deallocate
- stdext::rts_alloc [C++], equals
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
ms.openlocfilehash: 6ed84d906944a09fa355e281640e9480f3173554
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373421"
---
# <a name="rts_alloc-class"></a>rts_alloc Sınıfı

rts_alloc sınıf şablonu, bir dizi önbellek örneği tutan ve derleme zamanında yerine çalışma zamanında ayırma ve ayırma için hangi örneğin kullanılacağını belirleyen bir [filtreyi](../standard-library/allocators-header.md) açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class rts_alloc
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Dizide bulunan önbellek örneklerinin türü. Bu [sınıf cache_chunklist](../standard-library/cache-chunklist-class.md)olabilir , [cache_freelist](../standard-library/cache-freelist-class.md), veya [cache_suballoc](../standard-library/cache-suballoc-class.md).|

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu birden çok blok ayırıcı örnek tutar ve derleme zamanında yerine çalışma zamanında ayırma veya ayırma için hangi örneğin kullanılacağını belirler. Rebind'i derleyemeyen derleyicilerle kullanılır.

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[Ayırması](#deallocate)|Belirli bir konumdan başlayarak belirli sayıda nesneyi depolamadan serbest sağlar.|
|[equals](#equals)|Eşitlik için iki önbellek karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<tahsisörler>

**Ad alanı:** stdext

## <a name="rts_allocallocate"></a><a name="allocate"></a>rts_alloc::allocate

Bellek bloğunu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sayısı*|Dizideki ayrılacak öğe sayısı.|

### <a name="return-value"></a>Dönüş Değeri

Ayrılan nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlev `caches[_IDX].allocate(count)`döndürür `_IDX` , dizin istenen blok boyutu *sayısına*göre belirlenir, veya `operator new(count)` *sayısı* çok büyükse, döndürür. `cache`, önbellek nesnesini temsil eder.

## <a name="rts_allocdeallocate"></a><a name="deallocate"></a>rts_alloc::d

Belirli bir konumdan başlayarak belirli sayıda nesneyi depolamadan serbest sağlar.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Ptr*|Depolamadan ayrılacak ilk nesneye işaretçi.|
|*Sayısı*|Depolamadan ayrılacak nesne sayısı.|

### <a name="remarks"></a>Açıklamalar

Üye işlev `caches[_IDX].deallocate(ptr, count)`çağrıları , `_IDX` dizin istenen blok boyutu *sayısı*tarafından belirlenir , veya *sayısı* çok büyükse, döndürür `operator delete(ptr)`.

## <a name="rts_allocequals"></a><a name="equals"></a>rts_alloc::eşittir

Eşitlik için iki önbellek karşılaştırır.

```cpp
bool equals(const sync<_Cache>& _Other) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Cache*|Filtreyle ilişkili önbellek nesnesi.|
|*_Other*|Eşitlik için karşılaştırılacak önbellek nesnesi.|

### <a name="remarks"></a>Açıklamalar

**doğru** eğer sonucu `caches[0].equals(other.caches[0])`; aksi takdirde, **yanlış**. `caches`önbellek nesnelerinin dizisini temsil eder.

## <a name="see-also"></a>Ayrıca bkz.

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)\
[\<tahsisat>](../standard-library/allocators-header.md)
