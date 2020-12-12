---
description: 'Hakkında daha fazla bilgi edinin: sync_per_thread sınıfı'
title: sync_per_thread Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_per_thread
- allocators/stdext::sync_per_thread::allocate
- allocators/stdext::sync_per_thread::deallocate
- allocators/stdext::sync_per_thread::equals
helpviewer_keywords:
- stdext::sync_per_thread
- stdext::sync_per_thread [C++], allocate
- stdext::sync_per_thread [C++], deallocate
- stdext::sync_per_thread [C++], equals
ms.assetid: 47bf75f8-5b02-4760-b1d3-3099d08fe14c
ms.openlocfilehash: dbce0441e32c97907bdf2cc5831a94c9af125453
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183301"
---
# <a name="sync_per_thread-class"></a>sync_per_thread Sınıfı

Her iş parçacığı için ayrı bir önbellek nesnesi sağlayan bir [eşitleme filtresi](../standard-library/allocators-header.md) tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class sync_per_thread
```

### <a name="parameters"></a>Parametreler

*Önbellek*\
Eşitleme filtresiyle ilişkili önbelleğin türü. [`cache_chunklist`](../standard-library/cache-chunklist-class.md), [`cache_freelist`](../standard-library/cache-freelist-class.md) Veya olabilir [`cache_suballoc`](../standard-library/cache-suballoc-class.md) .

## <a name="remarks"></a>Açıklamalar

`sync_per_thread`Bir iş parçacığında ayrılan blokların başka bir iş parçacığından serbest bırakılmasa bile, kullanan ayırıcılar eşit olarak karşılaştırılabilir. Bu ayırıcıların birini kullanırken, bir iş parçacığında ayrılan bellek bloklarından biri, diğer iş parçacıkları tarafından görünür yapılmamalıdır. Bu, bu ayırıcılardan birini kullanan bir kapsayıcının yalnızca tek bir iş parçacığı tarafından erişilmesi anlamına gelir.

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[kaldırmak](#deallocate)|Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.|
|[eşittir](#equals)|, Eşitlik için iki önbelleği karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<allocators>

**Ad alanı:** stdext

## <a name="sync_per_threadallocate"></a><a name="allocate"></a> sync_per_thread:: ayır

Bellek bloğunu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

*biriktirme*\
Ayrılacak dizideki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `cache::allocate(count)` geçerli iş parçacığına ait olan Cache nesnesindeki bir çağrının sonucunu döndürür. Geçerli iş parçacığı için bir önbellek nesnesi ayrılmışsa, önce bir tane ayırır.

## <a name="sync_per_threaddeallocate"></a><a name="deallocate"></a> sync_per_thread::d eallocate

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

Üye işlevi, `deallocate` geçerli iş parçacığına ait olan Cache nesnesi üzerinde çağırır. Geçerli iş parçacığı için bir önbellek nesnesi ayrılmışsa, önce bir tane ayırır.

## <a name="sync_per_threadequals"></a><a name="equals"></a> sync_per_thread:: Equals

, Eşitlik için iki önbelleği karşılaştırır.

```cpp
bool equals(const sync<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

*Önbellek*\
Eşitleme filtresinin önbellek nesnesi.

*Farklı*\
Eşitlik için Karşılaştırılacak önbellek nesnesi.

### <a name="return-value"></a>Dönüş Değeri

**`false`** Bu nesne için veya geçerli iş parçacığında *başka* bir önbellek nesnesi ayrılmışsa. Aksi takdirde, `operator==` iki önbellek nesnesine uygulamanın sonucunu döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators>](../standard-library/allocators-header.md)
