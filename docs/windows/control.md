---
title: Denetim | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.control
dev_langs: C++
helpviewer_keywords: Control attribute
ms.assetid: 3d046bb2-4afe-4cb8-a762-233b296e1975
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 00e9ce0a3e310ad9d07f41b0053ed5249a35a339
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="control"></a>denetimi
Kullanıcı tanımlı tür denetim olduğunu belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[control]  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Denetim** özniteliği gelir [coclass](../windows/coclass.md) özniteliği. **Denetim** C++ özniteliğine sahip ile aynı işlevselliği [denetim](http://msdn.microsoft.com/library/windows/desktop/aa366764) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
  
```  
// cpp_attr_ref_control.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="Test", control=true)];  
  
[object, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
};  
  
[coclass, control, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]  
class CTest : public ICustom {};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**,`struct`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [Typedef, Enum, Union ve Struct Öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
