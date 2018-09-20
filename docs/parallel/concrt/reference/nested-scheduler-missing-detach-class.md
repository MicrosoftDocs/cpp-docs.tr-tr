---
title: nested_scheduler_missing_detach sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach
dev_langs:
- C++
helpviewer_keywords:
- nested_scheduler_missing_detach class
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7c862cdf778b726a4d416ea490f5da9c3d7eb01
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414894"
---
# <a name="nestedschedulermissingdetach-class"></a>nested_scheduler_missing_detach Sınıfı

Bu sınıf, eşzamanlılık çalışma zamanı çağırmaya ihmal algıladığında oluşturulan bir özel tanımlar `CurrentScheduler::Detach` yöntemi kullanarak ikinci bir zamanlayıcı bağlı bir bağlam `Attach` yöntemi `Scheduler` nesne.

## <a name="syntax"></a>Sözdizimi

```
class nested_scheduler_missing_detach : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[nested_scheduler_missing_detach](#ctor)|Fazla Yüklendi. Oluşturur bir `nested_scheduler_missing_detach` nesne.|

## <a name="remarks"></a>Açıklamalar

Çağırarak bir zamanlayıcı iç içe olduğunda bu durum `Attach` yöntemi bir `Scheduler` üzerinde zaten tarafından sahip olunan veya başka bir zamanlayıcı için bağlı bir bağlam nesnesi. Senaryo, sorun bulma için bir yardımcı olarak algılayabilir, eşzamanlılık çalışma zamanı modülüne bu özel durum oluşturur. Her örneğini çağrılacak önermesinin `CurrentScheduler::Detach` yöntemi için bu özel durum garantisi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`nested_scheduler_missing_detach`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> nested_scheduler_missing_detach

Oluşturur bir `nested_scheduler_missing_detach` nesne.

```
explicit _CRTIMP nested_scheduler_missing_detach(_In_z_ const char* _Message) throw();

nested_scheduler_missing_detach() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı Sınıfı](scheduler-class.md)
