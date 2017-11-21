---
title: 'Microsoft::wrl:: Wrappers Namespace | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers
dev_langs: C++
helpviewer_keywords: Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7390f68d7bc7c7856d1fef35ba1fb180b8341559
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="microsoftwrlwrappers-namespace"></a>Microsoft::WRL::Wrappers Ad Alanı
Nesneleri, dizeleri ve tanıtıcıları ömür yönetimini basitleştirmeye kaynak edinme olan başlatma (RAII) sarmalayıcı türlerini tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
|[CriticalSection sınıfı](../windows/criticalsection-class.md)|Kritik bölüm nesneyi temsil eder.|  
|[Olay sınıfı (Windows çalışma zamanı C++ Şablon kitaplığı)](../windows/event-class-windows-runtime-cpp-template-library.md)|Bir olayı temsil eder.|  
|[HandleT sınıfı](../windows/handlet-class.md)|Bir tanıtıcı nesneyi temsil eder.|  
|[HString sınıfı](../windows/hstring-class.md)|HSTRING tanıtıcıları yönlendirmek için destek sağlar.|  
|[HStringReference sınıfı](../windows/hstringreference-class.md)|Varolan bir dizeden oluşturulmuş bir HSTRING temsil eder.|  
|[Mutex sınıfı](../windows/mutex-class1.md)|Paylaşılan bir kaynak yalnızca denetleyen eşitleme nesnesi temsil eder.|  
|[Roınitializewrapper sınıfı](../windows/roinitializewrapper-class.md)|Windows çalışma zamanı başlatır.|  
|[Semafor sınıfı](../windows/semaphore-class.md)|Kullanıcılar, sınırlı sayıda destekleyebilir paylaşılan bir kaynak denetleyen eşitleme nesnesi temsil eder.|  
|[SRWLock sınıfı](../windows/srwlock-class.md)|Bir ince Okuyucu/Yazıcı kilidi temsil eder.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)