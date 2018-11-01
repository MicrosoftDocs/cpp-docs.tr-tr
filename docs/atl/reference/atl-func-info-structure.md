---
title: _Atl_func_ınfo yapısı
ms.date: 11/04/2016
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
ms.openlocfilehash: 8398bc999e9a62d03990fd1b205ad438b6428431
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554030"
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

`cc`<br/>
Çağırma kuralı. Bu yapı ile kullanırken [Idispeventsimpleımpl](../../atl/reference/idispeventsimpleimpl-class.md) sınıfı, bu üye CC_STDCALL olması gerekir. `CC_CDECL` Windows CE için desteklenen tek seçenek `CALLCONV` alanını `_ATL_FUNC_INFO` yapısı. Başka bir değer desteklenmiyor bu nedenle, davranışı tanımsız.

`vtReturn`<br/>
Değişken türü işlevin dönüş değeri.

`nParams`<br/>
İşlev parametreleri sayısı.

`pVarTypes`<br/>
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

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)<br/>
[IDispEventSimpleImpl Sınıfı](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)

