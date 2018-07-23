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
ms.openlocfilehash: bfee0c0cd7ff7bd7f4525a291184f08f1e2898e5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878742"
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