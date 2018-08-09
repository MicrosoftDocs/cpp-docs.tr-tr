---
title: implements_category | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.implements_category
dev_langs:
- C++
helpviewer_keywords:
- implements_category attribute
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 28df44096f3b61eb4ada17ec824292281edee602
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013720"
---
# <a name="implementscategory"></a>implements_category
Hedef sınıf tarafından uygulanan bileşen kategorilerini belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
[ implements_category(  
   implements_category="uuid"  
) ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *implements_category*  
 Uygulanan kategori kimliği.  
  
## <a name="remarks"></a>Açıklamalar  
 **İmplements_category** C++ özniteliği hedef sınıf tarafından uygulanan bileşen kategorileri belirtir. Bu kategori harita oluşturma ve tarafından belirlenen ayrı girdileri ekleyerek yapılır **implements_category** özniteliği. Daha fazla bilgi için [bileşen kategorileri ve nasıl yapın, iş nedir?](http://msdn.microsoft.com/library/windows/desktop/ms694322).  
  
 Bu öznitelik gerektiren [coclass'ı](../windows/coclass.md), [ProgID](../windows/progid.md), veya [vi_progid](../windows/vi-progid.md) özniteliği (ya da bunlardan birini anlamına gelir. başka bir öznitelik) da uygulanabilir aynı öğeye. Herhangi bir tek öznitelik kullandıysanız, diğer iki otomatik olarak uygulanır. Örneğin, varsa `progid` uygulanan `vi_progid` ve `coclass` de uygulanır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, aşağıdaki uygulayan nesne belirtir `Control` kategorisi.  
  
```cpp  
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
|**İçin geçerlidir**|**sınıf**, **yapısı**|  
|**Tekrarlanabilir**|Evet|  
|**Gerekli öznitelikleri**|Aşağıdakilerden biri: `coclass`, `progid`, veya `vi_progid`|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM öznitelikleri](../windows/com-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [IMPLEMENTED_CATEGORY](../atl/reference/category-macros.md#implemented_category)   