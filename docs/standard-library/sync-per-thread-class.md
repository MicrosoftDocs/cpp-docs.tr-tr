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
ms.openlocfilehash: 3cb1946ee68642065488cfd13c146abab818ec60
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412325"
---
# <a name="syncperthread-class"></a>sync_per_thread Sınıfı

Açıklayan bir [eşitleme filtresi](../standard-library/allocators-header.md) her iş parçacığı için ayrı önbellek nesnesi sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class sync_per_thread
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresiyle ilişkili önbellek türü. Bu, [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md), veya [cache_suballoc](../standard-library/cache-suballoc-class.md).|

## <a name="remarks"></a>Açıklamalar

Kullanan ayırıcılar `sync_per_thread` başka bir iş parçacığından bir iş parçacığına ayrılan blokları serbest bırakılması kullanılamaz halde eşit karşılaştırabilirsiniz. Bu ayırıcılar bellek blokları birini kullanarak ayrıldığı zaman tek bir iş parçacığı için diğer iş parçacıklarını görünür yapılmaması gerekir. Uygulamada bu ayırıcılar birini kullanan bir kapsayıcı yalnızca tek bir iş parçacığı tarafından erişilmelidir anlamına gelir.

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bir bellek bloğu ayırır.|
|[Serbest Bırak](#deallocate)|Belirtilen konumda depolama başından nesneleri belirtilen sayıda serbest bırakır.|
|[equals](#equals)|Eşitlik için iki önbellekler karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ayırıcılar >

**Namespace:** stdext

## <a name="allocate"></a>  sync_per_thread::allocate

Bir bellek bloğu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sayısı*|Ayrılacak dizideki öğelerin sayısı.|

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrısı sonucunu döndürür `cache::allocate(count)` geçerli iş parçacığına ait önbellek nesnesini üzerinde. Hiçbir önbellek nesnesi geçerli iş parçacığı için ayrıldı, onu önce bir ayırır.

## <a name="deallocate"></a>  sync_per_thread::deallocate

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

Üye işlev çağrıları `deallocate` geçerli iş parçacığına ait önbellek nesnesini üzerinde. Hiçbir önbellek nesnesi geçerli iş parçacığı için ayrıldı, onu önce bir ayırır.

## <a name="equals"></a>  sync_per_thread::Equals

Eşitlik için iki önbellekler karşılaştırır.

```cpp
bool equals(const sync<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Önbellek*|Eşitleme filtresi önbellek nesnesi.|
|*Diğer*|Eşitlik için karşılaştırma için önbellek nesnesi.|

### <a name="return-value"></a>Dönüş Değeri

**false** önbellek nesnesi yok veya bu nesne için ayrıldı, *diğer* geçerli iş parçacığındaki. Aksi halde sonucu döndürür `operator==` iki önbellek nesnelere.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<Ayırıcılar >](../standard-library/allocators-header.md)<br/>
