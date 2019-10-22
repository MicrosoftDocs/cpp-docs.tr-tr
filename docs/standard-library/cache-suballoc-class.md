---
title: cache_suballoc Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_suballoc
- allocators/stdext::cache_suballoc::allocate
- allocators/stdext::cache_suballoc::deallocate
helpviewer_keywords:
- stdext::cache_suballoc
- stdext::cache_suballoc [C++], allocate
- stdext::cache_suballoc [C++], deallocate
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
ms.openlocfilehash: 7a21f0c4f81277200ff069baf751fa013a3c0cea
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688352"
---
# <a name="cache_suballoc-class"></a>cache_suballoc Sınıfı

Tek boyuttaki bellek bloklarını ayıran ve ayıran [blok ayırıcıyı](../standard-library/allocators-header.md) tanımlar.

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

Cache_suballoc sınıf şablonu, serbest bırakılmış bellek bloklarını, `freelist<sizeof(Type), max_unbounded>` kullanarak ve boş bir liste boş olduğunda **Yeni işleç** ile ayrılmış daha büyük bir öbekten, alt ayırır.

Her öbek kullanılabilir bellek `Sz * Nelts` bayt ve yeni ve **işleç silme** **işleci** için gerekli olan verileri bulundurur. Ayrılan parçalar hiçbir şekilde serbest bırakılmaz.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[cache_suballoc](#cache_suballoc)|@No__t_0 türünde bir nesne oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[allocate](#allocate)|Bellek bloğunu ayırır.|
|[kaldırmak](#deallocate)|Belirli bir konumdan başlayarak depolama alanından belirtilen sayıda nesneyi serbest bırakır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<allocators >

**Ad alanı:** stdext

## <a name="allocate"></a>cache_suballoc:: allocate

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

## <a name="cache_suballoc"></a>cache_suballoc::cache_suballoc

@No__t_0 türünde bir nesne oluşturur.

```cpp
cache_suballoc();
```

### <a name="remarks"></a>Açıklamalar

## <a name="deallocate"></a>cache_suballoc::d eallocate

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
