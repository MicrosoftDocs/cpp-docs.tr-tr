---
title: invalid_scheduler_policy_value Sınıfı
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_value
helpviewer_keywords:
- invalid_scheduler_policy_value class
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
ms.openlocfilehash: 53a4ee37c28cd7d45552cfe4dd7d25ce9fa37a70
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439603"
---
# <a name="invalidschedulerpolicyvalue-class"></a>invalid_scheduler_policy_value Sınıfı

Bu sınıf bir ilke anahtarı olduğunda oluşturulan bir özel durumu anlatmaktadır bir `SchedulerPolicy` nesne bu anahtar için geçersiz bir değere ayarlanır.

## <a name="syntax"></a>Sözdizimi

```
class invalid_scheduler_policy_value : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_scheduler_policy_value] (invalid-scheduler-policy-thread-specification-class.md#ctor|Fazla Yüklendi. Oluşturur bir `invalid_scheduler_policy_value` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_scheduler_policy_value`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> invalid_scheduler_policy_value

Oluşturur bir `invalid_scheduler_policy_value` nesne.

```
explicit _CRTIMP invalid_scheduler_policy_value(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_value() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[SchedulerPolicy Sınıfı](schedulerpolicy-class.md)
