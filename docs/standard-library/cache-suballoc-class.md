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
ms.openlocfilehash: ccc01372d08edb997ed6b0aaa70be69fde60a1e2
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954329"
---
# <a name="cachesuballoc-class"></a>cache_suballoc Sınıfı

Tanımlayan bir [ayırıcı block](../standard-library/allocators-header.md) ayırır ve bellek blokları tek bir boyutta ayırmayı iptal eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Sz, size_t Nelts = 20>
class cache_suballoc
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*SZ*|Ayrılacak dizideki öğelerin sayısı.|

## <a name="remarks"></a>Açıklamalar

Cache_suballoc Şablon sınıfı sınırsız uzunlukta boş bir liste serbest bırakılmış bellek blokları depolar kullanarak `freelist<sizeof(Type), max_unbounded>`ve öğesinden daha büyük Öbek ile ayrılan bellek blokları suballocates **new işleci** boş liste olduğunda boş.

Her bir öbeği tutan `Sz * Nelts` kullanılabilir bellek ve verileri baytlık, **new işleci** ve **delete işleci** gerektirir. Ayrılmış öbekleri hiçbir zaman kurtulurlar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[cache_suballoc](#cache_suballoc)|Türünde bir nesne oluşturur `cache_suballoc`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bir bellek bloğu ayırır.|
|[Serbest Bırak](#deallocate)|Belirtilen konumda depolama başından nesneleri belirtilen sayıda serbest bırakır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ayırıcılar >

**Namespace:** stdext

## <a name="allocate"></a>  cache_suballoc::allocate

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

## <a name="cache_suballoc"></a>  cache_suballoc::cache_suballoc

Türünde bir nesne oluşturur `cache_suballoc`.

```cpp
cache_suballoc();
```

### <a name="remarks"></a>Açıklamalar

## <a name="deallocate"></a>  cache_suballoc::deallocate

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

## <a name="see-also"></a>Ayrıca bkz.

[\<Ayırıcılar >](../standard-library/allocators-header.md)<br/>
