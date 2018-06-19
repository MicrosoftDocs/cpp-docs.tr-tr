---
title: görüntüleme arabirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.dispinterface
dev_langs:
- C++
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 10f398e83650dc63c002801ac999816e48f7bdd4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874294"
---
# <a name="dispinterface"></a>dispinterface
Arabirim dağıtma arabirimi .idl dosyasına yerleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[dispinterface]  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Zaman **görüntüleme arabirimi** C++ öznitelik önündeki bir arabirim, oluşturulan .idl dosyasındaki kitaplığı bloğunun yerleştirilecek arabirimi neden olur.  
  
 Bir taban sınıfı belirtin sürece dağıtma arabirimi öğesinden türetilen `IDispatch`. Belirtmeniz gerekir bir [kimliği](../windows/id.md) dağıtma arabirimi üyeleri için.  
  
 Kullanım örneğin [görüntüleme arabirimi](http://msdn.microsoft.com/library/windows/desktop/aa366802) MIDL belgelerinde:  
  
```  
dispinterface helloPro   
   { interface hello; };   
```  
  
 için geçerli değil **görüntüleme arabirimi** özniteliği.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [bağlanabilirse](../windows/bindable.md) nasıl kullanılacağına ilişkin bir örnek **görüntüleme arabirimi**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|`interface`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|**çift**, **nesne**, **oleautomation**, `local`, **ms_union**|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Kullanıma göre öznitelikler](../windows/attributes-by-usage.md)   
 [UUID](../windows/uuid-cpp-attributes.md)   
 [Çift](../windows/dual.md)   
 [Özel](../windows/custom-cpp.md)   
 [Nesne](../windows/object-cpp.md)   
 [__interface](../cpp/interface.md)   
