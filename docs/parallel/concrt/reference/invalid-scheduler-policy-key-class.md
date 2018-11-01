---
title: invalid_scheduler_policy_key Sınıfı
ms.date: 11/04/2016
f1_keywords:
- invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key::invalid_scheduler_policy_key
helpviewer_keywords:
- invalid_scheduler_policy_key class
ms.assetid: 6a7c42fe-9bc4-4a02-bebb-99fe9ef9817d
ms.openlocfilehash: 775b98d2394dce04b362e92927db1a408b8e1656
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677415"
---
# <a name="invalidschedulerpolicykey-class"></a>invalid_scheduler_policy_key Sınıfı

Bu sınıf geçersiz olduğunda oluşturulan bir özel durumu açıklayan veya bilinmeyen anahtarı geçirildiğinde bir `SchedulerPolicy` nesne Oluşturucu, veya `SetPolicyValue` yöntemi bir `SchedulerPolicy` nesnesi gibi diğer araçları kullanarak değiştirmesi gereken bir anahtarı geçirildi `SetConcurrencyLimits` yöntemi.

## <a name="syntax"></a>Sözdizimi

```
class invalid_scheduler_policy_key : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_scheduler_policy_key](#ctor)|Fazla Yüklendi. Oluşturur bir `invalid_scheduler_policy_key` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_scheduler_policy_key`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> invalid_scheduler_policy_key

Oluşturur bir `invalid_scheduler_policy_key` nesne.

```
explicit _CRTIMP invalid_scheduler_policy_key(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_key() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[SchedulerPolicy Sınıfı](schedulerpolicy-class.md)
