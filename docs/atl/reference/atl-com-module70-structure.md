---
title: _ATL_COM_MODULE70 Yapısı
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_COM_MODULE70
- ATL._ATL_COM_MODULE70
- _ATL_COM_MODULE70
helpviewer_keywords:
- _ATL_COM_MODULE70 structure
- ATL_COM_MODULE70 structure
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
ms.openlocfilehash: c2e9e3d6695a7fbbcc87c489edf2e96fcdffb835
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168637"
---
# <a name="_atl_com_module70-structure"></a>_ATL_COM_MODULE70 Yapısı

ATL 'de COM ile ilgili kod tarafından kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
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
Sürüm oluşturma için kullanılan yapının boyutu.

`m_hInstTypeLib`<br/>
Bu modülün tür kitaplığına tanıtıcı örneği.

`m_ppAutoObjMapFirst`<br/>
Bu modülün nesne eşleme girdilerinin başlangıcını gösteren dizi öğesinin adresi.

`m_ppAutoObjMapLast`<br/>
Bu modülün nesne eşleme girdilerinin sonunu gösteren dizi öğesinin adresi.

`m_csObjMap`<br/>
Nesne eşleme girişlerine erişimi seri hale getirmek için kritik bölüm. ATL tarafından dahili olarak kullanılır.

## <a name="remarks"></a>Açıklamalar

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module) , _ATL_COM_MODULE70 bir typedef olarak tanımlanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)
