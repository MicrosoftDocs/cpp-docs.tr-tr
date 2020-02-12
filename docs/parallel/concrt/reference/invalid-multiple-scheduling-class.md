---
title: invalid_multiple_scheduling Sınıfı
ms.date: 11/04/2016
f1_keywords:
- invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling::invalid_multiple_scheduling
helpviewer_keywords:
- invalid_multiple_scheduling class
ms.assetid: e9a47cb7-a778-4df7-92b0-3752119fd4c7
ms.openlocfilehash: a8b2a045ce94562dcba0019bc03aaa90c4d384a9
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140899"
---
# <a name="invalid_multiple_scheduling-class"></a>invalid_multiple_scheduling Sınıfı

Bu sınıf, `wait` veya `run_and_wait` yöntemlerine aradaki bir çağrı olmadan bir `task_group` veya `structured_task_group` nesnesinin `run` yöntemi kullanılarak birden çok kez zamanlan`task_handle` dığında oluşturulan bir özel durumu açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class invalid_multiple_scheduling : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_multiple_scheduling](#ctor)|Fazla Yüklendi. `invalid_multiple_scheduling` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_multiple_scheduling`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>invalid_multiple_scheduling

`invalid_multiple_scheduling` nesnesi oluşturur.

```cpp
explicit _CRTIMP invalid_multiple_scheduling(_In_z_ const char* _Message) throw();

invalid_multiple_scheduling() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[task_handle Sınıfı](task-handle-class.md)<br/>
[task_group Sınıfı](task-group-class.md)<br/>
[çalışmaz](task-group-class.md)<br/>
[bekleneceğini](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group Sınıfı](structured-task-group-class.md)
