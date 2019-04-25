---
title: scheduler_ptr yapısı
ms.date: 11/04/2016
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
ms.openlocfilehash: 2373fe3bc8cac501d1b6b32ca66996eff47ba6f3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180739"
---
# <a name="schedulerptr-structure"></a>scheduler_ptr yapısı

Bir işaretçi için bir Zamanlayıcı'yı temsil eder. Shared_ptr veya yalnızca bir düz başvuru ham işaretçiyi kullanarak paylaşılan bir kullanım ömrünün belirtilmesine izin vermek için bu sınıfı var.

## <a name="syntax"></a>Sözdizimi

```
struct scheduler_ptr;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[scheduler_ptr::scheduler_ptr](#ctor)|Fazla Yüklendi. Bir zamanlayıcı işaretçisi shared_ptr'den zamanlayıcıya oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[scheduler_ptr::get](#get)|Zamanlayıcıya ham işaretçiyi döndürür|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[scheduler_ptr::operator bool](#operator_bool)|Zamanlayıcı işaretçisinin null dışında değer olup olmadığını test edin|
|[scheduler_ptr::operator-&gt;](#operator_ptr)|Bir işaretçi gibi davranma|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`scheduler_ptr`

## <a name="requirements"></a>Gereksinimler

**Başlık:** pplinterface.h

**Namespace:** eşzamanlılık

##  <a name="get"></a>  scheduler_ptr::GET yöntemi

Zamanlayıcıya ham işaretçiyi döndürür.

```
scheduler_interface* get() const;
```

### <a name="return-value"></a>Dönüş Değeri

##  <a name="operator_bool"></a>  scheduler_ptr::operator bool

Zamanlayıcı işaretçisinin null dışında değer olup olmadığını sınar.

```
operator bool() const;
```

##  <a name="operator_ptr"></a>  scheduler_ptr::operator-&gt;

Bir işaretçi gibi davranır.

```
scheduler_interface* operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

##  <a name="ctor"></a>  scheduler_ptr::scheduler_ptr Oluşturucusu

Bir zamanlayıcı işaretçisi shared_ptr'den zamanlayıcıya oluşturur.

```
explicit scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);
explicit scheduler_ptr(_In_opt_ scheduler_interface* pScheduler);
```

### <a name="parameters"></a>Parametreler

*scheduler*<br/>
Dönüştürülecek Zamanlayıcı.

*pScheduler*<br/>
Dönüştürülecek Zamanlayıcı işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
