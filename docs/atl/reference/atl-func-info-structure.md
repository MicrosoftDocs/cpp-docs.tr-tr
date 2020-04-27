---
title: _ATL_FUNC_INFO Yapısı
ms.date: 11/04/2016
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
ms.openlocfilehash: b1c740cf1a1ed344dbceb028bd1f39a87fc09363
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168598"
---
# <a name="_atl_func_info-structure"></a>_ATL_FUNC_INFO Yapısı

Bir dispınterface üzerindeki bir yöntemi veya özelliği anlatmak için kullanılan tür bilgilerini içerir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct _ATL_FUNC_INFO {
    CALLCONV cc;
    VARTYPE vtReturn;
    SHORT nParams;
    VARTYPE pVarTypes[_ATL_MAX_VARTYPES];
};
```

## <a name="members"></a>Üyeler

`cc`<br/>
Çağırma kuralı. Bu yapının [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) sınıfıyla birlikte kullanılması durumunda, bu üyenin CC_STDCALL olması gerekir. `CC_CDECL``_ATL_FUNC_INFO` yapının `CALLCONV` alanı için Windows CE desteklenen tek seçenektir. Başka herhangi bir değer desteklenmez, dolayısıyla davranışı tanımsız olur.

`vtReturn`<br/>
İşlev dönüş değerinin değişken türü.

`nParams`<br/>
İşlev parametrelerinin sayısı.

`pVarTypes`<br/>
İşlev parametrelerinin değişken türlerinden oluşan bir dizi.

## <a name="remarks"></a>Açıklamalar

Dahili olarak, ATL bu yapıyı bir tür kitaplığından alınan bilgileri tutmak için kullanır. [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) sınıfı ve [SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) makrosu ile kullanılan bir olay işleyicisi için tür bilgisi sağlarsanız, bu yapıyı doğrudan değiştirmeniz gerekebilir.

## <a name="example"></a>Örnek

IDL içinde tanımlanan bir dispınterface yöntemi verildi:

[!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]

bir `_ATL_FUNC_INFO` yapı tanımlayabilirsiniz:

[!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]

## <a name="requirements"></a>Gereksinimler

Üstbilgi: atlcom. h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)<br/>
[IDispEventSimpleImpl Sınıfı](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)
