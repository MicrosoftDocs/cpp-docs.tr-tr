---
description: 'Daha fazla bilgi edinin: DispatchState Yapısı'
title: DispatchState Yapısı
ms.date: 11/04/2016
f1_keywords:
- DispatchState
- CONCRTRM/concurrency::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::m_dispatchStateSize
- CONCRTRM/concurrency::DispatchState::DispatchState::m_fIsPreviousContextAsynchronouslyBlocked
- CONCRTRM/concurrency::DispatchState::DispatchState::m_reserved
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
ms.openlocfilehash: 1352a283d6f75d90872e75da92450a4867cf497f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169430"
---
# <a name="dispatchstate-structure"></a>DispatchState Yapısı

`DispatchState`Yapı, durumu yöntemine aktarmak için kullanılır `IExecutionContext::Dispatch` . Bu, `Dispatch` yönteminin bir arabirimde çağrıldığı koşulları açıklar `IExecutionContext` .

## <a name="syntax"></a>Syntax

```cpp
struct DispatchState;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[DispatchState::D ispatchState](#ctor)|Yeni bir `DispatchState` nesne oluşturur.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[DispatchState:: m_dispatchStateSize](#m_dispatchstatesize)|Sürüm oluşturma için kullanılan bu yapının boyutu.|
|[DispatchState:: m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|Önceki bağlam zaman uyumsuz olarak engellendiğinden bu bağlamın yöntemi girdikten sonra bu bağlamı belirtir `Dispatch` . Bu yalnızca UMS zamanlama bağlamında kullanılır ve `0` tüm diğer yürütme bağlamları için değere ayarlanır.|
|[DispatchState:: m_reserved](#m_reserved)|Gelecekteki bilgi geçirme için ayrılan bitler.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`DispatchState`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="dispatchstatedispatchstate-constructor"></a><a name="ctor"></a> DispatchState::D ispatchState Oluşturucusu

Yeni bir `DispatchState` nesne oluşturur.

```cpp
DispatchState();
```

## <a name="dispatchstatem_dispatchstatesize-data-member"></a><a name="m_dispatchstatesize"></a> DispatchState:: m_dispatchStateSize veri üyesi

Sürüm oluşturma için kullanılan bu yapının boyutu.

```cpp
unsigned long m_dispatchStateSize;
```

## <a name="dispatchstatem_fispreviouscontextasynchronouslyblocked-data-member"></a><a name="m_fispreviouscontextasynchronouslyblocked"></a> DispatchState:: m_fIsPreviousContextAsynchronouslyBlocked veri üyesi

Önceki bağlam zaman uyumsuz olarak engellendiğinden bu bağlamın yöntemi girdikten sonra bu bağlamı belirtir `Dispatch` . Bu yalnızca UMS zamanlama bağlamında kullanılır ve `0` tüm diğer yürütme bağlamları için değere ayarlanır.

```cpp
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

## <a name="dispatchstatem_reserved-data-member"></a><a name="m_reserved"></a> DispatchState:: m_reserved veri üyesi

Gelecekteki bilgi geçirme için ayrılan bitler.

```cpp
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
