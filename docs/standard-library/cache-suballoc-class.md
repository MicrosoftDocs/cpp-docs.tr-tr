---
title: cache_suballoc sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::cache_suballoc
- allocators/stdext::cache_suballoc::allocate
- allocators/stdext::cache_suballoc::deallocate
dev_langs:
- C++
helpviewer_keywords:
- stdext::cache_suballoc
- stdext::cache_suballoc [C++], allocate
- stdext::cache_suballoc [C++], deallocate
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28dc4e52e2f114600ad3a22697500ce9d8594113
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33850313"
---
# <a name="cachesuballoc-class"></a>cache_suballoc Sınıfı

Tanımlayan bir [ayırıcısı engelleme](../standard-library/allocators-header.md) ayırır ve bellek blokları tek bir boyutta kaldırır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Sz, size_t Nelts = 20>
class cache_suballoc
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Sz`|Ayrılacak dizideki öğelerin sayısı.|

## <a name="remarks"></a>Açıklamalar

Cache_suballoc Şablon sınıfı deallocated bellek blokları sınırsız uzunluğu, boş bir listeyle depolar kullanarak `freelist<sizeof(Type), max_unbounded>`ve daha büyük bir Öbek ile ayrılan gelen bellek blokları suballocates `operator new` boş liste olduğunda boş.

Her bir öbeğin tutan `Sz * Nelts` bayt kullanılabilir bellek ve verileri, `operator new` ve `operator delete` gerektirir. Ayrılmış öbekleri hiçbir zaman kurtulurlar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[cache_suballoc](#cache_suballoc)|Türünde bir nesne oluşturur `cache_suballoc`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bir bellek bloğu ayırır.|
|[Serbest bırakma](#deallocate)|Nesneleri belirtilen konumdaki depolama başından itibaren belirli sayıda boşaltır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<allocators >

**Namespace:** stdext

## <a name="allocate"></a>  cache_suballoc::allocate

Bir bellek bloğu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`count`|Ayrılacak dizideki öğelerin sayısı.|

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış nesnesine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cache_suballoc"></a>  cache_suballoc::cache_suballoc

Türünde bir nesne oluşturur `cache_suballoc`.

```cpp
cache_suballoc();
```

### <a name="remarks"></a>Açıklamalar

## <a name="deallocate"></a>  cache_suballoc::deallocate

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

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators >](../standard-library/allocators-header.md)<br/>
