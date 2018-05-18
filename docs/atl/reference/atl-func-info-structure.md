---
title: _ATL_FUNC_INFO yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
dev_langs:
- C++
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa81e83d353c542ea5b2b6e8e5e8fe32f7c57606
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
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
 Çağırma kuralı. Bu yapı ile kullanırken [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) sınıfı, bu üye olmalıdır **CC_STDCALL**. `CC_CDECL` Windows CE için desteklenen tek seçenek `CALLCONV` alanını `_ATL_FUNC_INFO` yapısı. Başka bir değer desteklenmiyor böylece davranışını tanımlanmamış.  
  
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
  [Sınıflar ve yapılar](../../atl/reference/atl-classes.md)  
 [IDispEventSimpleImpl sınıfı](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)





