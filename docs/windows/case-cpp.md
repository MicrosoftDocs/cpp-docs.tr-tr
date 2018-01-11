---
title: Durum (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.case
dev_langs: C++
helpviewer_keywords: case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: adacffa4dbce4cc908c393cb5019375234e9ff85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="case-c"></a>durum (C++)
İle kullanılan [switch_type](../windows/switch-type.md) özniteliğini bir **UNION**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ case(  
   value  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *value*  
 Olası işleme sağlamak istediğiniz değeri girin. Türü **değeri** aşağıdaki türlerden biri olabilir:  
  
-   `int`  
  
-   `char`  
  
-   `boolean`  
  
-   `enum`  
  
 ya da böyle bir türde bir tanımlayıcı.  
  
## <a name="remarks"></a>Açıklamalar  
 **Durum** C++ özniteliğine sahip ile aynı işlevselliği **durumda** MIDL özniteliği. Bu öznitelik yalnızca ile kullanılan [switch_type](../windows/switch-type.md) özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod bir kullanımını gösterir **durumda** özniteliği:  
  
```  
// cpp_attr_ref_case.cpp  
// compile with: /LD  
#include <unknwn.h>  
[export]  
struct SizedValue2 {  
   [switch_type(char), switch_is(kind)] union {  
      [case(1), string]  
          wchar_t* wval;  
      [default, string]  
          char* val;  
   };  
    char kind;  
};  
[module(name="ATLFIRELib")];  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Üye bir **sınıfı** veya`struct`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Sınıf Öznitelikleri](../windows/class-attributes.md)   
