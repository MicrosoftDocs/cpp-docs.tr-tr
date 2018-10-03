---
title: 'Microsoft::wrl:: Wrappers Namespace | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
dev_langs:
- C++
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2b1a63494e06ce3117e7e8fccd1d0cbca8cdb4d0
ms.sourcegitcommit: d1527eb2d50156bf923f2a32ec3af9efc7fc4304
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48250347"
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
|[CriticalSection Sınıfı](../windows/criticalsection-class.md)|Kritik bölüm nesneyi temsil eder.|
|[Olay sınıfı (WRL)](../windows/event-class-wrl.md)|Bir olayı temsil eder.|
|[HandleT Sınıfı](../windows/handlet-class.md)|Bir tutamacı nesneyi temsil eder.|
|[HString Sınıfı](../windows/hstring-class.md)|HSTRING tutamaçları düzenlenmesi için destek sağlar.|
|[HStringReference Sınıfı](../windows/hstringreference-class.md)|Varolan bir dizeden oluşturulan bir HSTRING temsil eder.|
|[Mutex sınıfı](../windows/mutex-class.md)|Paylaşılan bir kaynağa özel olarak denetleyen bir eşitleme nesnesi temsil eder.|
|[RoInitializeWrapper Sınıfı](../windows/roinitializewrapper-class.md)|Windows çalışma zamanı'nı başlatır.|
|[Semafor Sınıfı](../windows/semaphore-class.md)|Sınırlı sayıda kullanıcıları destekleyen bir paylaşılan kaynak denetleyen bir eşitleme nesnesi temsil eder.|
|[SRWLock Sınıfı](../windows/srwlock-class.md)|Bir ince Okuyucu/Yazıcı kilidi temsil eder.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)