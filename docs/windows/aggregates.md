---
title: Toplamalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.aggregates
dev_langs:
- C++
helpviewer_keywords:
- aggregates attribute
- aggregation [C++]
- aggregate objects [C++], aggregates attribute
- aggregates [C++]
ms.assetid: 67a084c9-941f-474b-a029-9c93b38ebe9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 19dea3b078f894931002d186b20c1ffb85bb763b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857993"
---
# <a name="aggregates"></a>toplamlar
Nesne tarafından CLSID belirtilen nesne toplayan gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ aggregates(  
   clsid,  
   variable_name  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `clsid`  
 Toplanabilir nesnesinin CLSID belirtir.  
  
 `variable_name`  
 Eklenecek değişkeninin adı. Bu değişken içeriyor **IUnknown** toplanan nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir nesneye uygulandığında **toplamalar** C++ öznitelik uygulayan bir dış sarmalayıcı toplanan nesnesi için (tarafından belirtilen `clsid`).  
  
 Bu öznitelik gerektiren [coclass](../windows/coclass.md), [ProgID](../windows/progid.md), veya [vi_progid](../windows/vi-progid.md) özniteliği (veya bunlardan birini gelir başka bir öznitelik) de uygulanması aynı öğeye. Herhangi bir tek öznitelik kullanılırsa, diğer iki otomatik olarak uygulanır. Örneğin, varsa **ProgID** uygulanan **vi_progid** ve **coclass** da uygulanır.  
  
 **ATL projeleri**  
  
 Bu öznitelik, ATL kullanan bir proje içinde kullanılıyorsa, öznitelik davranışını değiştirir. İlk olarak, aşağıdaki girdi hedef nesnenin COM eşlemesi eklenir:  
  
```  
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(_m_spAttrXXX, clsid)  
```  
  
 İkinci, [DECLARE_GET_CONTROLLING_UNKNOWN](../atl/reference/aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) makrosu da eklenir.  
  
## <a name="example"></a>Örnek  
  
```  
// cpp_attr_ref_aggregates.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
// requires 'aggregatable.dll'  
// see aggregatable attribute to create 'aggregatable.dll'  
class DECLSPEC_UUID("1a8369cc-1c91-42c4-befa-5a5d8c9d2529") CMyClass;  
  
[module (name="MYObject")];  
[object, uuid("ab006d85-e754-47c5-9ef4-2744ff32a20c")]  
__interface IObject  
{  
};  
  
[ coclass, aggregates(__uuidof(CMyClass)),   
  uuid("91cb2c06-8931-432a-baac-206e55c4edfb")]  
struct CObject : IObject  
{  
   int i;  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**, `struct`|  
|**Yinelenebilir**|Evet|  
|**Gerekli öznitelikler**|Bir veya daha fazlasını: **coclass**, **ProgID**, veya **vi_progid**.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM öznitelikleri](../windows/com-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Toplama](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
 [toplanabilir](http://msdn.microsoft.com/library/windows/desktop/aa366721)   
 [COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](../atl/reference/com-interface-entry-macros.md#com_interface_entry_autoaggregate_blind)   
 