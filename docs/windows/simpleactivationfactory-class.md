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
ms.openlocfilehash: 2d10544a08fa6faebb1434cd00ca80ac30d4570a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889855"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory Sınıfı
Windows çalışma zamanı veya klasik COM temel sınıf oluşturmak için temel bir mekanizma sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Base>  
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