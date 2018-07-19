---
title: rts_alloc sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::rts_alloc
- allocators/stdext::rts_alloc::allocate
- allocators/stdext::rts_alloc::deallocate
- allocators/stdext::rts_alloc::equals
dev_langs:
- C++
helpviewer_keywords:
- stdext::rts_alloc
- stdext::rts_alloc [C++], allocate
- stdext::rts_alloc [C++], deallocate
- stdext::rts_alloc [C++], equals
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4bff519ea12646e94e92cde219fa38e4009a767
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956465"
---
# <a name="rtsalloc-class"></a>rts_alloc Sınıfı

Rts_alloc Şablon sınıfı tanımlar bir [filtre](../standard-library/allocators-header.md) tutan bir dizi önbellek örnekleri ve ayırmayı ve ayırmayı kaldırma yerine çalışma zamanında derleme zamanında kullanılmak üzere hangi örneğinin belirler.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class rts_alloc
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Önbellek örnekleri dizisi içinde yer alan türü. Bu, [cache_chunklist sınıfı](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md), veya [cache_suballoc](../standard-library/cache-suballoc-class.md).|

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıfı, birden fazla blok ayırıcı örnekleri tutan ve ayırma ya da ayırmayı kaldırma yerine çalışma zamanında derleme zamanında kullanılmak üzere hangi örneğinin belirler. Yeniden bağlamasını derlenemez derleyicilerle birlikte kullanılır.

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bir bellek bloğu ayırır.|
|[Serbest Bırak](#deallocate)|Belirtilen konumda depolama başından nesneleri belirtilen sayıda serbest bırakır.|
|[equals](#equals)|Eşitlik için iki önbellekler karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ayırıcılar >

**Namespace:** stdext

## <a name="allocate"></a>  rts_alloc::allocate

Bir bellek bloğu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sayısı*|Ayrılacak dizideki öğelerin sayısı.|

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış bir nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `caches[_IDX].allocate(count)`burada dizin `_IDX` istenen blok boyutu tarafından belirlenir *sayısı*, veya *sayısı* döndürür, çok büyük olduğundan `operator new(count)`. `cache`, önbellek nesnesini temsil eder.

## <a name="deallocate"></a>  rts_alloc::deallocate

Belirtilen konumda depolama başından nesneleri belirtilen sayıda serbest bırakır.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ptr*|Depolama alanından serbest bırakılması ilk nesneye bir işaretçi.|
|*Sayısı*|Depolama alanından serbest bırakılması nesne sayısı.|

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrıları `caches[_IDX].deallocate(ptr, count)`burada dizin `_IDX` istenen blok boyutu tarafından belirlenir *sayısı*, veya *sayısı* döndürür, çok büyük olduğundan `operator delete(ptr)`.

## <a name="equals"></a>  rts_alloc::Equals

Eşitlik için iki önbellekler karşılaştırır.

```cpp
bool equals(const sync<_Cache>& _Other) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*_Cache*|Filtreyle ilişkili önbellek nesnesi.|
|*_Diğer*|Eşitlik için karşılaştırma için önbellek nesnesi.|

### <a name="remarks"></a>Açıklamalar

**doğru** varsa sonucunu `caches[0].equals(other.caches[0])`; Aksi takdirde **false**. `caches` önbelleğe nesneler dizisi temsil eder.

## <a name="see-also"></a>Ayrıca bkz.

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)<br/>
[\<Ayırıcılar >](../standard-library/allocators-header.md)<br/>
