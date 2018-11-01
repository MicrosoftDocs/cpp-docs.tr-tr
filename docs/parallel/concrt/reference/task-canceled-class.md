---
title: task_canceled Sınıfı
ms.date: 11/04/2016
f1_keywords:
- task_canceled
- CONCRT/concurrency::task_canceled
- CONCRT/concurrency::task_canceled::task_canceled
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
ms.openlocfilehash: b17050deacd1dee0c1b08ffbc4056e957884cd3a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617457"
---
# <a name="taskcanceled-class"></a>task_canceled Sınıfı

Bu sınıf, geçerli görevi iptal etmek için zorlamak için PPL görev katmanı tarafından verilen bir özel durumu anlatmaktadır. Ayrıca tarafından oluşturulur `get()` metodunda [görev](/visualstudio/extensibility/debugger/task-class-internal-members), iptal edilen bir görev için.

## <a name="syntax"></a>Sözdizimi

```
class task_canceled : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[task_canceled](#ctor)|Fazla Yüklendi. Oluşturur bir `task_canceled` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`task_canceled`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> task_canceled

Oluşturur bir `task_canceled` nesne.

```
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```

### <a name="parameters"></a>Parametreler

*İl_eti*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
