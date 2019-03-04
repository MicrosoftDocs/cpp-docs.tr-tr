---
title: invalid_scheduler_policy_thread_specification Sınıfı
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_thread_specification
helpviewer_keywords:
- invalid_scheduler_policy_thread_specification class
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
ms.openlocfilehash: 26d09610c6bb9e0c87852c9804e094617b021273
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278879"
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

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[SchedulerPolicy Sınıfı](schedulerpolicy-class.md)
