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
ms.openlocfilehash: b0ec7d4d3dbe5ef1334bf3c394819a4f5235c28c
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688989"
---
# <a name="rts_alloc-class"></a>rts_alloc Sınıfı

Rts_alloc sınıf şablonu, bir dizi önbellek örneği tutan bir [filtre](../standard-library/allocators-header.md) tanımlar ve derleme zamanı yerine çalışma zamanında ayırma ve ayırmayı kaldırma için hangi örneği kullanacağınızı belirler.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class rts_alloc
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Dizide bulunan önbellek örneklerinin türü. Bu, [Cache_chunklist Class](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md)veya [cache_suballoc](../standard-library/cache-suballoc-class.md)olabilir.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu, birden çok blok ayırıcı örneği barındırır ve derleme süresi yerine çalışma zamanında ayırma veya ayırmayı kaldırma için hangi örneği kullanacağınızı belirler. Yeniden bağlama Derlenemeyen derleyiciler ile kullanılır.

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[kaldırmak](#deallocate)|Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.|
|[equals](#equals)|, Eşitlik için iki önbelleği karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<allocators >

**Ad alanı:** stdext

## <a name="allocate"></a>Rts_alloc:: allocate

Bellek bloğunu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*biriktirme*|Ayrılacak dizideki öğelerin sayısı.|

### <a name="return-value"></a>Dönüş Değeri

Ayrılan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, Dizin `_IDX` istenen blok boyutu *sayısı*tarafından belirlendiği `caches[_IDX].allocate(count)` döndürür veya *sayı* çok büyükse `operator new(count)` döndürür. Cache nesnesini temsil eden `cache`.

## <a name="deallocate"></a>Rts_alloc::d eallocate

Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ptr*|Depolamadan serbest bırakmak için ilk nesneye yönelik bir işaretçi.|
|*biriktirme*|Depolamadan serbest bırakmak için nesne sayısı.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi, Dizin `_IDX` istenen blok boyutu *sayısı*tarafından belirlendiği `caches[_IDX].deallocate(ptr, count)` çağırır veya *sayı* çok büyükse `operator delete(ptr)` döndürür.

## <a name="equals"></a>Rts_alloc:: Equals

, Eşitlik için iki önbelleği karşılaştırır.

```cpp
bool equals(const sync<_Cache>& _Other) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Önbellek*|Filtreyle ilişkili önbellek nesnesi.|
|*_Diğer*|Eşitlik için Karşılaştırılacak önbellek nesnesi.|

### <a name="remarks"></a>Açıklamalar

`caches[0].equals(other.caches[0])` sonucu olursa **true** ; Aksi takdirde, **false**. `caches`, önbellek nesnelerinin dizisini temsil eder.

## <a name="see-also"></a>Ayrıca bkz.

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) \
[\<allocators >](../standard-library/allocators-header.md)
