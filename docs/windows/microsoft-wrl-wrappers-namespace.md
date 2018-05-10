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
ms.openlocfilehash: fa666c1a5de2962a4479b355966c1e8282f2989b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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
|[CriticalSection Sınıfı](../windows/criticalsection-class.md)|Kritik bölüm nesneyi temsil eder.|  
|[Olay Sınıfı (Windows Çalışma Zamanı C++ Şablon Kitaplığı)](../windows/event-class-windows-runtime-cpp-template-library.md)|Bir olayı temsil eder.|  
|[HandleT Sınıfı](../windows/handlet-class.md)|Bir tanıtıcı nesneyi temsil eder.|  
|[HString Sınıfı](../windows/hstring-class.md)|HSTRING tanıtıcıları yönlendirmek için destek sağlar.|  
|[HStringReference Sınıfı](../windows/hstringreference-class.md)|Varolan bir dizeden oluşturulmuş bir HSTRING temsil eder.|  
|[Mutex sınıfı](../windows/mutex-class1.md)|Paylaşılan bir kaynak yalnızca denetleyen eşitleme nesnesi temsil eder.|  
|[RoInitializeWrapper Sınıfı](../windows/roinitializewrapper-class.md)|Windows çalışma zamanı başlatır.|  
|[Semafor Sınıfı](../windows/semaphore-class.md)|Kullanıcılar, sınırlı sayıda destekleyebilir paylaşılan bir kaynak denetleyen eşitleme nesnesi temsil eder.|  
|[SRWLock Sınıfı](../windows/srwlock-class.md)|Bir ince Okuyucu/Yazıcı kilidi temsil eder.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)