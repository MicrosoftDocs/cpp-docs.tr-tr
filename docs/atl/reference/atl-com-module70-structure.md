---
description: 'Daha fazla bilgi edinin: _ATL_COM_MODULE70 yapısı'
title: _ATL_COM_MODULE70 yapısı
ms.date: 11/04/2016
f1_keywords:
- ATL::_ATL_COM_MODULE70
- ATL._ATL_COM_MODULE70
- _ATL_COM_MODULE70
helpviewer_keywords:
- _ATL_COM_MODULE70 structure
- ATL_COM_MODULE70 structure
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
ms.openlocfilehash: db2139d1c816c13e6da104f6a6d785ef35a07721
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165419"
---
# <a name="_atl_com_module70-structure"></a>_ATL_COM_MODULE70 yapısı

ATL 'de COM ile ilgili kod tarafından kullanılır.

## <a name="syntax"></a>Syntax

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
