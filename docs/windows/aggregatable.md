---
title: toplanabilir | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.aggregatable
dev_langs:
- C++
helpviewer_keywords:
- aggregatable attribute
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1d80b2fb707145f698e8d9bb883059478c3da10b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863832"
---
# <a name="aggregatable"></a>toplanabilir
Sınıf toplama desteklediğini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ aggregatable(   
   value  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *değer* (isteğe bağlı)  
 COM nesnesinin ne zaman kümelenebilir belirtmek için bir parametre:  
  
-   **hiçbir zaman** COM nesnesi toplanamaz.  
  
-   **izin verilen** COM nesnesi doğrudan oluşturulabilir veya onu kümelenebilir. Bu varsayılandır.  
  
-   **her zaman** COM nesnesi doğrudan oluşturulamaz ve yalnızca kümelenebilir. Çağırdığınızda `CoCreateInstance` bu nesne için aggregating nesnenin belirtmelisiniz **IUnknown** arabirimi (denetleme **IUnknown**).  
  
## <a name="remarks"></a>Açıklamalar  
 **Toplanabilir** C++ özniteliğine sahip ile aynı işlevselliği [toplanabilir](http://msdn.microsoft.com/library/windows/desktop/aa366721) MIDL özniteliği. Bu derleyici geçer anlamına gelir **toplanabilir** oluşturulan .idl dosyasına özniteliği aracılığıyla.  
  
 Bu öznitelik gerektiren [coclass](../windows/coclass.md), [ProgID](../windows/progid.md), veya [vi_progid](../windows/vi-progid.md) özniteliği (veya bunlardan birini gelir başka bir öznitelik) de uygulanması aynı öğeye. Herhangi bir tek öznitelik kullanılırsa, diğer iki otomatik olarak uygulanır. Örneğin, varsa **ProgID** uygulanan **vi_progid** ve **coclass** da uygulanır.  
  
 **ATL projeleri**  
  
 Bu öznitelik, ATL kullanan bir proje içinde kullanılıyorsa, öznitelik davranışını değiştirir. Daha önce açıklanan davranışa ek olarak, öznitelik ayrıca aşağıdaki makroları biri için hedef sınıf ekler:  
  
|Parametre değeri|Eklenen makrosu|  
|---------------------|--------------------|  
|**Hiçbir zaman**|[DECLARE_NOT_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_not_aggregatable)|  
|**İzin verildi**|[DECLARE_POLY_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_poly_aggregatable)|  
|**Her zaman**|[DECLARE_ONLY_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_only_aggregatable)|  
  
## <a name="example"></a>Örnek  
  
```  
// cpp_attr_ref_aggregatable.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="MyModule")];  
  
[ coclass, aggregatable(allowed),  
  uuid("1a8369cc-1c91-42c4-befa-5a5d8c9d2529")]  
class CMyClass {};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**, `struct`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Bir veya daha fazlasını: **coclass**, **ProgID**, veya **vi_progid**.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Toplama](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
