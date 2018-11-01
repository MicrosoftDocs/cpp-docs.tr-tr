---
title: _Atl_wın_module70 yapısı
ms.date: 11/04/2016
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
ms.openlocfilehash: 4f1718c76d21f2e13b36c29db785fe989ff6108e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482530"
---
# <a name="atlwinmodule70-structure"></a>_Atl_wın_module70 yapısı

ATL Pencereleme kod tarafından kullanılan

## <a name="syntax"></a>Sözdizimi

```
struct _ATL_WIN_MODULE70 {
    UNIT cbSize;
    CRITICAL_SECTION m_csWindowCreate;
    _AtlCreateWndData* m_pCreateWndList;
    CSimpleArray<ATOM> m_rgWindowClassAtoms;
};
```

## <a name="members"></a>Üyeler

`cbSize`<br/>
Sürüm oluşturma için kullanılan bir yapının boyutu.

`m_csWindowCreate`<br/>
Pencere kayıt kodu erişim serileştirmek için kullanılır. ATL tarafından dahili olarak kullanılır

`m_pCreateWndList`<br/>
Windows, nesnelere bağlamak için kullanılır. ATL tarafından dahili olarak kullanılır

`m_rgWindowClassAtoms`<br/>
Pencere sınıfı kaydı sonlandırmanın düzgün kaydedilmemiş olabilir, böylece izlemek için kullanılır. ATL tarafından dahili olarak kullanılır

## <a name="remarks"></a>Açıklamalar

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module) typedef tanımlanan `_ATL_WIN_MODULE70`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)

