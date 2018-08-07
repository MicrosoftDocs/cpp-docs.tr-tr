---
title: ModuleBase sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
dev_langs:
- C++
helpviewer_keywords:
- ModuleBase class
ms.assetid: edce7591-6893-46f7-94a7-382827775548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b298bcab4c2b3547f2b285fe21d4967f4696fb9d
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605064"
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
|[ModuleBase::ModuleBase Oluşturucusu](../windows/modulebase-modulebase-constructor.md)|Bir örneğini başlatır `Module` sınıfı.|  
|[ModuleBase::~ModuleBase Yıkıcısı](../windows/modulebase-tilde-modulebase-destructor.md)|Geçerli örneğinin başlatmasını geri alır `Module` sınıfı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ModuleBase::DecrementObjectCount Metodu](../windows/modulebase-decrementobjectcount-method.md)|Uygulandığında, azaltır nesne sayısını modülü tarafından izlenir.|  
|[ModuleBase::IncrementObjectCount Metodu](../windows/modulebase-incrementobjectcount-method.md)|Uygulandığında, modül tarafından izlenen nesne sayısını artırır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ModuleBase`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)