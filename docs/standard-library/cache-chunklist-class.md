---
title: cache_chunklist sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 808340df89bb548fee57604f25409c117933cc4e
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953266"
---
# <a name="cachechunklist-class"></a>cache_chunklist Sınıfı

Tanımlayan bir [ayırıcı block](../standard-library/allocators-header.md) ayırır ve bellek blokları tek bir boyutta ayırmayı iptal eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Sz, std::size_t Nelts = 20>
class cache_chunklist
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*SZ*|Ayrılacak dizideki öğelerin sayısı.|

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıfının kullandığı **new işleci** öbekleri ham bellek ayırmak için suballocating engeller gerektiğinde bir bellek bloğu için ayrılacak; her öbek için ayrı bir ücretsiz listesinde serbest bırakılmış bellek blokları depolar ve kullanır**delete işleci** kendi bellek blokları hiçbiri kullanımda olduğunda bir öbek serbest bırakmak.

Her bellek bloğu şunları tutar *Sz* bayt cinsinden kullanılabilir bellek ve ait olduğu öbek için bir işaretçi. Her bir öbeği tutan `Nelts` bellek blokları, üç işaretçileri, int ve verileri, **new işleci** ve **delete işleci** gerektirir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[cache_chunklist](#cache_chunklist)|Türünde bir nesne oluşturur `cache_chunklist`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bir bellek bloğu ayırır.|
|[Serbest Bırak](#deallocate)|Belirtilen konumda depolama başından nesneleri belirtilen sayıda serbest bırakır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ayırıcılar >

**Namespace:** stdext

## <a name="allocate"></a>  cache_chunklist::allocate

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

## <a name="cache_chunklist"></a>  cache_chunklist::cache_chunklist

Türünde bir nesne oluşturur `cache_chunklist`.

```cpp
cache_chunklist();
```

### <a name="remarks"></a>Açıklamalar

## <a name="deallocate"></a>  cache_chunklist::deallocate

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
