---
title: cache_freelist Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_freelist
- allocators/stdext::cache_freelist::allocate
- allocators/stdext::cache_freelist::deallocate
helpviewer_keywords:
- stdext::cache_freelist
- stdext::cache_freelist [C++], allocate
- stdext::cache_freelist [C++], deallocate
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
ms.openlocfilehash: d7840d114acfa0f3daa01c8dfdb6c6114829d93d
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689909"
---
# <a name="cache_freelist-class"></a>cache_freelist Sınıfı

Tek boyuttaki bellek bloklarını ayıran ve ayıran [blok ayırıcıyı](../standard-library/allocators-header.md) tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Sz, class Max>
class cache_freelist
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*SZ*|Ayrılacak dizideki öğelerin sayısı.|
|*Biçimlendir*|Ücretsiz listenin en büyük boyutunu temsil eden en büyük sınıf. Bu, [max_fixed_size](../standard-library/max-fixed-size-class.md), [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md)veya [max_variable_size](../standard-library/max-variable-size-class.md)olabilir.|

## <a name="remarks"></a>Açıklamalar

Cache_freelist sınıf şablonu, *SZ*boyutundaki bellek bloklarının boş bir listesini tutar. Ücretsiz liste dolduğunda, bellek bloklarını serbest bırakmak için **işleç Delete** kullanır. Ücretsiz liste boş olduğunda yeni bellek blokları ayırmak için **New işlecini** kullanır. Ücretsiz listenin en büyük boyutu, *en* büyük parametrede geçirilen sınıf en büyük sınıfına göre belirlenir.

Her bellek bloğunda, kullanılabilir bellek ve **New işleci** ve **delete işleci** için gerekli bellek bulunur.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[cache_freelist](#cache_freelist)|@No__t_0 türünde bir nesne oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[kaldırmak](#deallocate)|Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<allocators >

**Ad alanı:** stdext

## <a name="allocate"></a>cache_freelist:: allocate

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

## <a name="cache_freelist"></a>cache_freelist::cache_freelist

@No__t_0 türünde bir nesne oluşturur.

```cpp
cache_freelist();
```

### <a name="remarks"></a>Açıklamalar

## <a name="deallocate"></a>cache_freelist::d eallocate

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
