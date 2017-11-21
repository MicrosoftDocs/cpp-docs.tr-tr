---
title: "_ATL_FUNC_INFO yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
dev_langs: C++
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cb7f467d6491f58337177e8f16a580d28cb63e78
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="atlfuncinfo-structure"></a>_ATL_FUNC_INFO yapısı
Bir yöntemi veya özelliği üzerinde görüntüleme arabirimi tanımlamak için kullanılan tür bilgileri içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct _ATL_FUNC_INFO {
    CALLCONV cc;
    VARTYPE vtReturn;
    SHORT nParams;
    VARTYPE pVarTypes[_ATL_MAX_VARTYPES];
};
```  
  
## <a name="members"></a>Üyeler  
 **cc**  
 Çağırma kuralı. Bu yapı ile kullanırken [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) sınıfı, bu üye olmalıdır **CC_STDCALL**. `CC_CDECL`Windows CE için desteklenen tek seçenek `CALLCONV` alanını `_ATL_FUNC_INFO` yapısı. Başka bir değer desteklenmiyor böylece davranışını tanımlanmamış.  
  
 **vtReturn**  
 Değişken türü işlevinin dönüş değeri.  
  
 **nParams**  
 İşlev parametreleri sayısı.  
  
 **pVarTypes**  
 İşlev parametreleri VARIANT türleri dizisi.  
  
## <a name="remarks"></a>Açıklamalar  
 Dahili olarak, bir tür kitaplığından alınan bilgileri tutmak için bu yapı ATL kullanır. Bu yapı ile kullanılan bir olay işleyicisinin türü bilgilerini sağlarsanız, doğrudan işlemek gerekebilir [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) sınıfı ve [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) makrosu.  
  
## <a name="example"></a>Örnek  
 IDL içinde tanımlanmış bir görüntüleme arabirimi yöntemi verilen:  
  
 [!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]  
  
 tanımlayın bir `_ATL_FUNC_INFO` yapısı:  
  
 [!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapıları](../../atl/reference/atl-structures.md)   
 [IDispEventSimpleImpl sınıfı](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)





