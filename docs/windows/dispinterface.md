---
title: "görüntüleme arabirimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.dispinterface
dev_langs: C++
helpviewer_keywords: dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf7fb54b4059bc56aea967f03b9e4c2874f84e82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [çift](../windows/dual.md)   
 [Özel](../windows/custom-cpp.md)   
 [Nesne](../windows/object-cpp.md)   
 [__interface](../cpp/interface.md)   
