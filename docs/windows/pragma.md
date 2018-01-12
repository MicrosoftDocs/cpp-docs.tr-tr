---
title: pragma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.pragma
dev_langs: C++
helpviewer_keywords: pragma attribute
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 36016ae4af32ead520c8d9919840d267e9d46211
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="pragma"></a>pragması
Belirtilen dize tırnak işaretleri kullanılmadan oluşturulmuş .idl dosyasına yayar. biçimindeki telefon numarasıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ pragma(  
   pragma_statement  
) ];  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pragma_statement*  
 Oluşturulan .idl dosyasına gitmek istiyorsanız pragması.  
  
## <a name="remarks"></a>Açıklamalar  
 **Pragma** C++ özniteliğine sahip ile aynı işlevselliği [pragma](http://msdn.microsoft.com/library/windows/desktop/aa367143) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
  
```  
// cpp_attr_ref_pragma.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
[pragma(pack(4))];  
  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface A  
{  
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);  
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
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Tek başına öznitelikler](../windows/stand-alone-attributes.md)   
 [pack](../preprocessor/pack.md)   
