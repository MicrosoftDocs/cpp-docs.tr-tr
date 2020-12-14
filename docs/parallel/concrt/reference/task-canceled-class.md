---
description: 'Hakkında daha fazla bilgi edinin: task_canceled sınıfı'
title: task_canceled Sınıfı
ms.date: 11/04/2016
f1_keywords:
- task_canceled
- CONCRT/concurrency::task_canceled
- CONCRT/concurrency::task_canceled::task_canceled
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
ms.openlocfilehash: 223a1168464e312c272f770247b3574311ff97ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188410"
---
# <a name="task_canceled-class"></a>task_canceled Sınıfı

Bu sınıf, geçerli görevin iptal edilmeye zorlamak için PPL görev katmanı tarafından oluşturulan bir özel durumu açıklar. Ayrıca `get()` , iptal edilen bir görev için [görev](/visualstudio/extensibility/debugger/task-class-internal-members)üzerindeki yöntemi tarafından da oluşturulur.

## <a name="syntax"></a>Syntax

```cpp
class task_canceled : public std::exception;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[task_canceled](#ctor)|Fazla Yüklendi. Bir `task_canceled` nesnesi oluşturur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`exception`

`task_canceled`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="task_canceled"></a><a name="ctor"></a> task_canceled

Bir `task_canceled` nesnesi oluşturur.

```cpp
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```

### <a name="parameters"></a>Parametreler

*_Message*<br/>
Hatanın açıklayıcı bir iletisi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
