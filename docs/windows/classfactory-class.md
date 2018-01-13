---
title: "ClassFactory sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::ClassFactory
dev_langs: C++
helpviewer_keywords: ClassFactory class
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8c37c016809d31fcb072f23768e9f54313331016
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="classfactory-class"></a>ClassFactory Sınıfı
IClassFactory arabiriminin temel işlevlerini uygular.  
  
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
 `I0`  
 Sıfırıncı arabirimi.  
  
 `I1`  
 İlk arabirimi.  
  
 `I2`  
 İkinci arabirim.  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanan `ClassFactory` kullanıcı tanımlı Üreteç uygulaması sağlamak için.  
  
 Aşağıdaki programlama düzeni nasıl kullanılacağı gösterilmektedir [uygulayan](../windows/implements-structure.md) yapısı bir üreteci üçten fazla arabirimleri belirtin.  
  
 `struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ClassFactory::ClassFactory Oluşturucusu](../windows/classfactory-classfactory-constructor.md)||  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ClassFactory::AddRef Metodu](../windows/classfactory-addref-method.md)|Geçerli ClassFactory nesne başvurusu sayısını artırır.|  
|[ClassFactory::LockServer Metodu](../windows/classfactory-lockserver-method.md)|Arka plandaki sayısı geçerli ClassFactory nesne tarafından izlenen nesneleri artırır veya azaltır.|  
|[ClassFactory::QueryInterface Metodu](../windows/classfactory-queryinterface-method.md)|Parametresi tarafından belirtilen arabirimi için bir işaretçi alır.|  
|[ClassFactory::Release Metodu](../windows/classfactory-release-method.md)|Başvuru sayısı için geçerli ClassFactory nesnesi azaltır.|  
  
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