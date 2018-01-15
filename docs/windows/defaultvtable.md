---
title: defaultvtable | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.defaultvtable
dev_langs: C++
helpviewer_keywords: defaultvtable attribute
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 90c3fb3d72d71f4d61aebcef657b71bfaff87efd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="defaultvtable"></a>defaultvtable
Bir COM nesnesi için varsayılan vtable arabirimi olarak bir arabirim tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ defaultvtable(  
   interface  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `interface`  
 COM nesne için varsayılan vtable olmasını istediğiniz belirlenen arabirimi.  
  
## <a name="remarks"></a>Açıklamalar  
 **Defaultvtable** C++ özniteliğine sahip ile aynı işlevselliği [defaultvtable](http://msdn.microsoft.com/library/windows/desktop/aa366795) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod öznitelikleri kullanan bir sınıfı gösterir **defaultvtable** varsayılan arabirim belirlemek için:  
  
```  
// cpp_attr_ref_defaultvtable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI1 {  
   HRESULT x();  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface IMyI2 {  
   HRESULT x();  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000003")]  
__interface IMyI3 {  
   HRESULT x();  
};  
  
[coclass, source(IMyI3, IMyI1), default(IMyI3, IMyI2), defaultvtable(IMyI1),  
uuid("00000000-0000-0000-0000-000000000004")]  
class CMyC3 : public IMyI3 {};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**,`struct`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|**coclass**|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Sınıf Öznitelikleri](../windows/class-attributes.md)   
