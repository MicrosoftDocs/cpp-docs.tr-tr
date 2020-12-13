---
description: 'Hakkında daha fazla bilgi edinin: invalid_scheduler_policy_key sınıfı'
title: invalid_scheduler_policy_key Sınıfı
ms.date: 11/04/2016
f1_keywords:
- invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key::invalid_scheduler_policy_key
helpviewer_keywords:
- invalid_scheduler_policy_key class
ms.assetid: 6a7c42fe-9bc4-4a02-bebb-99fe9ef9817d
ms.openlocfilehash: d352246cf0fe94f0ba5ee567f353680c89efcddc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334512"
---
# <a name="invalid_scheduler_policy_key-class"></a>invalid_scheduler_policy_key Sınıfı

Bu sınıf, bir nesne oluşturucusuna geçersiz veya bilinmeyen bir anahtar geçirildiğinde oluşturulan bir özel durumu açıklar `SchedulerPolicy` veya `SetPolicyValue` bir nesnenin yöntemi, yöntemi gibi `SchedulerPolicy` diğer yollarla değiştirilmesi gereken bir anahtarı geçirmez `SetConcurrencyLimits` .

## <a name="syntax"></a>Syntax

```cpp
class invalid_scheduler_policy_key : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_scheduler_policy_key](#ctor)|Fazla Yüklendi. Bir `invalid_scheduler_policy_key` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_scheduler_policy_key`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="invalid_scheduler_policy_key"></a><a name="ctor"></a> invalid_scheduler_policy_key

Bir `invalid_scheduler_policy_key` nesnesi oluşturur.

```cpp
explicit _CRTIMP invalid_scheduler_policy_key(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_key() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[SchedulerPolicy Sınıfı](schedulerpolicy-class.md)
