---
title: "SimpleActivationFactory sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- SimpleActivationFactory class
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 991d428e90654fd29cfbb9c5c7e110708a05de01
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory Sınıfı
Windows çalışma zamanı veya klasik COM temel sınıf oluşturmak için temel bir mekanizma sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<  
   typename Base  
>  
class SimpleActivationFactory : public ActivationFactory<>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Base`  
 Bir temel sınıf.  
  
## <a name="remarks"></a>Açıklamalar  
 Taban sınıf, varsayılan bir oluşturucu sağlamanız gerekir.  
  
 Aşağıdaki kod örneğinde SimpleActivationFactory ile kullanımı gösterilmiştir [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) makrosu.  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SimpleActivationFactory::ActivateInstance Metodu](../windows/simpleactivationfactory-activateinstance-method.md)|Belirtilen arabiriminin bir örneğini oluşturur.|  
|[SimpleActivationFactory::GetRuntimeClassName Metodu](../windows/simpleactivationfactory-getruntimeclassname-method.md)|Tarafından belirtilen sınıfının bir örneğini çalışma zamanı sınıf adını alır `Base` sınıfı şablon parametresi.|  
|[SimpleActivationFactory::GetTrustLevel Metodu](../windows/simpleactivationfactory-gettrustlevel-method.md)|Tarafından belirtilen sınıfının bir örneği güven düzeyini alır `Base` sınıfı şablon parametresi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ActivationFactory`  
  
 `SimpleActivationFactory`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)