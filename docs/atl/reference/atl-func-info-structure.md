---
title: _Atl_func_ınfo yapısı | Microsoft Docs
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
ms.openlocfilehash: 392e9dc2997dc7f4f0f36b1d7d38cd8ecdc691bb
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43759538"
---
# <a name="atlfuncinfo-structure"></a>_Atl_func_ınfo yapısı

Bir yöntem veya özellik üzerinde bir dispinterface açıklamak için kullanılan tür bilgilerini içerir.

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

`cc`  
Çağırma kuralı. Bu yapı ile kullanırken [Idispeventsimpleımpl](../../atl/reference/idispeventsimpleimpl-class.md) sınıfı, bu üye CC_STDCALL olması gerekir. `CC_CDECL` Windows CE için desteklenen tek seçenek `CALLCONV` alanını `_ATL_FUNC_INFO` yapısı. Başka bir değer desteklenmiyor bu nedenle, davranışı tanımsız.

`vtReturn`  
Değişken türü işlevin dönüş değeri.

`nParams`  
İşlev parametreleri sayısı.

`pVarTypes`  
Değişken işlevi parametre türleri dizisi.

## <a name="remarks"></a>Açıklamalar

Dahili olarak, ATL tür kitaplığından alınan bilgileri tutmak için bu yapıyı kullanır. İle kullanılan bir olay işleyicisi için tür bilgilerini sağlarsanız, bu yapı doğrudan düzenlemezsiniz gerekebilir [Idispeventsimpleımpl](../../atl/reference/idispeventsimpleimpl-class.md) sınıfı ve [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) makrosu.

## <a name="example"></a>Örnek

IDL içinde tanımlanan bir görüntü arabirimi yöntemi verilen:

[!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]

tanımlayın bir `_ATL_FUNC_INFO` yapısı:

[!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]

## <a name="requirements"></a>Gereksinimler

Üstbilgi: atlcom.h

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)  
[Idispeventsimpleımpl sınıfı](../../atl/reference/idispeventsimpleimpl-class.md)   
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)

