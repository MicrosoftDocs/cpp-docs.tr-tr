---
description: 'Daha fazla bilgi edinin: _ATL_BASE_MODULE70 yapısı'
title: _ATL_BASE_MODULE70 yapısı
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
ms.openlocfilehash: 5bcf2083f9c8991871c05535fd3e20a39bfeb822
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165517"
---
# <a name="_atl_base_module70-structure"></a>_ATL_BASE_MODULE70 yapısı

ATL kullanan herhangi bir proje tarafından kullanılır.

## <a name="syntax"></a>Syntax

```cpp
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
Sürüm oluşturma için kullanılan yapının boyutu.

`m_hInst`<br/>
`hInstance`Bu modül için (exe veya dll).

`m_hInstResource`<br/>
Varsayılan örnek kaynak tanıtıcısı.

`m_bNT5orWin98`<br/>
İşletim sistemi sürüm bilgileri. ATL tarafından dahili olarak kullanılır.

`dwAtlBuildVer`<br/>
ATL sürümünü depolar. Şu anda 0x0700.

`pguidVer`<br/>
ATL 'nin iç GUID 'SI.

`m_csResource`<br/>
Diziye erişimi eşleştirmek için kullanılır `m_rgResourceInstance` . ATL tarafından dahili olarak kullanılır.

`m_rgResourceInstance`<br/>
ATL 'nin bildiği tüm kaynak örneklerinde kaynakları aramak için kullanılan dizi. ATL tarafından dahili olarak kullanılır.

## <a name="remarks"></a>Açıklamalar

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) , _ATL_BASE_MODULE70 bir typedef olarak tanımlanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore. h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)
