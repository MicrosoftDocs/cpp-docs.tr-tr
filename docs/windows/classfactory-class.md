---
title: ClassFactory sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory
dev_langs:
- C++
helpviewer_keywords:
- ClassFactory class
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97c07b5cf97578c49da9d4a72b5a232b559ec0ab
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463872"
---
# <a name="classfactory-class"></a>ClassFactory Sınıfı
Temel işlevselliğini uygular `IClassFactory` arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ClassFactory : public Details::RuntimeClass<  
   typename Details::InterfaceListHelper<IClassFactory,   
   I0,   
   I1,   
   I2,   
   Details::Nil>::TypeT,   
   RuntimeClassFlags<ClassicCom | InhibitWeakReference>,   
      false>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *I0*  
 Sıfırıncı arabirim.  
  
 *I1*  
 İlk arabirim.  
  
 *I2*  
 İkinci arabirim.  
  
## <a name="remarks"></a>Açıklamalar  
 Yazılımınız `ClassFactory` Fabrika kullanıcı tanımlı bir uygulama sağlamak için.  
  
 Aşağıdaki programlama deseni nasıl kullanılacağını gösteren [uygular](../windows/implements-structure.md) yapısı üzerinde bir sınıf üreteci üçten fazla arabirimleri belirtin.  
  
 `struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ClassFactory::ClassFactory Oluşturucusu](../windows/classfactory-classfactory-constructor.md)||  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ClassFactory::AddRef Metodu](../windows/classfactory-addref-method.md)|Geçerli ClassFactory nesneye başvuru sayısını artırır.|  
|[ClassFactory::LockServer Metodu](../windows/classfactory-lockserver-method.md)|Temel alınan sayısı geçerli ClassFactory nesne tarafından izlenen nesneleri artırır veya azaltır.|  
|[ClassFactory::QueryInterface Metodu](../windows/classfactory-queryinterface-method.md)|Parametresi tarafından belirtilen arabirim işaretçisi alır.|  
|[ClassFactory::Release Metodu](../windows/classfactory-release-method.md)|Geçerli ClassFactory nesne için başvuru sayısını azaltır.|  
  
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
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)   
 [RuntimeClassType Sabit Listesi](../windows/runtimeclasstype-enumeration.md)