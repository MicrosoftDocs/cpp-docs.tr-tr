---
title: scheduler_interface Yapısı
ms.date: 11/04/2016
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
ms.openlocfilehash: 99a3ea8b6ad1f23b4f3d54b7f2f406a3d115b374
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283377"
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

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
