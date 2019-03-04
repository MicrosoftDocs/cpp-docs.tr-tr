---
title: _ATL_COM_MODULE70 Structure
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_COM_MODULE70
- ATL._ATL_COM_MODULE70
- _ATL_COM_MODULE70
helpviewer_keywords:
- _ATL_COM_MODULE70 structure
- ATL_COM_MODULE70 structure
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
ms.openlocfilehash: c6361fc5374ed732cd9ccbfbbd1d3d1c2fc8f1f0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261290"
---
# <a name="atlcommodule70-structure"></a>_ATL_COM_MODULE70 Structure

ATL COM ile ilgili kod tarafından kullanılan

## <a name="syntax"></a>Sözdizimi

```
struct _ATL_COM_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInstTypeLib;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;
    CRITICAL_SECTION m_csObjMap;
};
```

## <a name="members"></a>Üyeler

`cbSize`<br/>
Sürüm oluşturma için kullanılan bir yapının boyutu.

`m_hInstTypeLib`<br/>
Bu modül için tür kitaplığı için tanıtıcı örneği.

`m_ppAutoObjMapFirst`<br/>
Bu modülü için nesne eşleme girişleri başlangıcını gösteren bir dizi öğenin adresi.

`m_ppAutoObjMapLast`<br/>
Bu modülü için nesne eşleme girişleri sonuna belirten dizi öğesinin adresi.

`m_csObjMap`<br/>
Nesne eşleme girişleri erişimi serileştirmek için kritik bölüm. ATL tarafından dahili olarak kullanılır

## <a name="remarks"></a>Açıklamalar

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module) _ATL_COM_MODULE70 typedef tanımlanır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)
