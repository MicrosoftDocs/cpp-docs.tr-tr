---
title: cache_chunklist Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_chunklist
- allocators/stdext::cache_chunklist::allocate
- allocators/stdext::cache_chunklist::deallocate
helpviewer_keywords:
- stdext::cache_chunklist
- stdext::cache_chunklist [C++], allocate
- stdext::cache_chunklist [C++], deallocate
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
ms.openlocfilehash: 035e5153b4e4c84743a64bcc9cec24920a6a0336
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688359"
---
# <a name="cache_chunklist-class"></a>cache_chunklist Sınıfı

Tek boyuttaki bellek bloklarını ayıran ve ayıran [blok ayırıcıyı](../standard-library/allocators-header.md) tanımlar.

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

Bu sınıf şablonu, gerektiğinde bir bellek bloğu için depolama alanı ayırmak üzere alt ayırma blokları, ham bellek öbeklerini ayırmak için **New işlecini** kullanır; serbest bırakılmış bellek bloklarını her bir öbek için ayrı bir ücretsiz listede depolar ve herhangi bir bellek bloğu kullanımda olduğunda bir öbeği serbest bırakmak için **işleç silme** kullanır.

Her bellek bloğunda, kullanılabilir bellek ve onun ait olduğu öbek için bir işaretçi bulunur. Her bir öbek `Nelts` bellek bloklarını, üç işaretçiyi, bir int ve **New** ve **Delete** işlecini içeren verileri içerir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[cache_chunklist](#cache_chunklist)|@No__t_0 türünde bir nesne oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[kaldırmak](#deallocate)|Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<allocators >

**Ad alanı:** stdext

## <a name="allocate"></a>cache_chunklist:: allocate

Bellek bloğunu ayırır.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*biriktirme*|Ayrılacak dizideki öğelerin sayısı.|

### <a name="return-value"></a>Dönüş Değeri

Ayrılan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cache_chunklist"></a>cache_chunklist::cache_chunklist

@No__t_0 türünde bir nesne oluşturur.

```cpp
cache_chunklist();
```

### <a name="remarks"></a>Açıklamalar

## <a name="deallocate"></a>cache_chunklist::d eallocate

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

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators >](../standard-library/allocators-header.md)
