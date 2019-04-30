---
title: Microsoft::WRL::Wrappers Ad Alanı
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
ms.openlocfilehash: 4b88ad0da31321a696c1238f1c9838d3b3a1c927
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392004"
---
# <a name="microsoftwrlwrappers-namespace"></a>Microsoft::WRL::Wrappers Ad Alanı

Nesneler, dizeler ve tanıtıcıları ömrü yönetimini basitleştirmek kaynak edinme olan başlatma (RAII) sarmalayıcı türlerini tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
namespace Microsoft::WRL::Wrappers;
```

## <a name="members"></a>Üyeler

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`FileHandle`|`HandleT<HandleTraits::FileHandleTraits>`|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[CriticalSection Sınıfı](criticalsection-class.md)|Kritik bölüm nesneyi temsil eder.|
|[Event Sınıfı (WRL)](event-class-wrl.md)|Bir olayı temsil eder.|
|[HandleT Sınıfı](handlet-class.md)|Bir tutamacı nesneyi temsil eder.|
|[HString Sınıfı](hstring-class.md)|HSTRING tutamaçları düzenlenmesi için destek sağlar.|
|[HStringReference Sınıfı](hstringreference-class.md)|Varolan bir dizeden oluşturulan bir HSTRING temsil eder.|
|[Mutex sınıfı](mutex-class.md)|Paylaşılan bir kaynağa özel olarak denetleyen bir eşitleme nesnesi temsil eder.|
|[RoInitializeWrapper Sınıfı](roinitializewrapper-class.md)|Windows çalışma zamanı'nı başlatır.|
|[Semafor Sınıfı](semaphore-class.md)|Sınırlı sayıda kullanıcıları destekleyen bir paylaşılan kaynak denetleyen bir eşitleme nesnesi temsil eder.|
|[SRWLock Sınıfı](srwlock-class.md)|Bir ince Okuyucu/Yazıcı kilidi temsil eder.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)