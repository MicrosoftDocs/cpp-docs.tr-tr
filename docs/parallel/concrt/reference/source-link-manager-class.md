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
ms.openlocfilehash: d4979eaf9065183be646be72cfdd5a94500edf55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337589"
---
# <a name="sourcelinkmanager-class"></a>source_link_manager Sınıfı

`source_link_manager` Nesnesi ileti bloğu ağ bağlantıları yönetir `ISource` engeller.

## <a name="syntax"></a>Sözdizimi

```
template<class _LinkRegistry>
class source_link_manager;
```

#### <a name="parameters"></a>Parametreler

*_LinkRegistry*<br/>
Ağ bağlantısı kayıt defteri.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`const_pointer`|Bir işaretçi sağlayan bir tür bir `const` öğesinde bir `source_link_manager` nesne.|
|`const_reference`|Bir başvuru sağlayan bir tür bir `const` öğesi içinde depolanan bir `source_link_manager` okumak ve const işlemleri gerçekleştirmek için nesne.|
|`iterator`|Bir yineleyici sağlayan bir tür okuyabilen veya değiştirebilen herhangi bir öğenin `source_link_manager` nesne.|
|`type`|Tarafından yönetilen bağlantı kayıt defteri türü `source_link_manager` nesne.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[source_link_manager](#ctor)|Oluşturur bir `source_link_manager` nesne.|
|[~ source_link_manager yok Edicisi](#dtor)|Yok eder `source_link_manager` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[add](#add)|Kaynak bağlantısını ekler `source_link_manager` nesne.|
|[başlayın](#begin)|İçindeki ilk öğeye bir yineleyici döndüren `source_link_manager` nesne.|
|[içerir](#contains)|Aramalar `network_link_registry` bu `source_link_manager` belirtilen bloğu için nesne.|
|[Sayısı](#count)|Bağlantılı bloklarında sayar `source_link_manager` nesne.|
|[Başvuru](#reference)|Bir başvuru alır `source_link_manager` nesne.|
|[register_target_block](#register_target_block)|Bu tutan hedef blok kaydeder `source_link_manager` nesne.|
|[Yayın](#release)|Başvuru üzerinde sürümleri `source_link_manager` nesne.|
|[remove](#remove)|Bir bağlantıdan kaldırır `source_link_manager` nesne.|
|[set_bound](#set_bound)|İçin eklenen kaynak bağlantı sayısının üst sınırını ayarlar `source_link_manager` nesne.|

## <a name="remarks"></a>Açıklamalar

Şu anda kaynak başvuru sayılan taşlarıdır. Bu bir sarmalayıcı olan bir `network_link_registry` nesnesini eş zamanlı erişim bağlantılara ve başvuru bağlantıları geri çağırmalarla olanağı sağlar. İleti blokları ( `target_block`s veya `propagator_block`s) Bu sınıf için bunların kaynak bağlantılarını kullanmalıdır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`source_link_manager`

## <a name="requirements"></a>Gereksinimler

**Başlık:** agents.h

**Namespace:** eşzamanlılık

##  <a name="add"></a> Ekleme

Kaynak bağlantısını ekler `source_link_manager` nesne.

```
void add(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Bağla*<br/>
Eklenecek bir blok için işaretçi.

##  <a name="begin"></a> başlayın

İçindeki ilk öğeye bir yineleyici döndüren `source_link_manager` nesne.

```
iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

İçindeki ilk öğeyi ele alan bir yineleyici `source_link_manager` nesne.

### <a name="remarks"></a>Açıklamalar

Bitiş durumuna yineleyici tarafından belirtilen bir `NULL` bağlantı.

##  <a name="contains"></a> içerir

Aramalar `network_link_registry` bu `source_link_manager` belirtilen bloğu için nesne.

```
bool contains(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Bağla*<br/>
İçinde arama yapılacak olan bloğu için bir işaretçi `source_link_manager` nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** belirtilen bloğu bulunduysa **false** Aksi takdirde.

##  <a name="count"></a> Sayısı

Bağlantılı bloklarında sayar `source_link_manager` nesne.

```
size_t count();
```

### <a name="return-value"></a>Dönüş Değeri

Bağlantılı blok sayısını `source_link_manager` nesne.

##  <a name="reference"></a> Başvuru

Bir başvuru alır `source_link_manager` nesne.

```
void reference();
```

##  <a name="register_target_block"></a> register_target_block

Bu tutan hedef blok kaydeder `source_link_manager` nesne.

```
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```

### <a name="parameters"></a>Parametreler

*_PTarget*<br/>
Bu bulunduran hedef blok `source_link_manager` nesne.

##  <a name="release"></a> Yayın

Başvuru üzerinde sürümleri `source_link_manager` nesne.

```
void release();
```

##  <a name="remove"></a> Kaldır

Bir bağlantıdan kaldırır `source_link_manager` nesne.

```
bool remove(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Bağla*<br/>
Bir blok, kaldırılacak işaretçisi bulunamadı.

### <a name="return-value"></a>Dönüş Değeri

**doğru** bağlantısı bulunan ve kaldırılmış **false** Aksi takdirde.

##  <a name="set_bound"></a> set_bound

İçin eklenen kaynak bağlantı sayısının üst sınırını ayarlar `source_link_manager` nesne.

```
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>Parametreler

*_MaxLinks*<br/>
Bağlantıların maksimum sayısı.

##  <a name="ctor"></a> source_link_manager

Oluşturur bir `source_link_manager` nesne.

```
source_link_manager();
```

##  <a name="dtor"></a> ~ source_link_manager

Yok eder `source_link_manager` nesne.

```
~source_link_manager();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[single_link_registry Sınıfı](single-link-registry-class.md)<br/>
[multi_link_registry Sınıfı](multi-link-registry-class.md)
