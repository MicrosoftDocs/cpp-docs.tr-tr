---
title: _AtlCreateWndData Structure
ms.date: 11/04/2016
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
ms.openlocfilehash: d6e3168b5c86de5bce3c3b9d3b0fbdea28ae604f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261253"
---
# <a name="atlcreatewnddata-structure"></a>_AtlCreateWndData Structure

Bu yapı ATL Pencereleme kodunda sınıfı örneği veri içeriyor

## <a name="syntax"></a>Sözdizimi

```
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```

## <a name="members"></a>Üyeler

`m_pThis`<br/>
**Bu** sınıf örneği pencere yordamları erişmek için kullanılan bir işaretçi.

`m_dwThreadID`<br/>
İş parçacığı kimliği geçerli sınıf örneğinin.

`m_pNext`<br/>
Sonraki işaretçisi `_AtlCreateWndData` nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)
