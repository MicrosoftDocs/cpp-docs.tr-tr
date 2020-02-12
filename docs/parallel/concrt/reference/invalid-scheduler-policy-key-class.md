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
ms.openlocfilehash: 60d5a57ff9cb33a3d522c14514f5107844216852
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143020"
---
# <a name="invalid_scheduler_policy_key-class"></a>invalid_scheduler_policy_key Sınıfı

Bu sınıf, `SchedulerPolicy` nesne oluşturucusuna geçersiz veya bilinmeyen bir anahtar geçirildiğinde oluşturulan bir özel durumu açıklar veya bir `SchedulerPolicy` nesnesinin `SetPolicyValue` yöntemine `SetConcurrencyLimits` yöntemi gibi diğer yollarla değiştirilmesi gereken bir anahtar geçirilir.

## <a name="syntax"></a>Sözdizimi

```cpp
class invalid_scheduler_policy_key : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_scheduler_policy_key](#ctor)|Fazla Yüklendi. `invalid_scheduler_policy_key` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_scheduler_policy_key`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>invalid_scheduler_policy_key

`invalid_scheduler_policy_key` nesnesi oluşturur.

```cpp
explicit _CRTIMP invalid_scheduler_policy_key(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_key() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[SchedulerPolicy Sınıfı](schedulerpolicy-class.md)
