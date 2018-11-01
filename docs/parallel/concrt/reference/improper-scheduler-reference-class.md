---
title: improper_scheduler_reference Sınıfı
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference::improper_scheduler_reference
helpviewer_keywords:
- improper_scheduler_reference class
ms.assetid: 434a7512-7796-4255-92a7-f3bf71c6a7a7
ms.openlocfilehash: 9bb62fbf5048766d2d11f344a401979e107ec702
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597190"
---
# <a name="improperschedulerreference-class"></a>improper_scheduler_reference Sınıfı

Bu sınıf oluşan bir özel durumu anlatmaktadır `Reference` yöntemi çağrıldığında bir `Scheduler` aşağı, bu Zamanlayıcı bir parçası olmayan bir bağlamdan kapatılıyor nesne.

## <a name="syntax"></a>Sözdizimi

```
class improper_scheduler_reference : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[improper_scheduler_reference](#ctor)|Fazla Yüklendi. Oluşturur bir `improper_scheduler_reference` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`improper_scheduler_reference`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> improper_scheduler_reference

Oluşturur bir `improper_scheduler_reference` nesne.

```
explicit _CRTIMP improper_scheduler_reference(_In_z_ const char* _Message) throw();

improper_scheduler_reference() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı Sınıfı](scheduler-class.md)
