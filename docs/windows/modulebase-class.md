---
title: "ModuleBase sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::ModuleBase
dev_langs: C++
helpviewer_keywords: ModuleBase class
ms.assetid: edce7591-6893-46f7-94a7-382827775548
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b02efe3ee61234b2439c1cbbae07827d6a879b2a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="modulebase-class"></a>ModuleBase Sınıfı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class ModuleBase;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Temel sınıfını temsil eden [Modülü](../windows/module-class.md) sınıfları.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ModuleBase::ModuleBase Oluşturucusu](../windows/modulebase-modulebase-constructor.md)|Modül sınıfının bir örneğini başlatır.|  
|[ModuleBase::~ModuleBase Yıkıcısı](../windows/modulebase-tilde-modulebase-destructor.md)|Modül sınıfının geçerli örneği deinitializes.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ModuleBase::DecrementObjectCount Metodu](../windows/modulebase-decrementobjectcount-method.md)|Uygulandığında, azaltır nesnelerin sayısı modül tarafından izlenir.|  
|[ModuleBase::IncrementObjectCount Metodu](../windows/modulebase-incrementobjectcount-method.md)|Uygulandığında modül tarafından izlenen nesne sayısını artırır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ModuleBase`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)