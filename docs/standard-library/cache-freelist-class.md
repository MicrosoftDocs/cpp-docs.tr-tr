---
title: cache_freelist sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::cache_freelist
- allocators/stdext::cache_freelist::allocate
- allocators/stdext::cache_freelist::deallocate
dev_langs:
- C++
helpviewer_keywords:
- stdext::cache_freelist
- stdext::cache_freelist [C++], allocate
- stdext::cache_freelist [C++], deallocate
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8478490914a6f9049cd54ec78c8de8a1e519f36f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="cachefreelist-class"></a>cache_freelist Sınıfı

Tanımlayan bir [ayırıcısı engelleme](../standard-library/allocators-header.md) ayırır ve bellek blokları tek bir boyutta kaldırır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Sz, class Max>
class cache_freelist
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Sz`|Ayrılacak dizideki öğelerin sayısı.|
|`Max`|Boş listenin en büyük boyutunu temsil eden max sınıfı. Bu, [max_fixed_size](../standard-library/max-fixed-size-class.md), [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), veya [max_variable_size](../standard-library/max-variable-size-class.md).|

## <a name="remarks"></a>Açıklamalar

Cache_freelist Şablon sınıfı bellek blok boyutu, boş bir listesini tutar `Sz`. Boş liste dolu olduğunda kullanan `operator delete` bellek ayırması için engeller. Boş liste boş olduğunda kullanan `operator new` yeni bellek bloğu ayrılamadı. Boş listenin en büyük boyutu en fazla sınıf geçirilen sınıfı tarafından belirlenen `Max` parametresi.

Her bellek bloğu tutan `Sz` bayt kullanılabilir bellek ve verileri, `operator new` ve `operator delete` gerektirir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[cache_freelist](#cache_freelist)|Türünde bir nesne oluşturur `cache_freelist`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bir bellek bloğu ayırır.|
|[Serbest bırakma](#deallocate)|Nesneleri belirtilen konumdaki depolama başından itibaren belirli sayıda boşaltır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<allocators >

**Namespace:** stdext

## <a name="allocate"></a>  cache_freelist::allocate

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

## <a name="cache_freelist"></a>  cache_freelist::cache_freelist

Türünde bir nesne oluşturur `cache_freelist`.

```cpp
cache_freelist();
```

### <a name="remarks"></a>Açıklamalar

## <a name="deallocate"></a>  cache_freelist::deallocate

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
