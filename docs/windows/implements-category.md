---
title: implements_category | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.implements_category
dev_langs:
- C++
helpviewer_keywords:
- implements_category attribute
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6ab6206851385dcf7bf73cf56730093e7fc5c48f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="implementscategory"></a>implements_category
Hedef sınıf tarafından uygulanan bileşen kategorileri belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ implements_category(  
   implements_category="uuid"  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 **implements_category**  
 Uygulanan kategori kimliği.  
  
## <a name="remarks"></a>Açıklamalar  
 **İmplements_category** C++ özniteliği, hedef sınıf tarafından uygulanan bileşen kategorileri belirtir. Bu kategori eşleme oluşturma ve tarafından belirtilen ayrı girişleri ekleyerek yapılır **implements_category** özniteliği. Daha fazla bilgi için bkz: [bileşen kategorileri ve nasıl yapmak bunlar iş nelerdir?](http://msdn.microsoft.com/library/windows/desktop/ms694322).  
  
 Bu öznitelik gerektiren [coclass](../windows/coclass.md), [ProgID](../windows/progid.md), veya [vi_progid](../windows/vi-progid.md) özniteliği (veya bunlardan birini gelir başka bir öznitelik) de uygulanması aynı öğeye. Herhangi bir tek öznitelik kullanılırsa, diğer iki otomatik olarak uygulanır. Örneğin, varsa **ProgID** uygulanan **vi_progid** ve **coclass** da uygulanır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, aşağıdaki nesne denetim kategorisi uygulayan belirtir.  
  
```  
// cpp_attr_ref_implements_category.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="MyLib")];  
[ coclass, implements_category("CATID_Control"),  
  uuid("20a0d0cc-5172-40f5-99ae-5e032f3205ae")]  
class CMyClass {};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**,`struct`|  
|**Yinelenebilir**|Evet|  
|**Gerekli öznitelikler**|Şunlardan biri: **coclass**, **ProgID**, veya **vi_progid**|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM öznitelikleri](../windows/com-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [IMPLEMENTED_CATEGORY](../atl/reference/category-macros.md#implemented_category)   
 