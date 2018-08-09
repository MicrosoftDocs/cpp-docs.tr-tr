---
title: SimpleClassFactory sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory
dev_langs:
- C++
helpviewer_keywords:
- SimpleClassFactory class
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c490e21717e44ec3e772c01f84a0f5adb08471fd
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012501"
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory Sınıfı
Bir temel sınıf oluşturmak için temel bir mekanizma sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<typename Base>  
class SimpleClassFactory : public ClassFactory<>;  
```  
  
### <a name="parameters"></a>Parametreler  
 *temel*  
 Temel sınıf.  
  
## <a name="remarks"></a>Açıklamalar  
 Temel sınıfın varsayılan bir oluşturucu sağlamanız gerekir.  
  
 Aşağıdaki kod örneğinde nasıl kullanılacağını gösterir **SimpleClassFactory** ile [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) makrosu.  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SimpleClassFactory::CreateInstance Metodu](../windows/simpleclassfactory-createinstance-method.md)|Belirtilen arabirim bir örneğini oluşturur.|  
  
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
  
 `ClassFactory`  
  
 `SimpleClassFactory`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)