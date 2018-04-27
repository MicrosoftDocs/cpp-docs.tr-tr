---
title: cache_chunklist sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- allocators/stdext::cache_chunklist
- allocators/stdext::cache_chunklist::allocate
- allocators/stdext::cache_chunklist::deallocate
dev_langs:
- C++
helpviewer_keywords:
- stdext::cache_chunklist
- stdext::cache_chunklist [C++], allocate
- stdext::cache_chunklist [C++], deallocate
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f30cde375f05dbba30da58ad3e71aa5e9bac11c
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="cachechunklist-class"></a>cache_chunklist Sınıfı

Tanımlayan bir [ayırıcısı engelleme](../standard-library/allocators-header.md) ayırır ve bellek blokları tek bir boyutta kaldırır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Sz, std::size_t Nelts = 20>
class cache_chunklist
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Sz`|Ayrılacak dizideki öğelerin sayısı.|

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıfı kullanır `operator new` öbekleri ham bellek ayrılamadı suballocating engeller gerektiğinde bir bellek bloğu için ayrılacak; her öbek için ayrı bir ücretsiz listesinde deallocated bellek blokları depolar ve kullanır `operator delete` serbest bırakma için bir bellek blokları hiçbiri kullanımda olduğunda öbek.

Her bellek bloğu tutan `Sz` bayt kullanılabilir bellek ve ait öbek için bir işaretçi. Her bir öbeğin tutan `Nelts` bellek blokları, üç işaretçileri, int ve verileri, `operator new` ve `operator delete` gerektirir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[cache_chunklist](#cache_chunklist)|Türünde bir nesne oluşturur `cache_chunklist`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bir bellek bloğu ayırır.|
|[Serbest bırakma](#deallocate)|Nesneleri belirtilen konumdaki depolama başından itibaren belirli sayıda boşaltır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<allocators >

**Namespace:** stdext

## <a name="allocate"></a>  cache_chunklist::allocate

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

## <a name="cache_chunklist"></a>  cache_chunklist::cache_chunklist

Türünde bir nesne oluşturur `cache_chunklist`.

```cpp
cache_chunklist();
```

### <a name="remarks"></a>Açıklamalar

## <a name="deallocate"></a>  cache_chunklist::deallocate

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
