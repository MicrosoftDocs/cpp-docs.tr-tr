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
ms.openlocfilehash: 7c8ce0aefc12097a71e79933d34a116997c8105f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276370"
---
# <a name="invalidmultiplescheduling-class"></a>invalid_multiple_scheduling Sınıfı

Bu sınıf oluşan bir özel durumu anlatmaktadır bir `task_handle` nesnedir kullanarak süreleri zamanlanmış birden çok `run` yöntemi bir `task_group` veya `structured_task_group` nesnesi olmadan bir çağrı göndermelisiniz `wait` veya `run_and_wait` yöntemleri.

## <a name="syntax"></a>Sözdizimi

```
class invalid_multiple_scheduling : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[invalid_multiple_scheduling](#ctor)|Fazla Yüklendi. Oluşturur bir `invalid_multiple_scheduling` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`invalid_multiple_scheduling`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> invalid_multiple_scheduling

Oluşturur bir `invalid_multiple_scheduling` nesne.

```
explicit _CRTIMP invalid_multiple_scheduling(_In_z_ const char* _Message) throw();

invalid_multiple_scheduling() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[task_handle Sınıfı](task-handle-class.md)<br/>
[task_group Sınıfı](task-group-class.md)<br/>
[run](task-group-class.md)<br/>
[bekleme](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group Sınıfı](structured-task-group-class.md)
