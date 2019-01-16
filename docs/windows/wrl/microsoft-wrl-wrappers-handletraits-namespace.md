---
title: Microsoft::WRL::Wrappers::HandleTraits Ad Alanı
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
ms.openlocfilehash: 55e1dfea2d4075a5a37b9654a70e9ce74383ea53
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54334992"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits Ad Alanı

Genel işleyici tabanlı kaynak türleri özelliklerini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
namespace Microsoft::WRL::Wrappers::HandleTraits;
```

## <a name="members"></a>Üyeler

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[CriticalSectionTraits Yapısı](criticalsectiontraits-structure.md)|Uzmanlaşmış bir `CriticalSection` geçersiz bir kritik bölüm veya kritik bir bölüm serbest bırakmak için bir işlevi desteklemek için nesne.|
|[EventTraits Yapısı](eventtraits-structure.md)|Özelliklerini tanımlayan bir `Event` sınıfı işleyici.|
|[FileHandleTraits Yapısı](filehandletraits-structure.md)|Bir dosya tanıtıcısı özelliklerini tanımlar.|
|[HANDLENullTraits Yapısı](handlenulltraits-structure.md)|Başlatılmamış bir tanıtıcı genel özelliklerini tanımlar.|
|[HANDLETraits Yapısı](handletraits-structure.md)|Bir tanıtıcı genel özelliklerini tanımlar.|
|[MutexTraits Yapısı](mutextraits-structure.md)|Ortak özelliklerini tanımlayan [Mutex](mutex-class.md) sınıfı.|
|[SemaphoreTraits Yapısı](semaphoretraits-structure.md)|Semafor nesne genel özelliklerini tanımlar.|
|[SRWLockExclusiveTraits Yapısı](srwlockexclusivetraits-structure.md)|Genel özelliklerini açıklayan `SRWLock` sınıfında özel bir kilit modu.|
|[SRWLockSharedTraits Yapısı](srwlocksharedtraits-structure.md)|Genel özelliklerini açıklayan `SRWLock` paylaşılan kilit modu sınıfta.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Wrappers Ad Alanı](microsoft-wrl-wrappers-namespace.md)