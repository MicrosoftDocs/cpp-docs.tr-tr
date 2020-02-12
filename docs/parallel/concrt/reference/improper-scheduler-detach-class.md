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
ms.openlocfilehash: 2f5ad16893a898d4258762b25fea3d557607a3f8
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141149"
---
# <a name="improper_scheduler_detach-class"></a>improper_scheduler_detach Sınıfı

Bu sınıf, bir `Scheduler` nesnesinin `Attach` yöntemi kullanılarak herhangi bir Scheduler 'a eklenmemiş bir bağlamda `CurrentScheduler::Detach` yöntemi çağrıldığında oluşturulan bir özel durumu açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class improper_scheduler_detach : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[improper_scheduler_detach](#ctor)|Fazla Yüklendi. `improper_scheduler_detach` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`improper_scheduler_detach`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>improper_scheduler_detach

`improper_scheduler_detach` nesnesi oluşturur.

```cpp
explicit _CRTIMP improper_scheduler_detach(_In_z_ const char* _Message) throw();

improper_scheduler_detach() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[Zamanlayıcı Sınıfı](scheduler-class.md)
