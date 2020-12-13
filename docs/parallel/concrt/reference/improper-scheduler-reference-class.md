---
description: 'Hakkında daha fazla bilgi edinin: improper_scheduler_reference sınıfı'
title: improper_scheduler_reference Sınıfı
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference::improper_scheduler_reference
helpviewer_keywords:
- improper_scheduler_reference class
ms.assetid: 434a7512-7796-4255-92a7-f3bf71c6a7a7
ms.openlocfilehash: 4857418e14908b2d085d52249236d6395284b98a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334605"
---
# <a name="improper_scheduler_reference-class"></a>improper_scheduler_reference Sınıfı

Bu sınıf `Reference` `Scheduler` , bu Scheduler 'ın parçası olmayan bir bağlamdan, yöntemi kapanmakta olan bir nesne üzerinde çağrıldığında oluşturulan bir özel durumu açıklar.

## <a name="syntax"></a>Syntax

```cpp
class improper_scheduler_reference : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[improper_scheduler_reference](#ctor)|Fazla Yüklendi. Bir `improper_scheduler_reference` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`improper_scheduler_reference`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="improper_scheduler_reference"></a><a name="ctor"></a> improper_scheduler_reference

Bir `improper_scheduler_reference` nesnesi oluşturur.

```cpp
explicit _CRTIMP improper_scheduler_reference(_In_z_ const char* _Message) throw();

improper_scheduler_reference() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı sınıfı](scheduler-class.md)
