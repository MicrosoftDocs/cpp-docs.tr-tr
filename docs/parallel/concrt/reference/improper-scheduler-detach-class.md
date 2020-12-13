---
description: 'Hakkında daha fazla bilgi edinin: improper_scheduler_detach sınıfı'
title: improper_scheduler_detach Sınıfı
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach::improper_scheduler_detach
helpviewer_keywords:
- improper_scheduler_detach class
ms.assetid: 30132102-c900-4951-a470-b63b4e3aa2d2
ms.openlocfilehash: 62def23a4a3459c4cb8268b3b0f4df4a77025668
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334616"
---
# <a name="improper_scheduler_detach-class"></a>improper_scheduler_detach Sınıfı

Bu sınıf, `CurrentScheduler::Detach` bir nesne yöntemi kullanılarak herhangi bir Scheduler 'a eklenmemiş bir bağlamda yöntemi çağrıldığında oluşturulan bir özel durumu açıklar `Attach` `Scheduler` .

## <a name="syntax"></a>Syntax

```cpp
class improper_scheduler_detach : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[improper_scheduler_detach](#ctor)|Fazla Yüklendi. Bir `improper_scheduler_detach` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`improper_scheduler_detach`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="improper_scheduler_detach"></a><a name="ctor"></a> improper_scheduler_detach

Bir `improper_scheduler_detach` nesnesi oluşturur.

```cpp
explicit _CRTIMP improper_scheduler_detach(_In_z_ const char* _Message) throw();

improper_scheduler_detach() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı sınıfı](scheduler-class.md)
