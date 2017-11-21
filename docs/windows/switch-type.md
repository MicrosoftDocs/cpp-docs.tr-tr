---
title: switch_type | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.switch_type
dev_langs: C++
helpviewer_keywords: switch_type attribute
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 99ec139c1ff10456639249c94451877a18cbbf51
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [dışarı aktarma](../windows/export.md)   
