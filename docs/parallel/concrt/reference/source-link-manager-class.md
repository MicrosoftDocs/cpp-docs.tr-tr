---
description: 'Hakkında daha fazla bilgi edinin: source_link_manager sınıfı'
title: source_link_manager Sınıfı
ms.date: 11/04/2016
f1_keywords:
- source_link_manager
- AGENTS/concurrency::source_link_manager
- AGENTS/concurrency::source_link_manager::source_link_manager
- AGENTS/concurrency::source_link_manager::add
- AGENTS/concurrency::source_link_manager::begin
- AGENTS/concurrency::source_link_manager::contains
- AGENTS/concurrency::source_link_manager::count
- AGENTS/concurrency::source_link_manager::reference
- AGENTS/concurrency::source_link_manager::register_target_block
- AGENTS/concurrency::source_link_manager::release
- AGENTS/concurrency::source_link_manager::remove
- AGENTS/concurrency::source_link_manager::set_bound
helpviewer_keywords:
- source_link_manager class
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
ms.openlocfilehash: 132dc2db07a1c9abeeb04672f97e262761764feb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188514"
---
# <a name="source_link_manager-class"></a>source_link_manager Sınıfı

`source_link_manager`Nesne, ileti bloğu ağ bağlantılarını `ISource` bloklara yönetir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class _LinkRegistry>
class source_link_manager;
```

### <a name="parameters"></a>Parametreler

*_LinkRegistry*<br/>
Ağ bağlantısı kayıt defteri.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`const_pointer`|Bir nesne içindeki bir öğeye işaretçi sağlayan bir tür **`const`** `source_link_manager` .|
|`const_reference`|**`const`** `source_link_manager` Const işlemlerini okumak ve gerçekleştirmek için bir nesnesinde depolanan öğeye başvuru sağlayan bir tür.|
|`iterator`|Nesnedeki herhangi bir öğeyi okuyabilen veya değiştirebilen bir yineleyici sağlayan bir tür `source_link_manager` .|
|`type`|Nesne tarafından yönetilmekte olan bağlantı kayıt defterinin türü `source_link_manager` .|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[source_link_manager](#ctor)|Bir `source_link_manager` nesnesi oluşturur.|
|[~ source_link_manager yok edici](#dtor)|Nesneyi yok eder `source_link_manager` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[add](#add)|Nesnesine bir kaynak bağlantısı ekler `source_link_manager` .|
|[başladı](#begin)|Nesne içindeki ilk öğeye bir yineleyici döndürür `source_link_manager` .|
|[vardır](#contains)|`network_link_registry` `source_link_manager` Belirtilen bir blok için bu nesne içinde arar.|
|[biriktirme](#count)|Nesnedeki bağlantılı blokların sayısını sayar `source_link_manager` .|
|[başvurunun](#reference)|Nesnesinde bir başvuru alır `source_link_manager` .|
|[register_target_block](#register_target_block)|Bu nesneyi tutan hedef bloğu kaydeder `source_link_manager` .|
|[Yayın](#release)|Nesnesindeki başvuruyu yayınlar `source_link_manager` .|
|[temizlenmesine](#remove)|Nesneden bir bağlantıyı kaldırır `source_link_manager` .|
|[set_bound](#set_bound)|Bu nesneye eklenebilecek en fazla kaynak bağlantısı sayısını ayarlar `source_link_manager` .|

## <a name="remarks"></a>Açıklamalar

Şu anda, kaynak bloklarında başvuru sayılır. Bu, `network_link_registry` bağlantılara eşzamanlı erişim sağlayan bir sarmalayıcıdır ve geri çağırmalar aracılığıyla bağlantılara başvuruda bulunmak için bir nesne sağlar. İleti blokları `target_block` `propagator_block` , kaynak bağlantıları için bu sınıfı kullanmalıdır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`source_link_manager`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="add"></a><a name="add"></a> ekleyemiyorum

Nesnesine bir kaynak bağlantısı ekler `source_link_manager` .

```cpp
void add(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Eklenecek bloğa yönelik bir işaretçi.

## <a name="begin"></a><a name="begin"></a> başladı

Nesne içindeki ilk öğeye bir yineleyici döndürür `source_link_manager` .

```cpp
iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki ilk öğeyi adresleyen bir yineleyici `source_link_manager` .

### <a name="remarks"></a>Açıklamalar

Yineleyicinin bitiş durumu bir bağlantı ile belirtilir `NULL` .

## <a name="contains"></a><a name="contains"></a> vardır

`network_link_registry` `source_link_manager` Belirtilen bir blok için bu nesne içinde arar.

```cpp
bool contains(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Nesnede aranacak bir blok işaretçisi `source_link_manager` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** Belirtilen blok bulunursa, **`false`** tersi durumda.

## <a name="count"></a><a name="count"></a> biriktirme

Nesnedeki bağlantılı blokların sayısını sayar `source_link_manager` .

```cpp
size_t count();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki bağlantılı blokların sayısı `source_link_manager` .

## <a name="reference"></a><a name="reference"></a> başvurunun

Nesnesinde bir başvuru alır `source_link_manager` .

```cpp
void reference();
```

## <a name="register_target_block"></a><a name="register_target_block"></a> register_target_block

Bu nesneyi tutan hedef bloğu kaydeder `source_link_manager` .

```cpp
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu nesneyi tutan hedef blok `source_link_manager` .

## <a name="release"></a><a name="release"></a> Yayın

Nesnesindeki başvuruyu yayınlar `source_link_manager` .

```cpp
void release();
```

## <a name="remove"></a><a name="remove"></a> temizlenmesine

Nesneden bir bağlantıyı kaldırır `source_link_manager` .

```cpp
bool remove(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Bulunursa, kaldırılacak bloğa yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

**`true`** bağlantı bulunursa ve kaldırılırsa, **`false`** tersi durumda.

## <a name="set_bound"></a><a name="set_bound"></a> set_bound

Bu nesneye eklenebilecek en fazla kaynak bağlantısı sayısını ayarlar `source_link_manager` .

```cpp
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>Parametreler

*_MaxLinks*<br/>
En fazla bağlantı sayısı.

## <a name="source_link_manager"></a><a name="ctor"></a> source_link_manager

Bir `source_link_manager` nesnesi oluşturur.

```cpp
source_link_manager();
```

## <a name="source_link_manager"></a><a name="dtor"></a> ~ source_link_manager

Nesneyi yok eder `source_link_manager` .

```cpp
~source_link_manager();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[single_link_registry sınıfı](single-link-registry-class.md)<br/>
[multi_link_registry sınıfı](multi-link-registry-class.md)
