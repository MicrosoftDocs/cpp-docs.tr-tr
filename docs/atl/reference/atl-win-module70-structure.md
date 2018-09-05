---
title: _Atl_wın_module70 yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4c5d7ad570d9745e10107f0df09faccd9eb42e3
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761559"
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

`cbSize`  
Sürüm oluşturma için kullanılan bir yapının boyutu.

`m_csWindowCreate`  
Pencere kayıt kodu erişim serileştirmek için kullanılır. ATL tarafından dahili olarak kullanılır

`m_pCreateWndList`  
Windows, nesnelere bağlamak için kullanılır. ATL tarafından dahili olarak kullanılır

`m_rgWindowClassAtoms`  
Pencere sınıfı kaydı sonlandırmanın düzgün kaydedilmemiş olabilir, böylece izlemek için kullanılır. ATL tarafından dahili olarak kullanılır

## <a name="remarks"></a>Açıklamalar

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module) typedef tanımlanan `_ATL_WIN_MODULE70`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)

