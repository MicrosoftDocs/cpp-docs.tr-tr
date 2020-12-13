---
description: 'Hakkında daha fazla bilgi edinin: invalid_scheduler_policy_value sınıfı'
title: invalid_scheduler_policy_value Sınıfı
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_value
helpviewer_keywords:
- invalid_scheduler_policy_value class
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
ms.openlocfilehash: c91295646b0bc85ea4ed5ee8f376c1ed029e4f0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334489"
---
# <a name="invalid_scheduler_policy_value-class"></a>invalid_scheduler_policy_value Sınıfı

Bu sınıf, bir nesnenin ilke anahtarı `SchedulerPolicy` Bu anahtar için geçersiz bir değere ayarlandığında oluşturulan bir özel durumu açıklar.

## <a name="syntax"></a>Syntax

```cpp
class invalid_scheduler_policy_value : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_scheduler_policy_value] (geçersiz-Scheduler-Policy-thread-Specification-Class. MD # ctor|Fazla Yüklendi. Bir `invalid_scheduler_policy_value` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_scheduler_policy_value`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="invalid_scheduler_policy_value"></a><a name="ctor"></a> invalid_scheduler_policy_value

Bir `invalid_scheduler_policy_value` nesnesi oluşturur.

```cpp
explicit _CRTIMP invalid_scheduler_policy_value(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_value() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[SchedulerPolicy Sınıfı](schedulerpolicy-class.md)
