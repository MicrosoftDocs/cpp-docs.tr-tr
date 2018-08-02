---
title: Durum (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.case
dev_langs:
- C++
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6567650d719b56bb320f1b40eae285322bcab364
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464317"
---
# <a name="case-c"></a>durum (C++)
İle kullanılan [switch_type](../windows/switch-type.md) özniteliğini bir **birleşim**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[ case(  
   value  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *value*  
 Olası bir işleme sağlamak istediğiniz değeri girin. Türünü **değer** şu türlerden biri olabilir:  
  
-   `int`  
  
-   `char`  
  
-   `boolean`  
  
-   `enum`  
  
 veya böyle bir türü bir tanımlayıcı.  
  
## <a name="remarks"></a>Açıklamalar  
 **Çalışması** C++ özniteliği ile aynı işlevlere sahip **çalışması** MIDL özniteliği. Bu öznitelik yalnızca birlikte kullanılan [switch_type](../windows/switch-type.md) özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, bir kullanımını göstermektedir. **çalışması** özniteliği:  
  
```cpp  
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
|**İçin geçerlidir**|Üye bir **sınıfı** veya **yapısı**|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Sınıf Öznitelikleri](../windows/class-attributes.md)   