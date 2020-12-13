---
description: 'Hakkında daha fazla bilgi edinin: rts_alloc sınıfı'
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
ms.openlocfilehash: b2fe4bf3fe3f54e8fe1de3d89605280b2ba2b857
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148947"
---
# <a name="rts_alloc-class"></a>rts_alloc Sınıfı

Rts_alloc sınıf şablonu, bir dizi önbellek örneği tutan ve derleme süresi yerine çalışma zamanında ayırma ve ayırmayı kaldırma için hangi örneği kullanacağınızı belirleyen bir [filtre](../standard-library/allocators-header.md) tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class rts_alloc
```

### <a name="parameters"></a>Parametreler

*Önbellek*\
Dizide bulunan önbellek örneklerinin türü. [`cache_chunklist`](../standard-library/cache-chunklist-class.md), [`cache_freelist`](../standard-library/cache-freelist-class.md) Veya olabilir [`cache_suballoc`](../standard-library/cache-suballoc-class.md) .

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu, birden çok blok ayırıcı örneği barındırır ve derleme süresi yerine çalışma zamanında ayırma veya ayırmayı kaldırma için hangi örneği kullanacağınızı belirler. Yeniden bağlama Derlenemeyen derleyiciler ile kullanılır.

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[kaldırmak](#deallocate)|Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.|
|[eşittir](#equals)|, Eşitlik için iki önbelleği karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<allocators>

**Ad alanı:** stdext

## <a name="rts_allocallocate"></a><a name="allocate"></a> rts_alloc:: ayır

Bellek bloğunu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Ayrılacak dizideki öğelerin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Ayrılan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi `caches[_IDX].allocate(count)` , dizinin `_IDX` istenen blok boyutu *sayısı* tarafından belirlendiği, veya *Count* çok büyükse, öğesini döndürür `operator new(count)` . `cache`, önbellek nesnesini temsil eder.

## <a name="rts_allocdeallocate"></a><a name="deallocate"></a> rts_alloc::d eallocate

Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Depolamadan serbest bırakmak için ilk nesneye yönelik bir işaretçi.

*biriktirme*\
Depolamadan serbest bırakmak için nesne sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi `caches[_IDX].deallocate(ptr, count)` , dizinin `_IDX` istenen blok boyutu *sayısı* tarafından belirlendiği, ya da *Count* çok büyükse, döndürür `operator delete(ptr)` .

## <a name="rts_allocequals"></a><a name="equals"></a> rts_alloc:: Equals

, Eşitlik için iki önbelleği karşılaştırır.

```cpp
bool equals(const sync<_Cache>& _Other) const;
```

### <a name="parameters"></a>Parametreler

*_Cache*\
Filtreyle ilişkili önbellek nesnesi.

*_Other*\
Eşitlik için Karşılaştırılacak önbellek nesnesi.

### <a name="remarks"></a>Açıklamalar

**`true`** Sonuç olarak `caches[0].equals(other.caches[0])` , aksi durumda, **`false`** . `caches` önbellek nesnelerinin dizisini temsil eder.

## <a name="see-also"></a>Ayrıca bkz.

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)\
[\<allocators>](../standard-library/allocators-header.md)
