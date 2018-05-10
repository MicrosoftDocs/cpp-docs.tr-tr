---
title: noncreatable | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.noncreatable
dev_langs:
- C++
helpviewer_keywords:
- noncreatable attribute
ms.assetid: 4d17937b-0bff-41af-ba57-53e18b7ab5a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4055d541fa60c714262a64466734bc2b2323775b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="noncreatable"></a>noncreatable
Tek başına başlatılamaz bir nesneyi tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[noncreatable]  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Noncreatable** C++ özniteliğine sahip ile aynı işlevselliği [noncreatable](http://msdn.microsoft.com/library/windows/desktop/aa367118) MIDL özniteliği ve otomatik olarak oluşturulan geçirilir. IDL derleyicisi dosyasıyla.  
  
 Bu öznitelik, ATL kullanan bir proje içinde kullanıldığında, öznitelik davranışını değiştirir. Yukarıdaki davranışa ek olarak, öznitelik ayrıca yerleştirir [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) makrosu. Bu makrosu nesne dışarıdan oluşturulamıyor için ATL gösterir.  
  
## <a name="example"></a>Örnek  
  
```  
// cpp_attr_ref_noncreatable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("11111111-1111-1111-1111-111111111111")]  
__interface A   
{  
};  
  
[coclass, uuid("11111111-1111-1111-1111-111111111112"), noncreatable]  
class CMyClass : public A   
{  
   HRESULT xx();  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**, `struct`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|**coclass**|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Sınıf Öznitelikleri](../windows/class-attributes.md)   
