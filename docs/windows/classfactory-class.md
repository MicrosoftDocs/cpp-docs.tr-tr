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
ms.openlocfilehash: c9a7caba7ccfb8f5764a1f460835ff540c838975
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641047"
---
# <a name="classfactory-class"></a>ClassFactory Sınıfı
Temel işlevselliğini uygular `IClassFactory` arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
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
  
### <a name="parameters"></a>Parametreler  
 *I0*  
 Sıfırıncı arabirim.  
  
 *I1*  
 İlk arabirim.  
  
 *I2*  
 İkinci arabirim.  
  
## <a name="remarks"></a>Açıklamalar  
 Yazılımınız **ClassFactory** Fabrika kullanıcı tanımlı bir uygulama sağlamak için.  
  
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
|[ClassFactory::AddRef Metodu](../windows/classfactory-addref-method.md)|Geçerli başvuru sayısını artırır **ClassFactory** nesne.|  
|[ClassFactory::LockServer Metodu](../windows/classfactory-lockserver-method.md)|Artırır veya azaltır temel sayısını nesneleri geçerli tarafından izlenen **ClassFactory** nesne.|  
|[ClassFactory::QueryInterface Metodu](../windows/classfactory-queryinterface-method.md)|Parametresi tarafından belirtilen arabirim işaretçisi alır.|  
|[ClassFactory::Release Metodu](../windows/classfactory-release-method.md)|Başvuru için geçerli sayısını azaltır **ClassFactory** nesne.|  
  
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