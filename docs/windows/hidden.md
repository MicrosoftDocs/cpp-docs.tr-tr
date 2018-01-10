---
title: Gizli | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.hidden
dev_langs: C++
helpviewer_keywords: hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c038eb4869cb3191dd26b5c4ea8e1c6cc182e366
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="hidden"></a>gizli
Öğe var, ancak kullanıcı odaklı bir tarayıcıda görüntülenmemelidir olduğunu gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[hidden]  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Gizli** C++ özniteliğine sahip ile aynı işlevselliği [gizli](http://msdn.microsoft.com/library/windows/desktop/aa366861) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [bağlanabilirse](../windows/bindable.md) nasıl kullanılacağına ilişkin bir örnek **gizli**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|`interface`, **sınıfı**, `struct`, yöntemi, özelliği|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|**coclass'ı** (uygulandığında **sınıfı** veya `struct`)|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim öznitelikleri](../windows/interface-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [Yöntem Öznitelikleri](../windows/method-attributes.md)   
