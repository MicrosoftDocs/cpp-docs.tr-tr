---
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
ms.openlocfilehash: 9bc4071e5699610a664cbf01ca3e7d36d7effc5e
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54334954"
---
# <a name="mutextraits-structure"></a>MutexTraits Yapısı

Ortak özelliklerini tanımlayan [Mutex](mutex-class.md) sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
struct MutexTraits : HANDLENullTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

Ad                           | Açıklama
------------------------------ | ------------------------------------------------
[MutexTraits::Unlock](#unlock) | Paylaşılan bir kaynağa özel denetimin serbest bırakır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HANDLENullTraits`

`MutexTraits`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="unlock"></a>MutexTraits::Unlock yöntemi

Paylaşılan bir kaynağa özel denetimin serbest bırakır.

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Mutex nesnesi için işler.
