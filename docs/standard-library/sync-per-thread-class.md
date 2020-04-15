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
ms.openlocfilehash: 2976cdc6671750f0da439e9eb42053518e4af8d9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376537"
---
# <a name="sync_per_thread-class"></a>sync_per_thread Sınıfı

Her iş parçacığı için ayrı bir önbellek nesnesi sağlayan bir [eşitleme filtresi](../standard-library/allocators-header.md) açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class sync_per_thread
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresiyle ilişkili önbellek türü. Bu [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md)veya [cache_suballoc](../standard-library/cache-suballoc-class.md)olabilir.|

## <a name="remarks"></a>Açıklamalar

Bir iş parçacığına ayrılan bloklar başka bir iş parçacığından ayrılamasa da, kullanılan `sync_per_thread` ayırıcılar eşit olarak karşılaştırılabilir. Bu ayırıcılardan biri kullanırken, bir iş parçacığına ayrılan bellek blokları diğer iş parçacıkları tarafından görünür hale getirilmemelidir. Uygulamada bu, bu ayırıcılardan birini kullanan bir kapsayıcıya yalnızca tek bir iş parçacığı tarafından erişilmesi gerektiği anlamına gelir.

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[Ayırması](#deallocate)|Belirli bir konumdan başlayarak belirli sayıda nesneyi depolamadan serbest sağlar.|
|[equals](#equals)|Eşitlik için iki önbellek karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<tahsisörler>

**Ad alanı:** stdext

## <a name="sync_per_threadallocate"></a><a name="allocate"></a>sync_per_thread::allocate

Bellek bloğunu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sayısı*|Dizideki ayrılacak öğe sayısı.|

### <a name="remarks"></a>Açıklamalar

Üye işlev, geçerli iş parçacığına `cache::allocate(count)` ait önbellek nesnesine yapılan bir çağrının sonucunu döndürür. Geçerli iş parçacığı için önbellek nesnesi ayrılmamışsa, önce bir önbellek ayırır.

## <a name="sync_per_threaddeallocate"></a><a name="deallocate"></a>sync_per_thread::deallocate

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

Üye işlev, `deallocate` geçerli iş parçacığına ait önbellek nesnesini çağırır. Geçerli iş parçacığı için önbellek nesnesi ayrılmamışsa, önce bir önbellek ayırır.

## <a name="sync_per_threadequals"></a><a name="equals"></a>sync_per_thread::eşittir

Eşitlik için iki önbellek karşılaştırır.

```cpp
bool equals(const sync<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresinin önbellek nesnesi.|
|*Diğer*|Eşitlik için karşılaştırılacak önbellek nesnesi.|

### <a name="return-value"></a>Dönüş Değeri

bu nesne için veya geçerli iş parçacığındaki *Diğer* için önbellek nesnesi ayrılmamışsa **false.** Aksi takdirde, iki önbellek `operator==` nesnelerine uygulama sonucunu döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<tahsisat>](../standard-library/allocators-header.md)
