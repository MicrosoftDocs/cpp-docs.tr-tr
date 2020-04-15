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
ms.openlocfilehash: 712c1f1638b954d1580eb527dd9eab7401917517
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317201"
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
|*Sz*|Dizideki ayrılacak öğe sayısı.|
|*Max*|Serbest listede depolanacak en fazla öğe sayısını temsil eden maksimum sınıf. Maksimum sınıf [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), [max_fixed_size](../standard-library/max-fixed-size-class.md), veya [max_variable_size](../standard-library/max-variable-size-class.md)olabilir.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf şablonu Max geçti max sınıfı tarafından belirlenen listenin maksimum uzunluğu ile boyutu *Sz* bellek blokları bir listesini *yönetir.*

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Freelist](#freelist)|Türünde `freelist`bir nesne oluşturuyor.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Pop](#pop)|İlk bellek bloğunu boş listeden kaldırır.|
|[Itme](#push)|Listeye bir bellek bloğu ekler.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<tahsisörler>

**Ad alanı:** stdext

## <a name="freelistfreelist"></a><a name="freelist"></a>freelist::freelist

Türünde `freelist`bir nesne oluşturuyor.

```cpp
freelist();
```

### <a name="remarks"></a>Açıklamalar

## <a name="freelistpop"></a><a name="pop"></a>freelist::pop

İlk bellek bloğunu boş listeden kaldırır.

```cpp
void *pop();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçiyi listeden kaldırılan bellek bloğuna döndürür.

### <a name="remarks"></a>Açıklamalar

Liste boşsa üye işlev NULL döndürür. Aksi takdirde, ilk bellek bloğunu listeden kaldırır.

## <a name="freelistpush"></a><a name="push"></a>freelist::push

Listeye bir bellek bloğu ekler.

```cpp
bool push(void* ptr);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Ptr*|Boş listeye eklenecek bellek bloğuna işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

**true** max sınıfının `full` işlevi **yanlış**dönerse doğru ; aksi takdirde, `push` işlev **yanlış**döndürür.

### <a name="remarks"></a>Açıklamalar

Max `full` sınıfının işlevi **yanlış**dönerse, bu üye işlev listenin başına *ptr* tarafından işaret edilen bellek bloğunu ekler.

## <a name="see-also"></a>Ayrıca bkz.

[\<tahsisat>](../standard-library/allocators-header.md)
