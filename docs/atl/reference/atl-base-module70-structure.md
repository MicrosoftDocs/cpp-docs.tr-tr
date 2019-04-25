---
title: _ATL_BASE_MODULE70 Structure
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
ms.openlocfilehash: 4fddd4b3af6155d0663b9c01edfab4fcf4a60426
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260993"
---
# <a name="atlbasemodule70-structure"></a>_ATL_BASE_MODULE70 Structure

ATL kullanan herhangi bir proje tarafından kullanılan

## <a name="syntax"></a>Sözdizimi

```
struct _ATL_BASE_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInst;
    HINSTANCE m_hInstResource;
    bool m_bNT5orWin98;
    DWORD dwAtlBuildVer;
    GUID* pguidVer;
    CRITICAL_SECTION m_csResource;
    CSimpleArray<HINSTANCE> m_rgResourceInstance;
};
```

## <a name="members"></a>Üyeler

`cbSize`<br/>
Sürüm oluşturma için kullanılan bir yapının boyutu.

`m_hInst`<br/>
`hInstance` Bu Modülü (exe veya dll).

`m_hInstResource`<br/>
Varsayılan örneği kaynağı tanıtıcısı.

`m_bNT5orWin98`<br/>
İşletim sistemi sürüm bilgisi. ATL tarafından dahili olarak kullanılır

`dwAtlBuildVer`<br/>
ATL sürümünü depolar Şu anda 0x0700.

`pguidVer`<br/>
ATL'nin iç GUID.

`m_csResource`<br/>
Erişimi eşitlemek için kullanılan `m_rgResourceInstance` dizisi. ATL tarafından dahili olarak kullanılır

`m_rgResourceInstance`<br/>
ATL uyumlu olduğu tüm kaynak örneklerinin kaynaklarında aramak için kullanılan dizisi. ATL tarafından dahili olarak kullanılır

## <a name="remarks"></a>Açıklamalar

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) _ATL_BASE_MODULE70 typedef tanımlanır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcore.h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)
