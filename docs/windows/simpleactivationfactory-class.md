---
title: SimpleActivationFactory sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- SimpleActivationFactory class
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97ad430bc0ab5a268ff428189da5987b6c45907d
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650797"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory Sınıfı
Bir Windows çalışma zamanı veya klasik COM temel sınıfı oluşturmak için temel bir mekanizma sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Base>  
class SimpleActivationFactory : public ActivationFactory<>;  
```  
  
### <a name="parameters"></a>Parametreler  
 *temel*  
 Temel sınıf.  
  
## <a name="remarks"></a>Açıklamalar  
 Temel sınıfın varsayılan bir oluşturucu sağlamanız gerekir.  
  
 Aşağıdaki kod örneği ile SimpleActivationFactory kullanımı gösterilmiştir [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) makrosu.  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SimpleActivationFactory::ActivateInstance Metodu](../windows/simpleactivationfactory-activateinstance-method.md)|Belirtilen arabirim bir örneğini oluşturur.|  
|[SimpleActivationFactory::GetRuntimeClassName Metodu](../windows/simpleactivationfactory-getruntimeclassname-method.md)|Çalışma zamanı sınıf adı tarafından belirtilen sınıfın örneğini alır *temel* sınıfı şablon parametresi.|  
|[SimpleActivationFactory::GetTrustLevel Metodu](../windows/simpleactivationfactory-gettrustlevel-method.md)|Tarafından belirtilen sınıfın bir örneği güven düzeyini alır *temel* sınıfı şablon parametresi.|  
  
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