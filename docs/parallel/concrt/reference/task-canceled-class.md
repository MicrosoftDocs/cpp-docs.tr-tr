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
ms.openlocfilehash: caef1c62ff09ffb76f74d4a1453e9d59dcb7d45b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265502"
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

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
