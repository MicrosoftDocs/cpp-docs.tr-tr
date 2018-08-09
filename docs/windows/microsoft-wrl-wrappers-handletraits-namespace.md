---
title: Microsoft::WRL::Wrappers::HandleTraits Namespace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
dev_langs:
- C++
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c83b921aabeee34b583c8f771190ecf60edccb59
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015817"
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
|[CriticalSectionTraits Yapısı](../windows/criticalsectiontraits-structure.md)|Uzmanlaşmış bir `CriticalSection` geçersiz bir kritik bölüm veya kritik bir bölüm serbest bırakmak için bir işlevi desteklemek için nesne.|  
|[EventTraits Yapısı](../windows/eventtraits-structure.md)|Özelliklerini tanımlayan bir `Event` sınıfı işleyici.|  
|[FileHandleTraits Yapısı](../windows/filehandletraits-structure.md)|Bir dosya tanıtıcısı özelliklerini tanımlar.|  
|[HANDLENullTraits Yapısı](../windows/handlenulltraits-structure.md)|Başlatılmamış bir tanıtıcı genel özelliklerini tanımlar.|  
|[HANDLETraits Yapısı](../windows/handletraits-structure.md)|Bir tanıtıcı genel özelliklerini tanımlar.|  
|[MutexTraits Yapısı](../windows/mutextraits-structure.md)|Ortak özelliklerini tanımlayan [Mutex](../windows/mutex-class1.md) sınıfı.|  
|[SemaphoreTraits Yapısı](../windows/semaphoretraits-structure.md)|Semafor nesne genel özelliklerini tanımlar.|  
|[SRWLockExclusiveTraits Yapısı](../windows/srwlockexclusivetraits-structure.md)|Genel özelliklerini açıklayan `SRWLock` sınıfında özel bir kilit modu.|  
|[SRWLockSharedTraits Yapısı](../windows/srwlocksharedtraits-structure.md)|Genel özelliklerini açıklayan `SRWLock` paylaşılan kilit modu sınıfta.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)