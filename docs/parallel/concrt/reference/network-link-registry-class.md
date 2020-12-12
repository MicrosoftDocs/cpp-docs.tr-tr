---
description: 'Hakkında daha fazla bilgi edinin: network_link_registry sınıfı'
title: network_link_registry Sınıfı
ms.date: 11/04/2016
f1_keywords:
- network_link_registry
- AGENTS/concurrency::network_link_registry
- AGENTS/concurrency::network_link_registry::add
- AGENTS/concurrency::network_link_registry::begin
- AGENTS/concurrency::network_link_registry::contains
- AGENTS/concurrency::network_link_registry::count
- AGENTS/concurrency::network_link_registry::remove
helpviewer_keywords:
- network_link_registry class
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
ms.openlocfilehash: d14ec5758b399d46d5a5f04200b9422b030305f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236600"
---
# <a name="network_link_registry-class"></a>network_link_registry Sınıfı

`network_link_registry`Soyut temel sınıf, kaynak ve hedef bloklar arasındaki bağlantıları yönetir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class _Block>
class network_link_registry;
```

### <a name="parameters"></a>Parametreler

*_Block*<br/>
İçinde depolanmakta olan blok veri türü `network_link_registry` .

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`const_pointer`|Bir nesne içindeki bir öğeye işaretçi sağlayan bir tür **`const`** `network_link_registry` .|
|`const_reference`|**`const`** `network_link_registry` Const işlemlerini okumak ve gerçekleştirmek için bir nesnesinde depolanan öğeye başvuru sağlayan bir tür.|
|`iterator`|Bir nesne içindeki herhangi bir öğeyi okuyabilen veya değiştirebilen bir yineleyici sağlayan bir tür `network_link_registry` .|
|`type`|Nesnesinde depolanan blok türünü temsil eden bir tür `network_link_registry` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[add](#add)|Türetilmiş bir sınıfta geçersiz kılınırsa, nesnesine bir bağlantı ekler `network_link_registry` .|
|[başladı](#begin)|Türetilmiş bir sınıfta geçersiz kılınırsa, nesne içindeki ilk öğeye bir yineleyici döndürür `network_link_registry` .|
|[vardır](#contains)|Türetilmiş bir sınıfta geçersiz kılınırsa, `network_link_registry` nesneyi belirtilen bir blok için arar.|
|[biriktirme](#count)|Türetilmiş bir sınıfta geçersiz kılınırsa, nesne içindeki öğe sayısını döndürür `network_link_registry` .|
|[temizlenmesine](#remove)|Türetilmiş bir sınıfta geçersiz kılındığında, belirtilen bloğu `network_link_registry` nesnesinden kaldırır.|

## <a name="remarks"></a>Açıklamalar

, `network link registry` Eşzamanlı erişim için güvenli değildir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`network_link_registry`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="add"></a><a name="add"></a> ekleyemiyorum

Türetilmiş bir sınıfta geçersiz kılınırsa, nesnesine bir bağlantı ekler `network_link_registry` .

```cpp
virtual void add(_EType _Link) = 0;
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Eklenecek bloğa yönelik bir işaretçi.

## <a name="begin"></a><a name="begin"></a> başladı

Türetilmiş bir sınıfta geçersiz kılınırsa, nesne içindeki ilk öğeye bir yineleyici döndürür `network_link_registry` .

```cpp
virtual iterator begin() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki ilk öğeyi adresleyen bir yineleyici `network_link_registry` .

### <a name="remarks"></a>Açıklamalar

Yineleyicinin bitiş durumu bir bağlantı ile belirtilir `NULL` .

## <a name="contains"></a><a name="contains"></a> vardır

Türetilmiş bir sınıfta geçersiz kılınırsa, `network_link_registry` nesneyi belirtilen bir blok için arar.

```cpp
virtual bool contains(_EType _Link) = 0;
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Nesnede aranmakta olan bloğa yönelik bir işaretçi `network_link_registry` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** blok bulunursa, **`false`** tersi durumda.

## <a name="count"></a><a name="count"></a> biriktirme

Türetilmiş bir sınıfta geçersiz kılınırsa, nesne içindeki öğe sayısını döndürür `network_link_registry` .

```cpp
virtual size_t count() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki öğelerin sayısı `network_link_registry` .

## <a name="remove"></a><a name="remove"></a> temizlenmesine

Türetilmiş bir sınıfta geçersiz kılındığında, belirtilen bloğu `network_link_registry` nesnesinden kaldırır.

```cpp
virtual bool remove(_EType _Link) = 0;
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Bulunursa, kaldırılacak bloğa yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** bağlantı bulunursa ve kaldırılırsa, **`false`** tersi durumda.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[single_link_registry sınıfı](single-link-registry-class.md)<br/>
[multi_link_registry sınıfı](multi-link-registry-class.md)
