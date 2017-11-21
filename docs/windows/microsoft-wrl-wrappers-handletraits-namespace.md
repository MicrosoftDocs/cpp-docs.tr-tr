---
title: Microsoft::WRL::Wrappers::HandleTraits Namespace | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits
dev_langs: C++
helpviewer_keywords: HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3369f7b9264c7b0fd0bfbb9f137278a9f53848d1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|[CriticalSectionTraits yapısı](../windows/criticalsectiontraits-structure.md)|Uzmanlaşmış bir `CriticalSection` geçersiz bir kritik bölüm veya önemli bir bölümü serbest bırakmak için bir işlev desteklemek için nesne.|  
|[EventTraits yapısı](../windows/eventtraits-structure.md)|Özelliklerini tanımlayan bir `Event` sınıfı işleyici.|  
|[FileHandleTraits yapısı](../windows/filehandletraits-structure.md)|Bir dosya tanıtıcısı özelliklerini tanımlar.|  
|[HANDLENullTraits yapısı](../windows/handlenulltraits-structure.md)|Başlatılmamış bir tanıtıcı genel özelliklerini tanımlar.|  
|[HANDLETraits yapısı](../windows/handletraits-structure.md)|Bir tanıtıcı genel özelliklerini tanımlar.|  
|[MutexTraits yapısı](../windows/mutextraits-structure.md)|Ortak özelliklerini tanımlayan [Mutex](../windows/mutex-class1.md) sınıfı.|  
|[SemaphoreTraits yapısı](../windows/semaphoretraits-structure.md)|Semafor nesnesinin ortak özelliklerini tanımlar.|  
|[SRWLockExclusiveTraits yapısı](../windows/srwlockexclusivetraits-structure.md)|Genel özelliklerini açıklayan `SRWLock` özel kullanım kilidi modu sınıfta.|  
|[SRWLockSharedTraits yapısı](../windows/srwlocksharedtraits-structure.md)|Genel özelliklerini açıklayan `SRWLock` paylaşılan kilit modu sınıfta.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: Wrappers Namespace](../windows/microsoft-wrl-wrappers-namespace.md)