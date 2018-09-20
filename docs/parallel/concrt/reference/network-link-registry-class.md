---
title: network_link_registry sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- network_link_registry
- AGENTS/concurrency::network_link_registry
- AGENTS/concurrency::network_link_registry::add
- AGENTS/concurrency::network_link_registry::begin
- AGENTS/concurrency::network_link_registry::contains
- AGENTS/concurrency::network_link_registry::count
- AGENTS/concurrency::network_link_registry::remove
dev_langs:
- C++
helpviewer_keywords:
- network_link_registry class
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2798c4abe33e49d2ac6199ad6f9a1013805fde7b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424423"
---
# <a name="networklinkregistry-class"></a>network_link_registry Sınıfı

`network_link_registry` Soyut temel sınıf kaynak ve hedef bloklar arasındaki bağlantıları yönetir.

## <a name="syntax"></a>Sözdizimi

```
template<class _Block>
class network_link_registry;
```

#### <a name="parameters"></a>Parametreler

*Girildiğinde _bloğu*<br/>
Blok veri türü içinde depolanan `network_link_registry`.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`const_pointer`|Bir işaretçi sağlayan bir tür bir `const` öğesinde bir `network_link_registry` nesne.|
|`const_reference`|Bir başvuru sağlayan bir tür bir `const` öğesi içinde depolanan bir `network_link_registry` okumak ve const işlemleri gerçekleştirmek için nesne.|
|`iterator`|Bir yineleyici sağlayan bir tür okuyabilen veya değiştirebilen herhangi bir öğenin bir `network_link_registry` nesne.|
|`type`|Depolanan blok türü temsil eden bir tür `network_link_registry` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[add](#add)|Türetilen bir sınıfta geçersiz kılındığında, bir bağlantı ekler `network_link_registry` nesne.|
|[başlayın](#begin)|Türetilen bir sınıfta geçersiz kılındığında, içindeki ilk öğeye bir yineleyici döndüren `network_link_registry` nesne.|
|[içerir](#contains)|Türetilen bir sınıfta geçersiz kılındığında, arar `network_link_registry` belirtilen bloğu için nesne.|
|[Sayısı](#count)|Türetilen bir sınıfta geçersiz kılındığında, öğe sayısını döndürür `network_link_registry` nesne.|
|[remove](#remove)|Türetilen bir sınıfta geçersiz kılındığında, belirtilen bloğundan kaldırır `network_link_registry` nesne.|

## <a name="remarks"></a>Açıklamalar

`network link registry` Eş zamanlı erişim için güvenli değildir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`network_link_registry`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="add"></a> Ekleme

Türetilen bir sınıfta geçersiz kılındığında, bir bağlantı ekler `network_link_registry` nesne.

```
virtual void add(_EType _Link) = 0;
```

### <a name="parameters"></a>Parametreler

*_Bağla*<br/>
Eklenecek bir blok için işaretçi.

##  <a name="begin"></a> başlayın

Türetilen bir sınıfta geçersiz kılındığında, içindeki ilk öğeye bir yineleyici döndüren `network_link_registry` nesne.

```
virtual iterator begin() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

İçindeki ilk öğeyi ele alan bir yineleyici `network_link_registry` nesne.

### <a name="remarks"></a>Açıklamalar

Bitiş durumuna yineleyici tarafından belirtilen bir `NULL` bağlantı.

##  <a name="contains"></a> içerir

Türetilen bir sınıfta geçersiz kılındığında, arar `network_link_registry` belirtilen bloğu için nesne.

```
virtual bool contains(_EType _Link) = 0;
```

### <a name="parameters"></a>Parametreler

*_Bağla*<br/>
Bir işaretçi için de Aranmakta olan bir blok `network_link_registry` nesne.

### <a name="return-value"></a>Dönüş Değeri

`true` bloğu bulunduysa `false` Aksi takdirde.

##  <a name="count"></a> Sayısı

Türetilen bir sınıfta geçersiz kılındığında, öğe sayısını döndürür `network_link_registry` nesne.

```
virtual size_t count() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe sayısını `network_link_registry` nesne.

##  <a name="remove"></a> Kaldır

Türetilen bir sınıfta geçersiz kılındığında, belirtilen bloğundan kaldırır `network_link_registry` nesne.

```
virtual bool remove(_EType _Link) = 0;
```

### <a name="parameters"></a>Parametreler

*_Bağla*<br/>
Bir blok, kaldırılacak işaretçisi bulunamadı.

### <a name="return-value"></a>Dönüş Değeri

`true` bağlantıyı bulunan ve kaldırılmış `false` Aksi takdirde.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[single_link_registry Sınıfı](single-link-registry-class.md)<br/>
[multi_link_registry Sınıfı](multi-link-registry-class.md)
