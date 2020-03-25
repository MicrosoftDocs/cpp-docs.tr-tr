---
title: Microsoft::WRL::Wrappers::HandleTraits Ad Alanı
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
ms.openlocfilehash: b19cc426fc7c1b4fc6ec0638730d59998f8c108a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213739"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits Ad Alanı

Ortak tanıtıcı tabanlı kaynak türlerinin özelliklerini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
namespace Microsoft::WRL::Wrappers::HandleTraits;
```

## <a name="members"></a>Üyeler

### <a name="structures"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[CriticalSectionTraits Yapısı](criticalsectiontraits-structure.md)|, Kritik bir bölümü serbest bırakmak için geçersiz bir kritik bölümü ya da bir işlevi desteklemek üzere bir `CriticalSection` nesnesini uzmanlaşmış hale getirir.|
|[EventTraits Yapısı](eventtraits-structure.md)|`Event` Sınıf tanıtıcısının özelliklerini tanımlar.|
|[FileHandleTraits Yapısı](filehandletraits-structure.md)|Bir dosya tanıtıcısının özelliklerini tanımlar.|
|[HANDLENullTraits Yapısı](handlenulltraits-structure.md)|Başlatılmamış tanıtıcının ortak özelliklerini tanımlar.|
|[HANDLETraits Yapısı](handletraits-structure.md)|Bir tanıtıcının ortak özelliklerini tanımlar.|
|[MutexTraits Yapısı](mutextraits-structure.md)|[Mutex](mutex-class.md) sınıfının ortak özelliklerini tanımlar.|
|[SemaphoreTraits Yapısı](semaphoretraits-structure.md)|Semafor nesnesinin ortak özelliklerini tanımlar.|
|[SRWLockExclusiveTraits Yapısı](srwlockexclusivetraits-structure.md)|Özel kilit modundaki `SRWLock` sınıfının ortak özelliklerini açıklar.|
|[SRWLockSharedTraits Yapısı](srwlocksharedtraits-structure.md)|Paylaşılan kilit modundaki `SRWLock` sınıfının ortak özelliklerini açıklar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Wrappers Ad Alanı](microsoft-wrl-wrappers-namespace.md)
