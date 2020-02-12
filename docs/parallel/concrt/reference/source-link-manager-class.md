---
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
ms.openlocfilehash: 35c7cc72520cdb0675abf9c15574a49e33741d0b
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142691"
---
# <a name="source_link_manager-class"></a>source_link_manager Sınıfı

`source_link_manager` nesnesi, `ISource` bloklara yönelik ileti bloğu ağ bağlantılarını yönetir.

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
|`const_pointer`|Bir `source_link_manager` nesnesindeki `const` öğeye işaretçi sağlayan bir tür.|
|`const_reference`|Const işlemlerini okumak ve gerçekleştirmek için bir `source_link_manager` nesnesinde depolanan `const` bir öğeye başvuru sağlayan bir tür.|
|`iterator`|`source_link_manager` nesnesindeki herhangi bir öğeyi okuyabilen veya değiştirebilen bir yineleyici sağlayan bir tür.|
|`type`|`source_link_manager` nesnesi tarafından yönetilmekte olan bağlantı kayıt defterinin türü.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[source_link_manager](#ctor)|`source_link_manager` nesnesi oluşturur.|
|[~ source_link_manager yok edici](#dtor)|`source_link_manager` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[add](#add)|`source_link_manager` nesnesine bir kaynak bağlantısı ekler.|
|[başladı](#begin)|`source_link_manager` nesnesindeki ilk öğeye bir yineleyici döndürür.|
|[vardır](#contains)|Belirtilen bir blok için bu `source_link_manager` nesnesi içindeki `network_link_registry` arar.|
|[count](#count)|`source_link_manager` nesnesindeki bağlantılı blokların sayısını sayar.|
|[başvurunun](#reference)|`source_link_manager` nesnesinde bir başvuru alır.|
|[register_target_block](#register_target_block)|Bu `source_link_manager` nesnesini tutan hedef bloğu kaydeder.|
|[Yayın](#release)|`source_link_manager` nesnesindeki başvuruyu yayınlar.|
|[remove](#remove)|`source_link_manager` nesnesinden bir bağlantıyı kaldırır.|
|[set_bound](#set_bound)|Bu `source_link_manager` nesnesine eklenebilecek en fazla kaynak bağlantısı sayısını ayarlar.|

## <a name="remarks"></a>Açıklamalar

Şu anda, kaynak bloklarında başvuru sayılır. Bu, bağlantılara eşzamanlı erişime izin veren `network_link_registry` nesnesi üzerinde bir sarmalayıcıdır ve geri çağırmalar aracılığıyla bağlantılara başvuru yapabilme olanağı sağlar. İleti blokları (`target_block`s veya `propagator_block`s), kaynak bağlantıları için bu sınıfı kullanmalıdır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`source_link_manager`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="add"></a>ekleyemiyorum

`source_link_manager` nesnesine bir kaynak bağlantısı ekler.

```cpp
void add(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Eklenecek bloğa yönelik bir işaretçi.

## <a name="begin"></a>başladı

`source_link_manager` nesnesindeki ilk öğeye bir yineleyici döndürür.

```cpp
iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

`source_link_manager` nesnesindeki ilk öğeyi adresleyen bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Yineleyicinin bitiş durumu bir `NULL` bağlantısıyla belirtilir.

## <a name="contains"></a>vardır

Belirtilen bir blok için bu `source_link_manager` nesnesi içindeki `network_link_registry` arar.

```cpp
bool contains(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
`source_link_manager` nesnesinde aranacak bir blok işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen blok bulunursa **true** , aksi durumda **false** .

## <a name="count"></a>biriktirme

`source_link_manager` nesnesindeki bağlantılı blokların sayısını sayar.

```cpp
size_t count();
```

### <a name="return-value"></a>Dönüş Değeri

`source_link_manager` nesnesindeki bağlantılı blokların sayısı.

## <a name="reference"></a>başvurunun

`source_link_manager` nesnesinde bir başvuru alır.

```cpp
void reference();
```

## <a name="register_target_block"></a>register_target_block

Bu `source_link_manager` nesnesini tutan hedef bloğu kaydeder.

```cpp
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu `source_link_manager` nesnesini tutan hedef blok.

## <a name="release"></a>Yayın

`source_link_manager` nesnesindeki başvuruyu yayınlar.

```cpp
void release();
```

## <a name="remove"></a>temizlenmesine

`source_link_manager` nesnesinden bir bağlantıyı kaldırır.

```cpp
bool remove(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Bulunursa, kaldırılacak bloğa yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

bağlantı bulunursa ve kaldırılırsa **doğru** , aksi takdirde **yanlış** olur.

## <a name="set_bound"></a>set_bound

Bu `source_link_manager` nesnesine eklenebilecek en fazla kaynak bağlantısı sayısını ayarlar.

```cpp
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>Parametreler

*_MaxLinks*<br/>
En fazla bağlantı sayısı.

## <a name="ctor"></a>source_link_manager

`source_link_manager` nesnesi oluşturur.

```cpp
source_link_manager();
```

## <a name="dtor"></a>~ source_link_manager

`source_link_manager` nesnesini yok eder.

```cpp
~source_link_manager();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[single_link_registry Sınıfı](single-link-registry-class.md)<br/>
[multi_link_registry Sınıfı](multi-link-registry-class.md)
