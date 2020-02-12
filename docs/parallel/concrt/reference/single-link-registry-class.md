---
title: single_link_registry Sınıfı
ms.date: 11/04/2016
f1_keywords:
- single_link_registry
- AGENTS/concurrency::single_link_registry
- AGENTS/concurrency::single_link_registry::single_link_registry
- AGENTS/concurrency::single_link_registry::add
- AGENTS/concurrency::single_link_registry::begin
- AGENTS/concurrency::single_link_registry::contains
- AGENTS/concurrency::single_link_registry::count
- AGENTS/concurrency::single_link_registry::remove
helpviewer_keywords:
- single_link_registry class
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
ms.openlocfilehash: c29caf6d31df316e80b15fe6827c81e34ece8a18
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142716"
---
# <a name="single_link_registry-class"></a>single_link_registry Sınıfı

`single_link_registry` nesnesi yalnızca tek bir kaynak veya hedef bloğu yöneten bir `network_link_registry`.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```

### <a name="parameters"></a>Parametreler

*_Block*<br/>
`single_link_registry` nesnesinde depolanmakta olan blok veri türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[single_link_registry](#ctor)|`single_link_registry` nesnesi oluşturur.|
|[~ single_link_registry yok edici](#dtor)|`single_link_registry` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[add](#add)|`single_link_registry` nesnesine bir bağlantı ekler. (Network_link_registry geçersiz kılmalar [:: Add](network-link-registry-class.md#add).)|
|[başladı](#begin)|`single_link_registry` nesnesindeki ilk öğeye bir yineleyici döndürür. (Geçersiz kılmalar [network_link_registry:: Begin](network-link-registry-class.md#begin).)|
|[vardır](#contains)|`single_link_registry` nesnesini belirtilen bir blok için arar. (Network_link_registry geçersiz kılmalar [:: Contains](network-link-registry-class.md#contains).)|
|[count](#count)|`single_link_registry` nesnesindeki öğelerin sayısını sayar. (Geçersiz kılmalar [network_link_registry:: Count](network-link-registry-class.md#count).)|
|[remove](#remove)|`single_link_registry` nesnesinden bir bağlantıyı kaldırır. (Geçersiz kılmalar [network_link_registry:: Remove](network-link-registry-class.md#remove).)|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[network_link_registry](network-link-registry-class.md)

`single_link_registry`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="add"></a>ekleyemiyorum

`single_link_registry` nesnesine bir bağlantı ekler.

```cpp
virtual void add(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Eklenecek bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu kayıt defterinde zaten bir bağlantı varsa Yöntem [invalid_link_target](invalid-link-target-class.md) bir özel durum oluşturur.

## <a name="begin"></a>başladı

`single_link_registry` nesnesindeki ilk öğeye bir yineleyici döndürür.

```cpp
virtual iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

`single_link_registry` nesnesindeki ilk öğeyi adresleyen bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bitiş durumu bir `NULL` bağlantısıyla belirtilir.

## <a name="contains"></a>vardır

`single_link_registry` nesnesini belirtilen bir blok için arar.

```cpp
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
`single_link_registry` nesnesinde aranacak bir blok işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

bağlantı bulunursa **true** , aksi durumda **false** .

## <a name="count"></a>biriktirme

`single_link_registry` nesnesindeki öğelerin sayısını sayar.

```cpp
virtual size_t count();
```

### <a name="return-value"></a>Dönüş Değeri

`single_link_registry` nesnesindeki öğelerin sayısı.

## <a name="remove"></a>temizlenmesine

`single_link_registry` nesnesinden bir bağlantıyı kaldırır.

```cpp
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Bulunursa, kaldırılacak bloğa yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

bağlantı bulunursa ve kaldırılırsa **doğru** , aksi takdirde **yanlış** olur.

## <a name="ctor"></a>single_link_registry

`single_link_registry` nesnesi oluşturur.

```cpp
single_link_registry();
```

## <a name="dtor"></a>~ single_link_registry

`single_link_registry` nesnesini yok eder.

```cpp
virtual ~single_link_registry();
```

### <a name="remarks"></a>Açıklamalar

Yöntemi, bağlantı kaldırılmadan önce çağrılırsa bir [invalid_operation](invalid-operation-class.md) özel durumu oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[multi_link_registry Sınıfı](multi-link-registry-class.md)
