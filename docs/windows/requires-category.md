---
title: requires_category | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.requires_category
dev_langs: C++
helpviewer_keywords: requires_category attribute
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 677e3c94a5db69dafb66a5cd33749c129cb35afb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="requirescategory"></a>requires_category
Hedef sınıf gerekli bir bileşen kategorilerini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
     [ requires_category(   
  requires_category  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *requires_category*  
 Gerekli Kategori Kimliği.  
  
## <a name="remarks"></a>Açıklamalar  
 **Requires_category** C++ özniteliği, hedef sınıf tarafından gerekli bileşen kategorileri belirtir. Daha fazla bilgi için bkz: [REQUIRED_CATEGORY](../atl/reference/category-macros.md#required_category).  
  
 Bu öznitelik gerektiren [coclass](../windows/coclass.md), [ProgID](../windows/progid.md), veya [vi_progid](../windows/vi-progid.md) özniteliği (veya bunlardan birini gelir başka bir öznitelik) de uygulanması aynı öğeye.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, nesne denetim kategorisi uygulamak gerektirir.  
  
```  
// cpp_attr_ref_requires_category.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="MyLibrary")];  
  
[ coclass, requires_category("CATID_Control"),  
  uuid("1e1a2436-f3ea-4ff3-80bf-5409370e8144")]  
class CMyClass {};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**,`struct`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Bir veya daha fazlasını: **coclass**, **ProgID**, veya **vi_progid**.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM öznitelikleri](../windows/com-attributes.md)   
 [implements_category](../windows/implements-category.md)   
