---
description: 'Daha fazla bilgi edinin: Mutexnitelikler yapısı'
title: MutexTraits Yapısı
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock method
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
ms.openlocfilehash: e3dfcee1251794734ed5cf787096361403d80c7f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330833"
---
# <a name="mutextraits-structure"></a>MutexTraits Yapısı

[Mutex](mutex-class.md) sınıfının ortak özelliklerini tanımlar.

## <a name="syntax"></a>Syntax

```cpp
struct MutexTraits : HANDLENullTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

Ad                           | Açıklama
------------------------------ | ------------------------------------------------
[Mutexnitelikler:: unlock](#unlock) | Paylaşılan bir kaynağın dışlamalı denetimini yayınlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HANDLENullTraits`

`MutexTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar:: Handlenitelikler

## <a name="mutextraitsunlock-method"></a><a name="unlock"></a> Mutexnitelikler:: unlock yöntemi

Paylaşılan bir kaynağın dışlamalı denetimini yayınlar.

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Bir mutex nesnesine işleyin.
