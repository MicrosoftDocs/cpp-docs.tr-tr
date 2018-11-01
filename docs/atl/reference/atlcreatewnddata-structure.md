---
title: _AtlCreateWndData yapısı
ms.date: 11/04/2016
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
ms.openlocfilehash: 860d5772279d0ca0581a8cac1e0ef224f829586d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534192"
---
# <a name="atlcreatewnddata-structure"></a>_AtlCreateWndData yapısı

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

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)

