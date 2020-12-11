---
description: 'Daha fazla bilgi edinin: _ATL_FUNC_INFO yapısı'
title: _ATL_FUNC_INFO yapısı
ms.date: 11/04/2016
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
ms.openlocfilehash: 6368440347672524bb7d1e3aa3068ef91a2c6f09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158861"
---
# <a name="_atl_func_info-structure"></a>_ATL_FUNC_INFO yapısı

Bir dispınterface üzerindeki bir yöntemi veya özelliği anlatmak için kullanılan tür bilgilerini içerir.

## <a name="syntax"></a>Syntax

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
Çağırma kuralı. Bu yapının [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) sınıfıyla birlikte kullanılması durumunda, bu üyenin CC_STDCALL olması gerekir. `CC_CDECL` yapının alanı için Windows CE desteklenen tek seçenektir `CALLCONV` `_ATL_FUNC_INFO` . Başka herhangi bir değer desteklenmez, dolayısıyla davranışı tanımsız olur.

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

bir `_ATL_FUNC_INFO` Yapı tanımlayabilirsiniz:

[!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]

## <a name="requirements"></a>Gereksinimler

Üstbilgi: atlcom. h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)<br/>
[IDispEventSimpleImpl sınıfı](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)
