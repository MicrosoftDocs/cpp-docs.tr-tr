---
title: _ATL_BASE_MODULE70 Yapısı
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
ms.openlocfilehash: 3893e4ce4fcd24f48d9e981ad24505f82dc98833
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168650"
---
# <a name="_atl_base_module70-structure"></a>_ATL_BASE_MODULE70 Yapısı

ATL kullanan herhangi bir proje tarafından kullanılır.

## <a name="syntax"></a>Sözdizimi

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
Bu `hInstance` modül için (exe veya dll).

`m_hInstResource`<br/>
Varsayılan örnek kaynak tanıtıcısı.

`m_bNT5orWin98`<br/>
İşletim sistemi sürüm bilgileri. ATL tarafından dahili olarak kullanılır.

`dwAtlBuildVer`<br/>
ATL sürümünü depolar. Şu anda 0x0700.

`pguidVer`<br/>
ATL 'nin iç GUID 'SI.

`m_csResource`<br/>
`m_rgResourceInstance` Diziye erişimi eşleştirmek için kullanılır. ATL tarafından dahili olarak kullanılır.

`m_rgResourceInstance`<br/>
ATL 'nin bildiği tüm kaynak örneklerinde kaynakları aramak için kullanılan dizi. ATL tarafından dahili olarak kullanılır.

## <a name="remarks"></a>Açıklamalar

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) , _ATL_BASE_MODULE70 bir typedef olarak tanımlanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore. h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)
