---
title: Microsoft::WRL::Wrappers::HandleTraits Ad Alanı
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
ms.openlocfilehash: 6ed8156b6a0e71d40d1579fc9a33912f698e1773
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030400"
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

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Wrappers Ad Alanı](microsoft-wrl-wrappers-namespace.md)