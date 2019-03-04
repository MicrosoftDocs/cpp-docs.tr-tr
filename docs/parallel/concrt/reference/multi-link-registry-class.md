---
title: multi_link_registry Sınıfı
ms.date: 11/04/2016
f1_keywords:
- multi_link_registry
- AGENTS/concurrency::multi_link_registry
- AGENTS/concurrency::multi_link_registry::multi_link_registry
- AGENTS/concurrency::multi_link_registry::add
- AGENTS/concurrency::multi_link_registry::begin
- AGENTS/concurrency::multi_link_registry::contains
- AGENTS/concurrency::multi_link_registry::count
- AGENTS/concurrency::multi_link_registry::remove
- AGENTS/concurrency::multi_link_registry::set_bound
helpviewer_keywords:
- multi_link_registry class
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
ms.openlocfilehash: 388cc0082f69041368d1a444179855451d552ce6
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264773"
---
# <a name="multilinkregistry-class"></a>multi_link_registry Sınıfı

`multi_link_registry` Nesnesi bir `network_link_registry` birden çok kaynak bloklar veya birden çok hedef bloğa yönetir.

## <a name="syntax"></a>Sözdizimi

```
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```

#### <a name="parameters"></a>Parametreler

*Girildiğinde _bloğu*<br/>
Blok veri türü içinde depolanan `multi_link_registry` nesne.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[multi_link_registry](#ctor)|Oluşturur bir `multi_link_registry` nesne.|
|[~ multi_link_registry yok Edicisi](#dtor)|Yok eder `multi_link_registry` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[add](#add)|Bir bağlantı ekler `multi_link_registry` nesne. (Geçersiz kılmaları [network_link_registry::add](network-link-registry-class.md#add).)|
|[başlayın](#begin)|İçindeki ilk öğeye bir yineleyici döndüren `multi_link_registry` nesne. (Geçersiz kılmaları [network_link_registry::begin](network-link-registry-class.md#begin).)|
|[içerir](#contains)|Aramalar `multi_link_registry` belirtilen bloğu için nesne. (Geçersiz kılmaları [network_link_registry::contains](network-link-registry-class.md#contains).)|
|[Sayısı](#count)|Öğeleri sayar `multi_link_registry` nesne. (Geçersiz kılmaları [network_link_registry::count](network-link-registry-class.md#count).)|
|[remove](#remove)|Bir bağlantıdan kaldırır `multi_link_registry` nesne. (Geçersiz kılmaları [network_link_registry::remove](network-link-registry-class.md#remove).)|
|[set_bound](#set_bound)|Bağlantı sayısı üzerinde bir üst sınır ayarlar `multi_link_registry` nesne tutabilir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[network_link_registry](network-link-registry-class.md)

`multi_link_registry`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="add"></a> Ekleme

Bir bağlantı ekler `multi_link_registry` nesne.

```
virtual void add(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Bağla*<br/>
Eklenecek bir blok için işaretçi.

### <a name="remarks"></a>Açıklamalar

Çağırılıyorsa yöntem bir [invalid_link_target](invalid-link-target-class.md) özel durum bağlantıyı kayıt defterinde zaten varsa veya bir sınır varsa zaten ayarlanmış ile `set_bound` işlevi ve bir bağlantı kaldırılmışsa.

##  <a name="begin"></a> başlayın

İçindeki ilk öğeye bir yineleyici döndüren `multi_link_registry` nesne.

```
virtual iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

İçindeki ilk öğeyi ele alan bir yineleyici `multi_link_registry` nesne.

### <a name="remarks"></a>Açıklamalar

Son durum tarafından belirtilen bir `NULL` bağlantı.

##  <a name="contains"></a> içerir

Aramalar `multi_link_registry` belirtilen bloğu için nesne.

```
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Bağla*<br/>
İçinde arama yapılacak olan bloğu için bir işaretçi `multi_link_registry` nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** belirtilen bloğu bulunduysa **false** Aksi takdirde.

##  <a name="count"></a> Sayısı

Öğeleri sayar `multi_link_registry` nesne.

```
virtual size_t count();
```

### <a name="return-value"></a>Dönüş Değeri

Öğe sayısını `multi_link_registry` nesne.

##  <a name="ctor"></a> multi_link_registry

Oluşturur bir `multi_link_registry` nesne.

```
multi_link_registry();
```

##  <a name="dtor"></a> ~ multi_link_registry

Yok eder `multi_link_registry` nesne.

```
virtual ~multi_link_registry();
```

### <a name="remarks"></a>Açıklamalar

Çağırılıyorsa yöntem bir [invalid_operation](invalid-operation-class.md) tüm bağlantıları kaldırılmadan önce çağrılırsa bir özel durum.

##  <a name="remove"></a> Kaldır

Bir bağlantıdan kaldırır `multi_link_registry` nesne.

```
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Bağla*<br/>
Bir blok, kaldırılacak işaretçisi bulunamadı.

### <a name="return-value"></a>Dönüş Değeri

**doğru** bağlantısı bulunan ve kaldırılmış **false** Aksi takdirde.

##  <a name="set_bound"></a> set_bound

Bağlantı sayısı üzerinde bir üst sınır ayarlar `multi_link_registry` nesne tutabilir.

```
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>Parametreler

*_MaxLinks*<br/>
En fazla bağlantılar `multi_link_registry` nesne tutabilir.

### <a name="remarks"></a>Açıklamalar

Bağımlı ayarlandıktan sonra bir giriş bağlantısını neden olacak `multi_link_registry` nesne değişmez bir duruma girmesini çağrıları burada daha fazla `add` oluşturmaz bir `invalid_link_target` özel durum.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[single_link_registry Sınıfı](single-link-registry-class.md)
