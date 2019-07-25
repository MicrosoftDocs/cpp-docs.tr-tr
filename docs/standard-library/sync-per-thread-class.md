---
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
ms.openlocfilehash: a08aa13aa46d5181e7c874b132b2bcbd5ec26dee
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450259"
---
# <a name="syncperthread-class"></a>sync_per_thread Sınıfı

Her iş parçacığı için ayrı bir önbellek nesnesi sağlayan bir [eşitleme filtresi](../standard-library/allocators-header.md) tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class sync_per_thread
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresiyle ilişkili önbelleğin türü. Bu, [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md)veya [cache_suballoc](../standard-library/cache-suballoc-class.md)olabilir.|

## <a name="remarks"></a>Açıklamalar

Bir iş parçacığında ayrılan `sync_per_thread` blokların başka bir iş parçacığından serbest bırakılmasa bile, kullanan ayırıcılar eşit olarak karşılaştırılabilir. Bu ayırıcıların birini kullanırken, bir iş parçacığında ayrılan bellek bloklarından biri, diğer iş parçacıkları tarafından görünür yapılmamalıdır. Bu, bu ayırıcılardan birini kullanan bir kapsayıcının yalnızca tek bir iş parçacığı tarafından erişilmesi anlamına gelir.

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[kaldırmak](#deallocate)|Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.|
|[equals](#equals)|, Eşitlik için iki önbelleği karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<ayrıcılar >

**Ad alanı:** stdext

## <a name="allocate"></a>sync_per_thread:: allocate

Bellek bloğunu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*biriktirme*|Ayrılacak dizideki öğelerin sayısı.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi, geçerli iş parçacığına ait olan Cache nesnesindeki `cache::allocate(count)` bir çağrının sonucunu döndürür. Geçerli iş parçacığı için bir önbellek nesnesi ayrılmışsa, önce bir tane ayırır.

## <a name="deallocate"></a>sync_per_thread::d eallocate

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

Üye işlevi, geçerli `deallocate` iş parçacığına ait olan Cache nesnesi üzerinde çağırır. Geçerli iş parçacığı için bir önbellek nesnesi ayrılmışsa, önce bir tane ayırır.

## <a name="equals"></a>sync_per_thread:: Equals

, Eşitlik için iki önbelleği karşılaştırır.

```cpp
bool equals(const sync<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresinin önbellek nesnesi.|
|*Diğer*|Eşitlik için Karşılaştırılacak önbellek nesnesi.|

### <a name="return-value"></a>Dönüş Değeri

Bu nesne için veya geçerli iş parçacığında *başka* bir önbellek nesnesi ayrılmamışsa **false** . Aksi takdirde, iki önbellek nesnesine uygulamanın `operator==` sonucunu döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<ayrıcılar >](../standard-library/allocators-header.md)
