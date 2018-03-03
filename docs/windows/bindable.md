---
title: "bağlanabilir | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.bindable
dev_langs:
- C++
helpviewer_keywords:
- bindable attribute
ms.assetid: a2360f92-927b-4af8-98cc-6eca7f4ec954
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5266bca832a128242bcbbc8904ad9650e4432fe2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="bindable"></a>bağlanabilir
Özellik veri bağlama desteklediğini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[bindable]  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Bağlanabilirse** C++ özniteliğine sahip ile aynı işlevselliği [bağlanabilirse](http://msdn.microsoft.com/library/windows/desktop/aa366738) MIDL özniteliği. Özellikleri ile tanımlanmış kullanmak [propget](../windows/propget.md), [propput](../windows/propput.md), veya [propputref](../windows/propputref.md) öznitelikleri, veya el ile tanımlayabilirsiniz bağlanabilirse yöntemi.  
  
 Aşağıdaki MFC örnekleri kullanımını göster **bağlanabilirse**:  
  
-   [Denetimleri örnekleri: MFC tabanlı ActiveX denetimleri](http://msdn.microsoft.com/en-us/a44adf86-0ba0-4504-bedb-512b6cba2e63)  
  
-   [DAİ örnek: ActiveX denetimi](http://msdn.microsoft.com/en-us/9ba34d04-280e-49f4-90ae-41a6be44c95b)  
  
-   [TESTHELP örnek: Araç ipuçları ve Yardım ActiveX denetimi](http://msdn.microsoft.com/en-us/d822861d-c6f0-4d0a-ad11-970eebb1e8cd)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod nasıl kullanabileceğinizi gösterir **bağlanabilirse** bir özelliğe:  
  
```  
// cpp_attr_ref_bindable.cpp  
// compile with: /LD  
#include <windows.h>  
[  
   uuid("479B29E3-9A2C-11D0-B696-00A0C903487A"),  
   dispinterface,  
   helpstring("property demo Interface")  
]  
__interface IPropDemo : IDispatch {  
  
   [propget, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([out, retval] long *nSize);  
   [propput, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([in] long nSize);  
   [id(3), bindable, propget] HRESULT Object([out, retval] IDispatch **ppObj);  
   [id(3), bindable, propputref] HRESULT Object([in] IDispatch* pObj);     
   [id(-552), helpstring("method AboutBox")] HRESULT AboutBox();  
};  
  
[ module(name="PropDemoLib", uuid="479B29E2-9A2C-11D0-B696-00A0C903487A", version="1.0", helpstring="property demo") ];  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Arabirim yöntemi|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Yöntem öznitelikleri](../windows/method-attributes.md)   
 [defaultbind](../windows/defaultbind.md)   
 [displaybind](../windows/displaybind.md)   
 [immediatebind](../windows/immediatebind.md)   
 [requestedit](../windows/requestedit.md)   
