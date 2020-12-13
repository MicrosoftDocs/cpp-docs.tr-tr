---
description: 'Hakkında daha fazla bilgi edinin: invalid_scheduler_policy_thread_specification sınıfı'
title: invalid_scheduler_policy_thread_specification Sınıfı
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_thread_specification
helpviewer_keywords:
- invalid_scheduler_policy_thread_specification class
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
ms.openlocfilehash: 97a3910fc83e741c54ece51ed8e20686bbd6c66b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334501"
---
# <a name="invalid_scheduler_policy_thread_specification-class"></a>invalid_scheduler_policy_thread_specification Sınıfı

Bu sınıf, bir nesnenin eşzamanlılık sınırlarını ayarlamak için bir girişimde bulunulduğunda, `SchedulerPolicy` anahtarın değeri anahtarın değerinden küçükse oluşan bir özel durum tanımlar `MinConcurrency` `MaxConcurrency` .

## <a name="syntax"></a>Syntax

```cpp
class invalid_scheduler_policy_thread_specification : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_scheduler_policy_thread_specification] (geçersiz-Scheduler-Policy-value-class. MD # ctor|Fazla Yüklendi. Bir `invalid_scheduler_policy_value` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_scheduler_policy_thread_specification`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="invalid_scheduler_policy_thread_specification"></a><a name="ctor"></a> invalid_scheduler_policy_thread_specification

Bir `invalid_scheduler_policy_value` nesnesi oluşturur.

```cpp
explicit _CRTIMP invalid_scheduler_policy_thread_specification(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_thread_specification() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[SchedulerPolicy Sınıfı](schedulerpolicy-class.md)
