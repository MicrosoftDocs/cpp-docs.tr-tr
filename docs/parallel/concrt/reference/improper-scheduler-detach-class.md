---
title: improper_scheduler_detach Sınıfı
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach::improper_scheduler_detach
helpviewer_keywords:
- improper_scheduler_detach class
ms.assetid: 30132102-c900-4951-a470-b63b4e3aa2d2
ms.openlocfilehash: 7e85ff8ea7ffb817c141094649cd39b8becccf53
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285041"
---
# <a name="improperschedulerdetach-class"></a>improper_scheduler_detach Sınıfı

Bu sınıf oluşan bir özel durumu anlatmaktadır `CurrentScheduler::Detach` yöntemi kullanarak herhangi bir zamanlayıcı için bağlı olmayan bir bağlamı çağrıldığında `Attach` yöntemi bir `Scheduler` nesne.

## <a name="syntax"></a>Sözdizimi

```
class improper_scheduler_detach : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[improper_scheduler_detach](#ctor)|Fazla Yüklendi. Oluşturur bir `improper_scheduler_detach` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`improper_scheduler_detach`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> improper_scheduler_detach

Oluşturur bir `improper_scheduler_detach` nesne.

```
explicit _CRTIMP improper_scheduler_detach(_In_z_ const char* _Message) throw();

improper_scheduler_detach() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı Sınıfı](scheduler-class.md)
