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
ms.openlocfilehash: 24f89a6b2fb998ba5e5a82dbb470accb45d0fd9f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219553"
---
# <a name="single_link_registry-class"></a>single_link_registry Sınıfı

`single_link_registry`Nesnesi `network_link_registry` yalnızca tek bir kaynağı veya hedef bloğu yöneten bir nesnesidir.

## <a name="syntax"></a>Söz dizimi

```cpp
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```

### <a name="parameters"></a>Parametreler

*_Block*<br/>
Nesnede depolanmakta olan blok veri türü `single_link_registry` .

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[single_link_registry](#ctor)|Bir `single_link_registry` nesnesi oluşturur.|
|[~ single_link_registry yok edici](#dtor)|Nesneyi yok eder `single_link_registry` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[add](#add)|Nesnesine bir bağlantı ekler `single_link_registry` . (Network_link_registry geçersiz kılmalar [:: Add](network-link-registry-class.md#add).)|
|[başladı](#begin)|Nesne içindeki ilk öğeye bir yineleyici döndürür `single_link_registry` . (Geçersiz kılmalar [network_link_registry:: Begin](network-link-registry-class.md#begin).)|
|[vardır](#contains)|`single_link_registry`Nesneyi belirtilen bir blok için arar. (Network_link_registry geçersiz kılmalar [:: Contains](network-link-registry-class.md#contains).)|
|[biriktirme](#count)|Nesnedeki öğelerin sayısını sayar `single_link_registry` . (Geçersiz kılmalar [network_link_registry:: Count](network-link-registry-class.md#count).)|
|[temizlenmesine](#remove)|Nesneden bir bağlantıyı kaldırır `single_link_registry` . (Geçersiz kılmalar [network_link_registry:: Remove](network-link-registry-class.md#remove).)|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[network_link_registry](network-link-registry-class.md)

`single_link_registry`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="add"></a><a name="add"></a>ekleyemiyorum

Nesnesine bir bağlantı ekler `single_link_registry` .

```cpp
virtual void add(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Eklenecek bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu kayıt defterinde zaten bir bağlantı varsa Yöntem [invalid_link_target](invalid-link-target-class.md) bir özel durum oluşturur.

## <a name="begin"></a><a name="begin"></a>başladı

Nesne içindeki ilk öğeye bir yineleyici döndürür `single_link_registry` .

```cpp
virtual iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki ilk öğeyi adresleyen bir yineleyici `single_link_registry` .

### <a name="remarks"></a>Açıklamalar

Bitiş durumu bir bağlantı ile belirtilir `NULL` .

## <a name="contains"></a><a name="contains"></a>vardır

`single_link_registry`Nesneyi belirtilen bir blok için arar.

```cpp
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Nesnede aranacak bir blok işaretçisi `single_link_registry` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** bağlantı bulunursa, **`false`** tersi durumda.

## <a name="count"></a><a name="count"></a>biriktirme

Nesnedeki öğelerin sayısını sayar `single_link_registry` .

```cpp
virtual size_t count();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki öğelerin sayısı `single_link_registry` .

## <a name="remove"></a><a name="remove"></a>temizlenmesine

Nesneden bir bağlantıyı kaldırır `single_link_registry` .

```cpp
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Bulunursa, kaldırılacak bloğa yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** bağlantı bulunursa ve kaldırılırsa, **`false`** tersi durumda.

## <a name="single_link_registry"></a><a name="ctor"></a>single_link_registry

Bir `single_link_registry` nesnesi oluşturur.

```cpp
single_link_registry();
```

## <a name="single_link_registry"></a><a name="dtor"></a>~ single_link_registry

Nesneyi yok eder `single_link_registry` .

```cpp
virtual ~single_link_registry();
```

### <a name="remarks"></a>Açıklamalar

Yöntemi, bağlantı kaldırılmadan önce çağrılırsa bir [invalid_operation](invalid-operation-class.md) özel durumu oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[multi_link_registry sınıfı](multi-link-registry-class.md)
