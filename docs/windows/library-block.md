---
title: library_block | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.library_block
dev_langs: C++
helpviewer_keywords: library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4e0255002a8235f4e8a36d4b43df520d6e26865b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="libraryblock"></a>library_block
IDL kitaplığı bloktaki bir yapı yerleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[library_block]  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kitaplık bloktaki bir yapı yerleştirdiğinizde, olup başvurulan bağımsız olarak türü kitaplığa geçirilir emin olun. Varsayılan olarak, yalnızca yapıları değiştiren tarafından [coclass](../windows/coclass.md), [görüntüleme arabirimi](../windows/dispinterface.md), ve [idl_module](../windows/idl-module.md) öznitelikleri kitaplığı bloğunda yerleştirilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodda özel bir arabirim kitaplığı bloğunun içine yerleştirilir.  
  
```  
// cpp_attr_ref_library_block.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib")];  
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface IMyInterface {  
   HRESULT f1();  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Her yerden|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici öznitelikleri](../windows/compiler-attributes.md)   
 [Tek başına öznitelikler](../windows/stand-alone-attributes.md)   
