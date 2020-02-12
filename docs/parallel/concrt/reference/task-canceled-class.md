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
ms.openlocfilehash: b1436f921343843ee2b50888f00b6d470e513329
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142601"
---
# <a name="task_canceled-class"></a>task_canceled Sınıfı

Bu sınıf, geçerli görevin iptal edilmeye zorlamak için PPL görev katmanı tarafından oluşturulan bir özel durumu açıklar. Ayrıca, iptal edilen bir görev için [görev](/visualstudio/extensibility/debugger/task-class-internal-members)üzerinde `get()` yöntemi tarafından da oluşturulur.

## <a name="syntax"></a>Sözdizimi

```cpp
class task_canceled : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[task_canceled](#ctor)|Fazla Yüklendi. `task_canceled` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`task_canceled`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>task_canceled

`task_canceled` nesnesi oluşturur.

```cpp
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
