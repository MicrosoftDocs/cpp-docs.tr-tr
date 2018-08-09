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
ms.openlocfilehash: 9667a3660f46db0a61991545108d66bf0cac9f38
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017802"
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
|[Olay Sınıfı (Windows Çalışma Zamanı C++ Şablon Kitaplığı)](../windows/event-class-windows-runtime-cpp-template-library.md)|Bir olayı temsil eder.|  
|[HandleT Sınıfı](../windows/handlet-class.md)|Bir tutamacı nesneyi temsil eder.|  
|[HString Sınıfı](../windows/hstring-class.md)|HSTRING tutamaçları düzenlenmesi için destek sağlar.|  
|[HStringReference Sınıfı](../windows/hstringreference-class.md)|Varolan bir dizeden oluşturulan bir HSTRING temsil eder.|  
|[Mutex sınıfı](../windows/mutex-class1.md)|Paylaşılan bir kaynağa özel olarak denetleyen bir eşitleme nesnesi temsil eder.|  
|[RoInitializeWrapper Sınıfı](../windows/roinitializewrapper-class.md)|Windows çalışma zamanı'nı başlatır.|  
|[Semafor Sınıfı](../windows/semaphore-class.md)|Sınırlı sayıda kullanıcıları destekleyen bir paylaşılan kaynak denetleyen bir eşitleme nesnesi temsil eder.|  
|[SRWLock Sınıfı](../windows/srwlock-class.md)|Bir ince Okuyucu/Yazıcı kilidi temsil eder.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)