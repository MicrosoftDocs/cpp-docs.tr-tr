---
description: 'Hakkında daha fazla bilgi edinin: invalid_multiple_scheduling sınıfı'
title: invalid_multiple_scheduling Sınıfı
ms.date: 11/04/2016
f1_keywords:
- invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling::invalid_multiple_scheduling
helpviewer_keywords:
- invalid_multiple_scheduling class
ms.assetid: e9a47cb7-a778-4df7-92b0-3752119fd4c7
ms.openlocfilehash: 23d89d93c953a3c01a6e0e698cfa7489effd2986
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334553"
---
# <a name="invalid_multiple_scheduling-class"></a>invalid_multiple_scheduling Sınıfı

Bu sınıf `task_handle` `run` `task_group` `structured_task_group` , veya yöntemlerine aradaki bir çağrı olmadan bir veya nesnesinin yöntemi kullanılarak bir nesne birden çok kez zamanlandığında oluşturulan bir `wait` özel durumu açıklar `run_and_wait` .

## <a name="syntax"></a>Syntax

```cpp
class invalid_multiple_scheduling : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_multiple_scheduling](#ctor)|Fazla Yüklendi. Bir `invalid_multiple_scheduling` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_multiple_scheduling`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="invalid_multiple_scheduling"></a><a name="ctor"></a> invalid_multiple_scheduling

Bir `invalid_multiple_scheduling` nesnesi oluşturur.

```cpp
explicit _CRTIMP invalid_multiple_scheduling(_In_z_ const char* _Message) throw();

invalid_multiple_scheduling() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[task_handle Sınıfı](task-handle-class.md)<br/>
[task_group sınıfı](task-group-class.md)<br/>
[çalışmaz](task-group-class.md)<br/>
[bekleneceğini](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group sınıfı](structured-task-group-class.md)
