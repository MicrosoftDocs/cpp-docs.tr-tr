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
ms.openlocfilehash: 20032f393964c8919d2c1a49ec8545400cd9e392
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290137"
---
# <a name="singlelinkregistry-class"></a>single_link_registry Sınıfı

`single_link_registry` Nesnesi bir `network_link_registry` , yalnızca tek bir kaynak veya hedef blok yönetir.

## <a name="syntax"></a>Sözdizimi

```
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```

#### <a name="parameters"></a>Parametreler

*Girildiğinde _bloğu*<br/>
Blok veri türü içinde depolanan `single_link_registry` nesne.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[single_link_registry](#ctor)|Oluşturur bir `single_link_registry` nesne.|
|[~ single_link_registry yok Edicisi](#dtor)|Yok eder `single_link_registry` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[add](#add)|Bir bağlantı ekler `single_link_registry` nesne. (Geçersiz kılmaları [network_link_registry::add](network-link-registry-class.md#add).)|
|[başlayın](#begin)|İçindeki ilk öğeye bir yineleyici döndüren `single_link_registry` nesne. (Geçersiz kılmaları [network_link_registry::begin](network-link-registry-class.md#begin).)|
|[içerir](#contains)|Aramalar `single_link_registry` belirtilen bloğu için nesne. (Geçersiz kılmaları [network_link_registry::contains](network-link-registry-class.md#contains).)|
|[Sayısı](#count)|Öğeleri sayar `single_link_registry` nesne. (Geçersiz kılmaları [network_link_registry::count](network-link-registry-class.md#count).)|
|[remove](#remove)|Bir bağlantıdan kaldırır `single_link_registry` nesne. (Geçersiz kılmaları [network_link_registry::remove](network-link-registry-class.md#remove).)|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[network_link_registry](network-link-registry-class.md)

`single_link_registry`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="add"></a> Ekleme

Bir bağlantı ekler `single_link_registry` nesne.

```
virtual void add(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Bağla*<br/>
Eklenecek bir blok için işaretçi.

### <a name="remarks"></a>Açıklamalar

Çağırılıyorsa yöntem bir [invalid_link_target](invalid-link-target-class.md) varsa zaten bir bağlantı içinde bu kayıt defteri özel durum.

##  <a name="begin"></a> başlayın

İçindeki ilk öğeye bir yineleyici döndüren `single_link_registry` nesne.

```
virtual iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

İçindeki ilk öğeyi ele alan bir yineleyici `single_link_registry` nesne.

### <a name="remarks"></a>Açıklamalar

Son durum tarafından belirtilen bir `NULL` bağlantı.

##  <a name="contains"></a> içerir

Aramalar `single_link_registry` belirtilen bloğu için nesne.

```
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Bağla*<br/>
İçinde arama yapılacak olan bloğu için bir işaretçi `single_link_registry` nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** bağlantı bulunduysa **false** Aksi takdirde.

##  <a name="count"></a> Sayısı

Öğeleri sayar `single_link_registry` nesne.

```
virtual size_t count();
```

### <a name="return-value"></a>Dönüş Değeri

Öğe sayısını `single_link_registry` nesne.

##  <a name="remove"></a> Kaldır

Bir bağlantıdan kaldırır `single_link_registry` nesne.

```
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Bağla*<br/>
Bir blok, kaldırılacak işaretçisi bulunamadı.

### <a name="return-value"></a>Dönüş Değeri

**doğru** bağlantısı bulunan ve kaldırılmış **false** Aksi takdirde.

##  <a name="ctor"></a> single_link_registry

Oluşturur bir `single_link_registry` nesne.

```
single_link_registry();
```

##  <a name="dtor"></a> ~ single_link_registry

Yok eder `single_link_registry` nesne.

```
virtual ~single_link_registry();
```

### <a name="remarks"></a>Açıklamalar

Çağırılıyorsa yöntem bir [invalid_operation](invalid-operation-class.md) oluşturmamasıdır bağlantı kaldırılmadan önce çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[multi_link_registry Sınıfı](multi-link-registry-class.md)
