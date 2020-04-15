---
title: scheduler_ptr Yapısı
ms.date: 11/04/2016
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
ms.openlocfilehash: 60d71a26e5dffcadfb900ef15c26a6d9dc6d6f8b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358777"
---
# <a name="scheduler_ptr-structure"></a>scheduler_ptr Yapısı

Zamanlayıcıiçin bir işaretçiyi temsil eder. Bu sınıf, ham işaretçi kullanarak shared_ptr veya yalnızca düz bir başvuru kullanarak paylaşılan bir yaşam süresinin belirtimini sağlamak için vardır.

## <a name="syntax"></a>Sözdizimi

```cpp
struct scheduler_ptr;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[scheduler_ptr:scheduler_ptr](#ctor)|Fazla Yüklendi. shared_ptr'dan zamanlayıcıya zamanlama işaretçisi oluşturur|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[scheduler_ptr::get](#get)|Ham işaretçiyi zamanlayıcıya verir|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[scheduler_ptr::operatör bool](#operator_bool)|Zamanlayıcı işaretçisinin null olup olmadığını test etme|
|[scheduler_ptr::operatör-&gt;](#operator_ptr)|Bir işaretçi gibi görün|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`scheduler_ptr`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** pplinterface.h

**Ad alanı:** eşzamanlılık

## <a name="scheduler_ptrget-method"></a><a name="get"></a>scheduler_ptr::get Method

Ham işaretçiyi zamanlayıcıya verir.

```cpp
scheduler_interface* get() const;
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="scheduler_ptroperator-bool"></a><a name="operator_bool"></a>scheduler_ptr::operatör bool

Zamanlayıcı işaretçisinin null olup olmadığını sınar.

```cpp
operator bool() const;
```

## <a name="scheduler_ptroperator-gt"></a><a name="operator_ptr"></a>scheduler_ptr::operatör-&gt;

Bir işaretçi gibi olur.

```cpp
scheduler_interface* operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

## <a name="scheduler_ptrscheduler_ptr-constructor"></a><a name="ctor"></a>scheduler_ptr::scheduler_ptr Yapıcı

shared_ptr'dan zamanlayıcıya kadar bir zamanlayıcı işaretçisi oluşturur.

```cpp
explicit scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);
explicit scheduler_ptr(_In_opt_ scheduler_interface* pScheduler);
```

### <a name="parameters"></a>Parametreler

*Zamanlayıcı*<br/>
Dönüştürmek için zamanlayıcı.

*pScheduler*<br/>
Dönüştürmeiçin zamanlayıcı işaretçisi.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)
