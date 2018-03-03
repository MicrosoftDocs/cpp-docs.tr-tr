---
title: switch_type | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.switch_type
dev_langs:
- C++
helpviewer_keywords:
- switch_type attribute
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2b41a71483bc26d1a28476f24a47395ccd6b35d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="switchtype"></a>switch_type
Birleşim discriminant kullanılan değişken türünü tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[switch_type(  
type  
}]  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `type`  
 Anahtar türü tamsayı, karakter, Boole veya numaralandırma türü olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 **Switch_type** C++ özniteliğine sahip ile aynı işlevselliği [switch_type](http://msdn.microsoft.com/library/windows/desktop/aa367276) MIDL özniteliği.  
  
 C++ öznitelikleri desteklemez [birleşimler kapsüllenmiş](http://msdn.microsoft.com/library/windows/desktop/aa366811). [Nonencapsulated birleşimler](http://msdn.microsoft.com/library/windows/desktop/aa367119) yalnızca şu biçimde desteklenir:  
  
```  
// cpp_attr_ref_switch_type.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLibrary")];  
[ export ]  
struct SizedValue2 {  
   [switch_type("char"), switch_is(kind)] union {  
      [case(1), string]  
         wchar_t* wval;  
      [default, string]  
         char* val;  
   };  
   char kind;  
};  
```  
  
## <a name="example"></a>Örnek  
 Bkz: [durum](../windows/case-cpp.md) bir örnek kullanımı, örneğin **switch_type**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|`typedef`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [export](../windows/export.md)   
