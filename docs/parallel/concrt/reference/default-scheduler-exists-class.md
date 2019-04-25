---
title: default_scheduler_exists Sınıfı
ms.date: 11/04/2016
f1_keywords:
- default_scheduler_exists
- CONCRT/concurrency::default_scheduler_exists
- CONCRT/concurrency::default_scheduler_exists::default_scheduler_exists
helpviewer_keywords:
- default_scheduler_exists class
ms.assetid: f6e575e2-4e0f-455a-9e06-54f462ce0c1c
ms.openlocfilehash: 326a2dfc6837665adb4d46a6aaa8780052ad2b22
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62296104"
---
# <a name="defaultschedulerexists-class"></a>default_scheduler_exists Sınıfı

Bu sınıf oluşan bir özel durumu anlatmaktadır `Scheduler::SetDefaultSchedulerPolicy` varsayılan Zamanlayıcı işlem içinde zaten mevcut olduğunda yöntemi çağrılır.

## <a name="syntax"></a>Sözdizimi

```
class default_scheduler_exists : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[default_scheduler_exists](#ctor)|Fazla Yüklendi. Oluşturur bir `default_scheduler_exists` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`default_scheduler_exists`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> default_scheduler_exists

Oluşturur bir `default_scheduler_exists` nesne.

```
explicit _CRTIMP default_scheduler_exists(_In_z_ const char* _Message) throw();

default_scheduler_exists() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
