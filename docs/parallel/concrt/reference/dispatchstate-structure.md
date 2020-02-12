---
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
ms.openlocfilehash: 69e00893373ccca6e2ed676fbb7f5a109c49efdf
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143051"
---
# <a name="dispatchstate-structure"></a>DispatchState Yapısı

`DispatchState` yapısı, durumu `IExecutionContext::Dispatch` yöntemine aktarmak için kullanılır. `Dispatch` yönteminin bir `IExecutionContext` arabiriminde çağrıldığı koşulları açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
struct DispatchState;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[DispatchState::D ispatchState](#ctor)|Yeni bir `DispatchState` nesnesi oluşturur.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[DispatchState:: m_dispatchStateSize](#m_dispatchstatesize)|Sürüm oluşturma için kullanılan bu yapının boyutu.|
|[DispatchState:: m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|Önceki bağlam zaman uyumsuz olarak engellendiğinden, bu bağlamın `Dispatch` yöntemi girilip girilmediğini söyler. Bu yalnızca UMS zamanlama bağlamında kullanılır ve tüm diğer yürütme bağlamları için `0` değere ayarlanır.|
|[DispatchState:: m_reserved](#m_reserved)|Gelecekteki bilgi geçirme için ayrılan bitler.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`DispatchState`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>DispatchState::D ispatchState Oluşturucusu

Yeni bir `DispatchState` nesnesi oluşturur.

```cpp
DispatchState();
```

## <a name="m_dispatchstatesize"></a>DispatchState:: m_dispatchStateSize veri üyesi

Sürüm oluşturma için kullanılan bu yapının boyutu.

```cpp
unsigned long m_dispatchStateSize;
```

## <a name="m_fispreviouscontextasynchronouslyblocked"></a>DispatchState:: m_fIsPreviousContextAsynchronouslyBlocked veri üyesi

Önceki bağlam zaman uyumsuz olarak engellendiğinden, bu bağlamın `Dispatch` yöntemi girilip girilmediğini söyler. Bu yalnızca UMS zamanlama bağlamında kullanılır ve tüm diğer yürütme bağlamları için `0` değere ayarlanır.

```cpp
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

## <a name="m_reserved"></a>DispatchState:: m_reserved veri üyesi

Gelecekteki bilgi geçirme için ayrılan bitler.

```cpp
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
