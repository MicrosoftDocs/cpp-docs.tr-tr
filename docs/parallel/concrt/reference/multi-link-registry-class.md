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
ms.openlocfilehash: 777b3f5206b4a595b5dcac653d608255e92f4ef6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231708"
---
# <a name="multi_link_registry-class"></a>multi_link_registry Sınıfı

`multi_link_registry`Nesnesi, `network_link_registry` birden çok kaynak bloğunu veya birden çok hedef bloğu yöneten bir nesnesidir.

## <a name="syntax"></a>Söz dizimi

```cpp
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```

### <a name="parameters"></a>Parametreler

*_Block*<br/>
Nesnede depolanmakta olan blok veri türü `multi_link_registry` .

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[multi_link_registry](#ctor)|Bir `multi_link_registry` nesnesi oluşturur.|
|[~ multi_link_registry yok edici](#dtor)|Nesneyi yok eder `multi_link_registry` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[add](#add)|Nesnesine bir bağlantı ekler `multi_link_registry` . (Network_link_registry geçersiz kılmalar [:: Add](network-link-registry-class.md#add).)|
|[başladı](#begin)|Nesne içindeki ilk öğeye bir yineleyici döndürür `multi_link_registry` . (Geçersiz kılmalar [network_link_registry:: Begin](network-link-registry-class.md#begin).)|
|[vardır](#contains)|`multi_link_registry`Nesneyi belirtilen bir blok için arar. (Network_link_registry geçersiz kılmalar [:: Contains](network-link-registry-class.md#contains).)|
|[biriktirme](#count)|Nesnedeki öğelerin sayısını sayar `multi_link_registry` . (Geçersiz kılmalar [network_link_registry:: Count](network-link-registry-class.md#count).)|
|[temizlenmesine](#remove)|Nesneden bir bağlantıyı kaldırır `multi_link_registry` . (Geçersiz kılmalar [network_link_registry:: Remove](network-link-registry-class.md#remove).)|
|[set_bound](#set_bound)|Nesnenin tutadığı bağlantı sayısında bir üst sınır ayarlar `multi_link_registry` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[network_link_registry](network-link-registry-class.md)

`multi_link_registry`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="add"></a><a name="add"></a>ekleyemiyorum

Nesnesine bir bağlantı ekler `multi_link_registry` .

```cpp
virtual void add(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Eklenecek bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bağlantı kayıt defterinde zaten [invalid_link_target](invalid-link-target-class.md) varsa veya bir `set_bound` bağlantı zaten işlevle ayarlandıysa ve bu yana bir bağlantı varsa, yöntem invalid_link_target bir özel durum oluşturur.

## <a name="begin"></a><a name="begin"></a>başladı

Nesne içindeki ilk öğeye bir yineleyici döndürür `multi_link_registry` .

```cpp
virtual iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki ilk öğeyi adresleyen bir yineleyici `multi_link_registry` .

### <a name="remarks"></a>Açıklamalar

Bitiş durumu bir bağlantı ile belirtilir `NULL` .

## <a name="contains"></a><a name="contains"></a>vardır

`multi_link_registry`Nesneyi belirtilen bir blok için arar.

```cpp
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Nesnede aranacak bir blok işaretçisi `multi_link_registry` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** Belirtilen blok bulunursa, **`false`** tersi durumda.

## <a name="count"></a><a name="count"></a>biriktirme

Nesnedeki öğelerin sayısını sayar `multi_link_registry` .

```cpp
virtual size_t count();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki öğelerin sayısı `multi_link_registry` .

## <a name="multi_link_registry"></a><a name="ctor"></a>multi_link_registry

Bir `multi_link_registry` nesnesi oluşturur.

```cpp
multi_link_registry();
```

## <a name="multi_link_registry"></a><a name="dtor"></a>~ multi_link_registry

Nesneyi yok eder `multi_link_registry` .

```cpp
virtual ~multi_link_registry();
```

### <a name="remarks"></a>Açıklamalar

Yöntemi, tüm bağlantılar kaldırılmadan önce çağrılırsa bir [invalid_operation](invalid-operation-class.md) özel durumu oluşturur.

## <a name="remove"></a><a name="remove"></a>temizlenmesine

Nesneden bir bağlantıyı kaldırır `multi_link_registry` .

```cpp
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Bulunursa, kaldırılacak bloğa yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** bağlantı bulunursa ve kaldırılırsa, **`false`** tersi durumda.

## <a name="set_bound"></a><a name="set_bound"></a>set_bound

Nesnenin tutadığı bağlantı sayısında bir üst sınır ayarlar `multi_link_registry` .

```cpp
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>Parametreler

*_MaxLinks*<br/>
Nesnenin tutadığı en fazla bağlantı sayısı `multi_link_registry` .

### <a name="remarks"></a>Açıklamalar

Bir bağlantı kurulduktan sonra, bir girdinin bağlantısını kesmek `multi_link_registry` nesnenin daha fazla çağrının `add` bir özel durum oluşturması için sabit bir durum girmesine neden olur `invalid_link_target` .

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[single_link_registry sınıfı](single-link-registry-class.md)
