---
description: 'Daha fazla bilgi edinin: freelist Sınıfı'
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
ms.openlocfilehash: de0803aac13138dc25116084f52e7a5bea694b41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324378"
---
# <a name="freelist-class"></a>freelist Sınıfı

Bellek bloklarının listesini yönetir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Sz, class Max>
class freelist : public Max
```

### <a name="parameters"></a>Parametreler

*SZ*\
Ayrılacak dizideki öğelerin sayısı.

*Biçimlendir*\
Ücretsiz listede depolanacak en fazla öğe sayısını temsil eden Max sınıfı. Max sınıfı [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), [max_fixed_size](../standard-library/max-fixed-size-class.md)veya [max_variable_size](../standard-library/max-variable-size-class.md)olabilir.

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu *, en fazla* değer olarak geçirilen maksimum sınıf tarafından belirlenen listenin en fazla uzunluğu ile *SZ* boyutundaki bellek bloklarının listesini yönetir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[freelist](#freelist)|Türünde bir nesne oluşturur `freelist` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[cağımız](#pop)|İlk bellek bloğunu ücretsiz listeden kaldırır.|
|[push](#push)|Listeye bir bellek bloğu ekler.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<allocators>

**Ad alanı:** stdext

## <a name="freelistfreelist"></a><a name="freelist"></a> freelist:: freelist

Türünde bir nesne oluşturur `freelist` .

```cpp
freelist();
```

### <a name="remarks"></a>Açıklamalar

## <a name="freelistpop"></a><a name="pop"></a> freelist::p op

İlk bellek bloğunu ücretsiz listeden kaldırır.

```cpp
void *pop();
```

### <a name="return-value"></a>Dönüş Değeri

Listeden kaldırılan bellek bloğuna yönelik bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, liste boşsa NULL değerini döndürür. Aksi takdirde, ilk bellek bloğunu listeden kaldırır.

## <a name="freelistpush"></a><a name="push"></a> freelist::p USH

Listeye bir bellek bloğu ekler.

```cpp
bool push(void* ptr);
```

### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Boş listeye eklenecek bellek bloğunun işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

**`true`**`full`Max sınıfının işlevi döndürürse **`false`** ; Aksi takdirde, `push` işlev döndürür **`false`** .

### <a name="remarks"></a>Açıklamalar

`full`Max sınıfının işlevi döndürürse **`false`** , bu üye işlevi *PTR* tarafından işaret edilen bellek bloğunu listenin baş öğesine ekler.

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators>](../standard-library/allocators-header.md)
