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
ms.openlocfilehash: ef1f2e617e93869a1084dc030c6496c819f1ed96
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652718"
---
# <a name="freelist-class"></a>freelist Sınıfı

Bellek bloklarını listesini yönetir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <std::size_t Sz, class Max>
class freelist : public Max
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*SZ*|Ayrılacak dizideki öğelerin sayısı.|
|*en fazla*|Öğeleri boş listeden depolanacak en fazla sayısını temsil eden en fazla sınıf. Max sınıfı olabilir [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), [max_fixed_size](../standard-library/max-fixed-size-class.md), veya [max_variable_size](../standard-library/max-variable-size-class.md).|

## <a name="remarks"></a>Açıklamalar

Bu şablon sınıfının bellek blok boyutu listesini yönetir *Sz* geçirilen max sınıfı tarafından belirlenen listenin maksimum uzunluğunu ile *Max*.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[FreeList](#freelist)|Türünde bir nesne oluşturur `freelist`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[POP](#pop)|İlk bellek bloğu boş listeden kaldırır.|
|[push](#push)|Bir bellek bloğunu listesine ekler.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<ayırıcılar >

**Namespace:** stdext

## <a name="freelist"></a>  FreeList::FreeList

Türünde bir nesne oluşturur `freelist`.

```cpp
freelist();
```

### <a name="remarks"></a>Açıklamalar

## <a name="pop"></a>  FreeList::POP

İlk bellek bloğu boş listeden kaldırır.

```cpp
void *pop();
```

### <a name="return-value"></a>Dönüş Değeri

Listeden kaldırılan bellek bloğu için bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Liste boşsa, üye işlev NULL döndürür. Aksi takdirde, ilk bellek bloğu listeden kaldırır.

## <a name="push"></a>  FreeList::push

Bir bellek bloğunu listesine ekler.

```cpp
bool push(void* ptr);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ptr*|Ücretsiz listeye eklenecek bellek bloğu için bir işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `full` max sınıfının işlevi döndürür **false**; Aksi takdirde `push` işlevinin döndürdükleriyle **false**.

### <a name="remarks"></a>Açıklamalar

Varsa `full` max sınıfının işlevi döndürür **false**, bu üye işlevi tarafından işaret edilen bellek bloğu ekler *ptr* listesinin karşılaştırması.

## <a name="see-also"></a>Ayrıca bkz.

[\<Ayırıcılar >](../standard-library/allocators-header.md)<br/>
