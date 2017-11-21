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
ms.openlocfilehash: fe24bd4995acb7a36f6aa50378a03b519c8d8e3e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|[ModuleBase:: ~ ModuleBase yok Edicisi](../windows/modulebase-tilde-modulebase-destructor.md)|Modül sınıfının geçerli örneği deinitializes.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ModuleBase::DecrementObjectCount yöntemi](../windows/modulebase-decrementobjectcount-method.md)|Uygulandığında, azaltır nesnelerin sayısı modül tarafından izlenir.|  
|[Modulebase::ıncrementobjectcount yöntemi](../windows/modulebase-incrementobjectcount-method.md)|Uygulandığında modül tarafından izlenen nesne sayısını artırır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ModuleBase`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)