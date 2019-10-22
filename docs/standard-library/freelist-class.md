---
title: freelist Sınıfı
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::freelist
- allocators/stdext::freelist::pop
- allocators/stdext::freelist::push
helpviewer_keywords:
- stdext::freelist
- stdext::freelist [C++], pop
- stdext::freelist [C++], push
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
ms.openlocfilehash: e37b2371238211033d6a8a0847a41677b4e908a2
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688050"
---
# <a name="freelist-class"></a>freelist Sınıfı

Bellek bloklarının listesini yönetir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Sz, class Max>
class freelist : public Max
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*SZ*|Ayrılacak dizideki öğelerin sayısı.|
|*Biçimlendir*|Ücretsiz listede depolanacak en fazla öğe sayısını temsil eden Max sınıfı. Max sınıfı [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), [max_fixed_size](../standard-library/max-fixed-size-class.md)veya [max_variable_size](../standard-library/max-variable-size-class.md)olabilir.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu *, en fazla*değer olarak geçirilen maksimum sınıf tarafından belirlenen listenin en fazla uzunluğu ile *SZ* boyutundaki bellek bloklarının listesini yönetir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[freelist](#freelist)|@No__t_0 türünde bir nesne oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[cağımız](#pop)|İlk bellek bloğunu ücretsiz listeden kaldırır.|
|[push](#push)|Listeye bir bellek bloğu ekler.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<allocators >

**Ad alanı:** stdext

## <a name="freelist"></a>freelist:: freelist

@No__t_0 türünde bir nesne oluşturur.

```cpp
freelist();
```

### <a name="remarks"></a>Açıklamalar

## <a name="pop"></a>freelist::p op

İlk bellek bloğunu ücretsiz listeden kaldırır.

```cpp
void *pop();
```

### <a name="return-value"></a>Dönüş Değeri

Listeden kaldırılan bellek bloğuna yönelik bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, liste boşsa NULL değerini döndürür. Aksi takdirde, ilk bellek bloğunu listeden kaldırır.

## <a name="push"></a>freelist::p USH

Listeye bir bellek bloğu ekler.

```cpp
bool push(void* ptr);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ptr*|Boş listeye eklenecek bellek bloğunun işaretçisi.|

### <a name="return-value"></a>Dönüş Değeri

Max sınıfının `full` işlevi **false**döndürürse **true** ; Aksi takdirde, `push` işlevi **false**döndürür.

### <a name="remarks"></a>Açıklamalar

Max sınıfının `full` işlevi **false**döndürürse, bu üye işlevi *PTR* tarafından işaret edilen bellek bloğunu listenin baş öğesine ekler.

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators >](../standard-library/allocators-header.md)
