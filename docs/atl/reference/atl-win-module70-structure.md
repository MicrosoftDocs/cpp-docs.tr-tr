---
description: 'Daha fazla bilgi edinin: _ATL_WIN_MODULE70 yapısı'
title: _ATL_WIN_MODULE70 yapısı
ms.date: 11/04/2016
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
ms.openlocfilehash: 11b7fdad71fa8c7b615a0e6873571c38420c9b5d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158627"
---
# <a name="_atl_win_module70-structure"></a>_ATL_WIN_MODULE70 yapısı

ATL 'de Pencereleme kodu tarafından kullanılır.

## <a name="syntax"></a>Syntax

```cpp
struct _ATL_WIN_MODULE70 {
    UNIT cbSize;
    CRITICAL_SECTION m_csWindowCreate;
    _AtlCreateWndData* m_pCreateWndList;
    CSimpleArray<ATOM> m_rgWindowClassAtoms;
};
```

## <a name="members"></a>Üyeler

`cbSize`<br/>
Sürüm oluşturma için kullanılan yapının boyutu.

`m_csWindowCreate`<br/>
Pencere kayıt koduna erişimi seri hale getirmek için kullanılır. ATL tarafından dahili olarak kullanılır.

`m_pCreateWndList`<br/>
Windows nesnelerini nesnelerine bağlamak için kullanılır. ATL tarafından dahili olarak kullanılır.

`m_rgWindowClassAtoms`<br/>
Pencere sınıfı kayıtlarını, sonlandırmada düzgün şekilde kaydettirilmemiş olmaları için izlemek için kullanılır. ATL tarafından dahili olarak kullanılır.

## <a name="remarks"></a>Açıklamalar

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module) , bir typedef olarak tanımlanır `_ATL_WIN_MODULE70` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)
