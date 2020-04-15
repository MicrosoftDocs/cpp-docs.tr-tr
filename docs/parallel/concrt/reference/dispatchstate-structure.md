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
ms.openlocfilehash: 2c4103f89f7fc74c5368bafac3c82685ff9b6e03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372693"
---
# <a name="dispatchstate-structure"></a>DispatchState Yapısı

Yapı, `DispatchState` durumu `IExecutionContext::Dispatch` yönteme aktarmak için kullanılır. Yöntemin `Dispatch` arabirimde `IExecutionContext` çağrıldığı koşulları açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
struct DispatchState;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[DispatchState::DispatchState](#ctor)|Yeni `DispatchState` bir nesne oluşturuyor.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[DispatchState::m_dispatchStateSize](#m_dispatchstatesize)|Sürüm için kullanılan bu yapının boyutu.|
|[DispatchState::m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|Önceki bağlam eş senkronize olarak engellediği için bu bağlamın yönteme `Dispatch` girip girmediğini söyler. Bu yalnızca UMS zamanlama bağlamında kullanılır ve diğer tüm `0` yürütme bağlamları için değere ayarlanır.|
|[DispatchState::m_reserved](#m_reserved)|Gelecekteki bilgi geçişi için ayrılmış bitler.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`DispatchState`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm.h

**Ad alanı:** eşzamanlılık

## <a name="dispatchstatedispatchstate-constructor"></a><a name="ctor"></a>DispatchState::DispatchState Yapıcı

Yeni `DispatchState` bir nesne oluşturuyor.

```cpp
DispatchState();
```

## <a name="dispatchstatem_dispatchstatesize-data-member"></a><a name="m_dispatchstatesize"></a>DispatchState::m_dispatchStateSize Veri Üyesi

Sürüm için kullanılan bu yapının boyutu.

```cpp
unsigned long m_dispatchStateSize;
```

## <a name="dispatchstatem_fispreviouscontextasynchronouslyblocked-data-member"></a><a name="m_fispreviouscontextasynchronouslyblocked"></a>DispatchState::m_fIsPreviousContextAsynchronouslyBlocked Veri Üyesi

Önceki bağlam eş senkronize olarak engellediği için bu bağlamın yönteme `Dispatch` girip girmediğini söyler. Bu yalnızca UMS zamanlama bağlamında kullanılır ve diğer tüm `0` yürütme bağlamları için değere ayarlanır.

```cpp
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

## <a name="dispatchstatem_reserved-data-member"></a><a name="m_reserved"></a>DispatchState::m_reserved Veri Üyesi

Gelecekteki bilgi geçişi için ayrılmış bitler.

```cpp
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)
