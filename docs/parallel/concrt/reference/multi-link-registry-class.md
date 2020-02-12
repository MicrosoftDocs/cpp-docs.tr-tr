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
ms.openlocfilehash: e22df5ee65d0219a46065044385dca46aac297a3
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142370"
---
# <a name="multi_link_registry-class"></a>multi_link_registry Sınıfı

`multi_link_registry` nesnesi, birden çok kaynak bloğunu veya birden çok hedef bloğu yöneten bir `network_link_registry`.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```

### <a name="parameters"></a>Parametreler

*_Block*<br/>
`multi_link_registry` nesnesinde depolanmakta olan blok veri türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[multi_link_registry](#ctor)|`multi_link_registry` nesnesi oluşturur.|
|[~ multi_link_registry yok edici](#dtor)|`multi_link_registry` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[add](#add)|`multi_link_registry` nesnesine bir bağlantı ekler. (Network_link_registry geçersiz kılmalar [:: Add](network-link-registry-class.md#add).)|
|[başladı](#begin)|`multi_link_registry` nesnesindeki ilk öğeye bir yineleyici döndürür. (Geçersiz kılmalar [network_link_registry:: Begin](network-link-registry-class.md#begin).)|
|[vardır](#contains)|`multi_link_registry` nesnesini belirtilen bir blok için arar. (Network_link_registry geçersiz kılmalar [:: Contains](network-link-registry-class.md#contains).)|
|[count](#count)|`multi_link_registry` nesnesindeki öğelerin sayısını sayar. (Geçersiz kılmalar [network_link_registry:: Count](network-link-registry-class.md#count).)|
|[remove](#remove)|`multi_link_registry` nesnesinden bir bağlantıyı kaldırır. (Geçersiz kılmalar [network_link_registry:: Remove](network-link-registry-class.md#remove).)|
|[set_bound](#set_bound)|`multi_link_registry` nesnenin tutadığı bağlantı sayısı üst sınırını ayarlar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[network_link_registry](network-link-registry-class.md)

`multi_link_registry`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="add"></a>ekleyemiyorum

`multi_link_registry` nesnesine bir bağlantı ekler.

```cpp
virtual void add(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Eklenecek bloğa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bağlantı kayıt defterinde zaten varsa veya bir bağlama zaten `set_bound` işleviyle ayarlandıysa ve bu yana bir bağlantı varsa [invalid_link_target](invalid-link-target-class.md) bir özel durum oluşturur.

## <a name="begin"></a>başladı

`multi_link_registry` nesnesindeki ilk öğeye bir yineleyici döndürür.

```cpp
virtual iterator begin();
```

### <a name="return-value"></a>Dönüş Değeri

`multi_link_registry` nesnesindeki ilk öğeyi adresleyen bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Bitiş durumu bir `NULL` bağlantısıyla belirtilir.

## <a name="contains"></a>vardır

`multi_link_registry` nesnesini belirtilen bir blok için arar.

```cpp
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
`multi_link_registry` nesnesinde aranacak bir blok işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen blok bulunursa **true** , aksi durumda **false** .

## <a name="count"></a>biriktirme

`multi_link_registry` nesnesindeki öğelerin sayısını sayar.

```cpp
virtual size_t count();
```

### <a name="return-value"></a>Dönüş Değeri

`multi_link_registry` nesnesindeki öğelerin sayısı.

## <a name="ctor"></a>multi_link_registry

`multi_link_registry` nesnesi oluşturur.

```cpp
multi_link_registry();
```

## <a name="dtor"></a>~ multi_link_registry

`multi_link_registry` nesnesini yok eder.

```cpp
virtual ~multi_link_registry();
```

### <a name="remarks"></a>Açıklamalar

Yöntemi, tüm bağlantılar kaldırılmadan önce çağrılırsa bir [invalid_operation](invalid-operation-class.md) özel durumu oluşturur.

## <a name="remove"></a>temizlenmesine

`multi_link_registry` nesnesinden bir bağlantıyı kaldırır.

```cpp
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>Parametreler

*_Link*<br/>
Bulunursa, kaldırılacak bloğa yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

bağlantı bulunursa ve kaldırılırsa **doğru** , aksi takdirde **yanlış** olur.

## <a name="set_bound"></a>set_bound

`multi_link_registry` nesnenin tutadığı bağlantı sayısı üst sınırını ayarlar.

```cpp
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>Parametreler

*_MaxLinks*<br/>
`multi_link_registry` nesnesinin tutadığı en fazla bağlantı sayısı.

### <a name="remarks"></a>Açıklamalar

Bir bağlantı kurulduktan sonra, bir girdinin bağlantısını kesmek `multi_link_registry` nesnesinin `add` daha fazla çağrının bir `invalid_link_target` özel durum oluşturması için sabit bir durum girmesine neden olur.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[single_link_registry Sınıfı](single-link-registry-class.md)
