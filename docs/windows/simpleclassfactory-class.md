---
title: "SimpleClassFactory sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::SimpleClassFactory
dev_langs: C++
helpviewer_keywords: SimpleClassFactory class
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 840862915e90accbab254f5a9003446471608a2a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory Sınıfı
Bir taban sınıf oluşturmak için temel bir mekanizma sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<  
   typename Base  
>  
class SimpleClassFactory : public ClassFactory<>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Base`  
 Bir temel sınıf.  
  
## <a name="remarks"></a>Açıklamalar  
 Taban sınıf, varsayılan bir oluşturucu sağlamanız gerekir.  
  
 Aşağıdaki kod örneğinde SimpleClassFactory ile kullanımı gösterilmiştir [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) makrosu.  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SimpleClassFactory::CreateInstance Metodu](../windows/simpleclassfactory-createinstance-method.md)|Belirtilen arabiriminin bir örneğini oluşturur.|  
  
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