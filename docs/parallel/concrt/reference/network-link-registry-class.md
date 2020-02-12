---
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
ms.openlocfilehash: 430190c11ec06a4f26eb9d8c4237552848420ad7
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138883"
---
# <a name="network_link_registry-class"></a>network_link_registry Sınıfı

`network_link_registry` soyut temel sınıfı, kaynak ve hedef bloklar arasındaki bağlantıları yönetir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class _Block>
class network_link_registry;
```

### <a name="parameters"></a>Parametreler

*_Block*<br/>
`network_link_registry`tutulan blok veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`const_pointer`|Bir `network_link_registry` nesnesindeki `const` öğeye işaretçi sağlayan bir tür.|
|`const_reference`|Const işlemlerini okumak ve gerçekleştirmek için bir `network_link_registry` nesnesinde depolanan `const` bir öğeye başvuru sağlayan bir tür.|
|`iterator`|Bir `network_link_registry` nesnesindeki herhangi bir öğeyi okuyabilen veya değiştirebilen bir yineleyici sağlayan bir tür.|
|`type`|`network_link_registry` nesnesinde depolanan blok türünü temsil eden bir tür.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[add](#add)|Türetilmiş bir sınıfta geçersiz kılınırsa, `network_link_registry` nesnesine bir bağlantı ekler.|
|[başladı](#begin)|Türetilmiş bir sınıfta geçersiz kılınırsa, `network_link_registry` nesnesindeki ilk öğeye bir yineleyici döndürür.|
|[vardır](#contains)|Türetilmiş bir sınıfta geçersiz kılınırsa, belirtilen blok için `network_link_registry` nesnesini arar.|
|[count](#count)|Türetilmiş bir sınıfta geçersiz kılınırsa, `network_link_registry` nesnesindeki öğe sayısını döndürür.|
|[remove](#remove)|Türetilmiş bir sınıfta geçersiz kılındığında, belirtilen bloğu `network_link_registry` nesnesinden kaldırır.|

## <a name="remarks"></a>Açıklamalar

`network link registry` eşzamanlı erişim için güvenli değildir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`network_link_registry`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="add"></a>ekleyemiyorum

Türetilmiş bir sınıfta geçersiz kılınırsa, `network_link_registry` nesnesine bir bağlantı ekler.

```cpp
virtual void add(_EType _Link) = 0;
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Eklenecek bloğa yönelik bir işaretçi.

## <a name="begin"></a>başladı

Türetilmiş bir sınıfta geçersiz kılınırsa, `network_link_registry` nesnesindeki ilk öğeye bir yineleyici döndürür.

```cpp
virtual iterator begin() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

`network_link_registry` nesnesindeki ilk öğeyi adresleyen bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Yineleyicinin bitiş durumu bir `NULL` bağlantısıyla belirtilir.

## <a name="contains"></a>vardır

Türetilmiş bir sınıfta geçersiz kılınırsa, belirtilen blok için `network_link_registry` nesnesini arar.

```cpp
virtual bool contains(_EType _Link) = 0;
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
`network_link_registry` nesnesinde aranmakta olan bloğa yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

blok bulunursa **true** , aksi takdirde **false** .

## <a name="count"></a>biriktirme

Türetilmiş bir sınıfta geçersiz kılınırsa, `network_link_registry` nesnesindeki öğe sayısını döndürür.

```cpp
virtual size_t count() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

`network_link_registry` nesnesindeki öğelerin sayısı.

## <a name="remove"></a>temizlenmesine

Türetilmiş bir sınıfta geçersiz kılındığında, belirtilen bloğu `network_link_registry` nesnesinden kaldırır.

```cpp
virtual bool remove(_EType _Link) = 0;
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Bulunursa, kaldırılacak bloğa yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

bağlantı bulunursa ve kaldırılırsa **doğru** , aksi takdirde **yanlış** olur.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[single_link_registry Sınıfı](single-link-registry-class.md)<br/>
[multi_link_registry Sınıfı](multi-link-registry-class.md)
