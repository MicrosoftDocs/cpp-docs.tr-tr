---
title: invalid_scheduler_policy_value Sınıfı
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_value
helpviewer_keywords:
- invalid_scheduler_policy_value class
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
ms.openlocfilehash: 6a66b2b303a4b3b0cb8c2c7a3c515ac8cd1b33a0
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143001"
---
# <a name="invalid_scheduler_policy_value-class"></a>invalid_scheduler_policy_value Sınıfı

Bu sınıf, bir `SchedulerPolicy` nesnesinin ilke anahtarı bu anahtar için geçersiz bir değere ayarlandığında oluşturulan bir özel durumu açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class invalid_scheduler_policy_value : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_scheduler_policy_value] (geçersiz-Scheduler-Policy-thread-Specification-Class. MD # ctor|Fazla Yüklendi. `invalid_scheduler_policy_value` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_scheduler_policy_value`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>invalid_scheduler_policy_value

`invalid_scheduler_policy_value` nesnesi oluşturur.

```cpp
explicit _CRTIMP invalid_scheduler_policy_value(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_value() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[SchedulerPolicy Sınıfı](schedulerpolicy-class.md)
