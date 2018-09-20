---
title: scheduler_interface yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
dev_langs:
- C++
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2178eddef2dcf7c2f48a5667930bc639781628fb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425382"
---
# <a name="schedulerinterface-structure"></a>scheduler_interface Yapısı

Zamanlayıcı arabirimi

## <a name="syntax"></a>Sözdizimi

```
struct __declspec(novtable) scheduler_interface;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[scheduler_interface::schedule](#schedule)||

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`scheduler_interface`

## <a name="requirements"></a>Gereksinimler

**Başlık:** pplinterface.h

**Namespace:** eşzamanlılık

##  <a name="schedule"></a>  scheduler_interface::Schedule yöntemi

```
virtual void schedule(
    TaskProc_t,
void*) = 0;
```

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
