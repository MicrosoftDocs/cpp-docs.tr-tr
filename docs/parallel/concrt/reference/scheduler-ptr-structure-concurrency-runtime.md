---
description: 'Daha fazla bilgi edinin: scheduler_ptr yapısı'
title: scheduler_ptr yapısı
ms.date: 11/04/2016
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
ms.openlocfilehash: 314f587c0fd55772a8b1b7b5b8fdf3ddeb53a7a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188787"
---
# <a name="scheduler_ptr-structure"></a>scheduler_ptr yapısı

Scheduler 'a yönelik bir işaretçi temsil eder. Bu sınıf, shared_ptr veya ham işaretçi kullanılarak yalnızca düz bir başvuru kullanılarak paylaşılan bir yaşam süresi belirtimine izin vermek için mevcuttur.

## <a name="syntax"></a>Syntax

```cpp
struct scheduler_ptr;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[scheduler_ptr:: scheduler_ptr](#ctor)|Fazla Yüklendi. Shared_ptr Scheduler 'dan Scheduler 'a bir Zamanlayıcı işaretçisi oluşturur|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[scheduler_ptr:: Get](#get)|Scheduler 'a ham işaretçiyi döndürür|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[scheduler_ptr:: operator bool](#operator_bool)|Zamanlayıcı işaretçisinin NULL olmadığını test edin|
|[scheduler_ptr:: operator-&gt;](#operator_ptr)|Bir işaretçi gibi davranır|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`scheduler_ptr`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** pplınterface. h

**Ad alanı:** eşzamanlılık

## <a name="scheduler_ptrget-method"></a><a name="get"></a> scheduler_ptr:: get yöntemi

Scheduler 'a ham işaretçiyi döndürür.

```cpp
scheduler_interface* get() const;
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="scheduler_ptroperator-bool"></a><a name="operator_bool"></a> scheduler_ptr:: operator bool

Zamanlayıcı işaretçisinin null olup olmadığını sınar.

```cpp
operator bool() const;
```

## <a name="scheduler_ptroperator-gt"></a><a name="operator_ptr"></a> scheduler_ptr:: operator-&gt;

Bir işaretçi gibi davranır.

```cpp
scheduler_interface* operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="scheduler_ptrscheduler_ptr-constructor"></a><a name="ctor"></a> scheduler_ptr:: scheduler_ptr Oluşturucusu

Shared_ptr Scheduler 'dan Scheduler 'a bir Zamanlayıcı işaretçisi oluşturur.

```cpp
explicit scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);
explicit scheduler_ptr(_In_opt_ scheduler_interface* pScheduler);
```

### <a name="parameters"></a>Parametreler

*leyiciyi*<br/>
Dönüştürülecek Zamanlayıcı.

*pScheduler*<br/>
Dönüştürülecek Zamanlayıcı işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
