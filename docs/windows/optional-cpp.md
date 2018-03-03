---
title: "İsteğe bağlı (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.optional
dev_langs:
- C++
helpviewer_keywords:
- optional attribute
ms.assetid: 86656a66-8e11-4589-8e30-9b0f34eeed03
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 028cb0f911ac389e4ad17f54fc16e24f29c8d9db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="optional-c"></a>isteğe bağlı (C++)
Üye işlevi için isteğe bağlı bir parametre belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[optional]  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **İsteğe bağlı** C++ özniteliğine sahip ile aynı işlevselliği [isteğe bağlı](http://msdn.microsoft.com/library/windows/desktop/aa367132) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodda gösterildiği nasıl **isteğe bağlı** kullanılabilir:  
  
```  
// cpp_attr_ref_optional.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl : IDispatch  
{  
   [id(1)] long procedure ([in, optional] VARIANT i);  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Parametre arabirimi|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Parametre Öznitelikleri](../windows/parameter-attributes.md)   
