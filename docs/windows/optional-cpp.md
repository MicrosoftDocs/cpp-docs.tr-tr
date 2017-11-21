---
title: "İsteğe bağlı (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.optional
dev_langs: C++
helpviewer_keywords: optional attribute
ms.assetid: 86656a66-8e11-4589-8e30-9b0f34eeed03
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fb1ae05d7b674f3f1d2c984792bb2bd53dd3de30
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Parametre öznitelikleri](../windows/parameter-attributes.md)   
