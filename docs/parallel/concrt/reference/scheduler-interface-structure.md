---
description: 'Daha fazla bilgi edinin: scheduler_interface yapısı'
title: scheduler_interface Yapısı
ms.date: 11/04/2016
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
ms.openlocfilehash: ba56ef809cf398a192810eb96a8b4e4ca50ec1cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188878"
---
# <a name="scheduler_interface-structure"></a>scheduler_interface Yapısı

Zamanlayıcı arabirimi

## <a name="syntax"></a>Syntax

```cpp
struct __declspec(novtable) scheduler_interface;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[scheduler_interface:: Schedule](#schedule)||

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`scheduler_interface`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** pplınterface. h

**Ad alanı:** eşzamanlılık

## <a name="scheduler_interfaceschedule-method"></a><a name="schedule"></a> scheduler_interface:: Schedule yöntemi

```cpp
virtual void schedule(
    TaskProc_t,
void*) = 0;
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
