---
title: requires_category | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.requires_category
dev_langs:
- C++
helpviewer_keywords:
- requires_category attribute
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9ddcfe01ec5bd838a84ddad351f43802a8142b44
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606107"
---
# <a name="requirescategory"></a>requires_category
Hedef sınıfın gerekli bileşen kategorilerini belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[ requires_category(   
  requires_category  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *requires_category*  
 Gerekli bir kategori kimliği.  
  
## <a name="remarks"></a>Açıklamalar  
 **Requires_category** C++ özniteliği hedef sınıfı tarafından gerekli bileşen kategorileri belirtir. Daha fazla bilgi için [REQUIRED_CATEGORY](../atl/reference/category-macros.md#required_category).  
  
 Bu öznitelik gerektiren [coclass'ı](../windows/coclass.md), [ProgID](../windows/progid.md), veya [vi_progid](../windows/vi-progid.md) özniteliği (ya da bunlardan birini anlamına gelir. başka bir öznitelik) da uygulanabilir aynı öğeye.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, nesneyi Denetim kategorisi uygulamak gerektirir.  
  
```cpp  
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
|**İçin geçerlidir**|**sınıf**, **yapısı**|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Bir veya daha fazlasını: `coclass`, `progid`, veya `vi_progid`.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM öznitelikleri](../windows/com-attributes.md)   
 [implements_category](../windows/implements-category.md)   