---
title: sync_per_thread sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::sync_per_thread
- allocators/stdext::sync_per_thread::allocate
- allocators/stdext::sync_per_thread::deallocate
- allocators/stdext::sync_per_thread::equals
dev_langs:
- C++
helpviewer_keywords:
- stdext::sync_per_thread
- stdext::sync_per_thread [C++], allocate
- stdext::sync_per_thread [C++], deallocate
- stdext::sync_per_thread [C++], equals
ms.assetid: 47bf75f8-5b02-4760-b1d3-3099d08fe14c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e366f9b0cf92aed9c61609642f48f0e5cc9530d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858776"
---
# <a name="syncperthread-class"></a>sync_per_thread Sınıfı

Açıklayan bir [eşitleme filtresi](../standard-library/allocators-header.md) , her iş parçacığı için ayrı önbellek nesnesi sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Cache>
class sync_per_thread
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Cache`|Eşitleme filtresiyle ilişkili önbellek türü. Bu, [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md), veya [cache_suballoc](../standard-library/cache-suballoc-class.md).|

## <a name="remarks"></a>Açıklamalar

Kullanmak allocators `sync_per_thread` bir iş parçacığı ayrılan blok başka bir iş parçacığından serbest olamaz olsa bile eşit karşılaştırabilirsiniz. Ayrılan bu allocators bellek blokları birini kullanarak, bir iş parçacığı için başka bir iş parçacığı görünür yapılmaması gerekir. Uygulamada bu allocators birini kullanan bir kapsayıcı yalnızca tek bir iş parçacığı tarafından erişilmelidir anlamına gelir.

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bir bellek bloğu ayırır.|
|[Serbest bırakma](#deallocate)|Nesneleri belirtilen konumdaki depolama başından itibaren belirli sayıda boşaltır.|
|[equals](#equals)|Eşitlik için iki önbellekleri karşılaştırır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<allocators >

**Namespace:** stdext

## <a name="allocate"></a>  sync_per_thread::allocate

Bir bellek bloğu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`count`|Ayrılacak dizideki öğelerin sayısı.|

### <a name="remarks"></a>Açıklamalar

Üye işlevi için bir çağrı sonucunu döndürür `cache::allocate(count)` geçerli iş parçacığına ait önbellek nesnesi üzerinde. Önbellek nesnesi için geçerli iş parçacığının ayrıldı, onu önce bir ayırır.

## <a name="deallocate"></a>  sync_per_thread::deallocate

Nesneleri belirtilen konumdaki depolama başından itibaren belirli sayıda boşaltır.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`ptr`|Depolama biriminden bırakılmasına ilk nesne için bir işaretçi.|
|`count`|Depolama biriminden bırakılmasına nesnelerin sayısı.|

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrılarını `deallocate` geçerli iş parçacığına ait önbellek nesnesi üzerinde. Önbellek nesnesi için geçerli iş parçacığının ayrıldı, onu önce bir ayırır.

## <a name="equals"></a>  sync_per_thread::Equals

Eşitlik için iki önbellekleri karşılaştırır.

```cpp
bool equals(const sync<Cache>& Other) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Cache`|Eşitleme filtresi önbellek nesnesi.|
|`Other`|Eşitlik için karşılaştırmak için önbellek nesnesi.|

### <a name="return-value"></a>Dönüş Değeri

`false` önbellek nesnesi yok veya bu nesne için ayrıldı, `Other` geçerli iş parçacığında. Aksi takdirde, uygulamanın sonucu döndürür `operator==` iki nesneleri önbelleğe almak için.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators >](../standard-library/allocators-header.md)<br/>
