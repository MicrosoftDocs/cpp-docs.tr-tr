---
title: invalid_scheduler_policy_thread_specification sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_thread_specification
dev_langs:
- C++
helpviewer_keywords:
- invalid_scheduler_policy_thread_specification class
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fc0f52bc36157bcbc1e6adaa28f786a01ac05263
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404923"
---
# <a name="invalidschedulerpolicythreadspecification-class"></a>invalid_scheduler_policy_thread_specification Sınıfı

Bu sınıf, eşzamanlılık sınırlarını ayarlamak için bir girişimde olduğunda oluşturulan bir özel durum açıklar bir `SchedulerPolicy` nesne gibi değerini `MinConcurrency` anahtar değerini azdır `MaxConcurrency` anahtarı.

## <a name="syntax"></a>Sözdizimi

```
class invalid_scheduler_policy_thread_specification : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_scheduler_policy_thread_specification] (geçersiz-Zamanlayıcı-ilkeyi-değeri-class.md #ctor|Fazla Yüklendi. Oluşturur bir `invalid_scheduler_policy_value` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_scheduler_policy_thread_specification`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık
##  <a name="ctor"></a> invalid_scheduler_policy_thread_specification

Oluşturur bir `invalid_scheduler_policy_value` nesne.

```
explicit _CRTIMP invalid_scheduler_policy_thread_specification(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_thread_specification() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[SchedulerPolicy Sınıfı](schedulerpolicy-class.md)
