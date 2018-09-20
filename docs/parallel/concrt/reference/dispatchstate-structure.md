---
title: DispatchState yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- DispatchState
- CONCRTRM/concurrency::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::m_dispatchStateSize
- CONCRTRM/concurrency::DispatchState::DispatchState::m_fIsPreviousContextAsynchronouslyBlocked
- CONCRTRM/concurrency::DispatchState::DispatchState::m_reserved
dev_langs:
- C++
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2cb60a183497942d7a8bea6a333d2dea62d8e2b4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448083"
---
# <a name="dispatchstate-structure"></a>DispatchState Yapısı

`DispatchState` Yapısı durumuna aktarmak için kullanılan `IExecutionContext::Dispatch` yöntemi. Hangi koşullarda açıklar `Dispatch` yöntemi çağrıldığında bir `IExecutionContext` arabirimi.

## <a name="syntax"></a>Sözdizimi

```
struct DispatchState;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[DispatchState::DispatchState](#ctor)|Yeni bir oluşturur `DispatchState` nesne.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[DispatchState::m_dispatchStateSize](#m_dispatchstatesize)|Bu yapı, sürüm oluşturma için kullanılan boyutu.|
|[Dispatchstate::m_fıspreviouscontextasynchronouslyblocked](#m_fispreviouscontextasynchronouslyblocked)|Bu bağlam girmediğini söyler `Dispatch` yöntemi çünkü zaman uyumsuz olarak önceki bağlam engellendi. Bu yalnızca UMS zamanlama bağlamda kullanılır ve değere ayarlanmış `0` için diğer tüm yürütme bağlamları.|
|[DispatchState::m_reserved](#m_reserved)|BITS, gelecekteki bilgi geçirme için ayrılmış.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`DispatchState`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrtrm.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a>  DispatchState::DispatchState Oluşturucusu

Yeni bir oluşturur `DispatchState` nesne.

```
DispatchState();
```

##  <a name="m_dispatchstatesize"></a>  DispatchState::m_dispatchStateSize veri üyesi

Bu yapı, sürüm oluşturma için kullanılan boyutu.

```
unsigned long m_dispatchStateSize;
```

##  <a name="m_fispreviouscontextasynchronouslyblocked"></a>  Dispatchstate::m_fıspreviouscontextasynchronouslyblocked veri üyesi

Bu bağlam girmediğini söyler `Dispatch` yöntemi çünkü zaman uyumsuz olarak önceki bağlam engellendi. Bu yalnızca UMS zamanlama bağlamda kullanılır ve değere ayarlanmış `0` için diğer tüm yürütme bağlamları.

```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

##  <a name="m_reserved"></a>  DispatchState::m_reserved veri üyesi

BITS, gelecekteki bilgi geçirme için ayrılmış.

```
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
