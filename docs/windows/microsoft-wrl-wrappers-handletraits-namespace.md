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
ms.openlocfilehash: b114d067249e78d7fb935e473cc3cc952c76fe02
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878040"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits Ad Alanı
Özelliklere genel tanıtıcı tabanlı kaynak türleri açıklanmaktadır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
namespace Microsoft::WRL::Wrappers::HandleTraits;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="structures"></a>Yapılar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CriticalSectionTraits Yapısı](../windows/criticalsectiontraits-structure.md)|Uzmanlaşmış bir `CriticalSection` geçersiz bir kritik bölüm veya önemli bir bölümü serbest bırakmak için bir işlev desteklemek için nesne.|  
|[EventTraits Yapısı](../windows/eventtraits-structure.md)|Özelliklerini tanımlayan bir `Event` sınıfı işleyici.|  
|[FileHandleTraits Yapısı](../windows/filehandletraits-structure.md)|Bir dosya tanıtıcısı özelliklerini tanımlar.|  
|[HANDLENullTraits Yapısı](../windows/handlenulltraits-structure.md)|Başlatılmamış bir tanıtıcı genel özelliklerini tanımlar.|  
|[HANDLETraits Yapısı](../windows/handletraits-structure.md)|Bir tanıtıcı genel özelliklerini tanımlar.|  
|[MutexTraits Yapısı](../windows/mutextraits-structure.md)|Ortak özelliklerini tanımlayan [Mutex](../windows/mutex-class1.md) sınıfı.|  
|[SemaphoreTraits Yapısı](../windows/semaphoretraits-structure.md)|Semafor nesnesinin ortak özelliklerini tanımlar.|  
|[SRWLockExclusiveTraits Yapısı](../windows/srwlockexclusivetraits-structure.md)|Genel özelliklerini açıklayan `SRWLock` özel kullanım kilidi modu sınıfta.|  
|[SRWLockSharedTraits Yapısı](../windows/srwlocksharedtraits-structure.md)|Genel özelliklerini açıklayan `SRWLock` paylaşılan kilit modu sınıfta.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)