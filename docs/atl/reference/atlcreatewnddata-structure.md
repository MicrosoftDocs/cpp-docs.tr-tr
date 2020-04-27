---
title: _AtlCreateWndData Yapısı
ms.date: 11/04/2016
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
ms.openlocfilehash: 6453156a59b73bcb06c7c86920e1dc524874cef8
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168546"
---
# <a name="_atlcreatewnddata-structure"></a>_AtlCreateWndData Yapısı

Bu yapı, ATL 'deki Pencereleme kodunda sınıf örneği verisi içerir.

## <a name="syntax"></a>Sözdizimi

```cpp
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```

## <a name="members"></a>Üyeler

`m_pThis`<br/>
**Bu** işaretçi, pencere yordamlarındaki sınıf örneğine erişim sağlamak için kullanılır.

`m_dwThreadID`<br/>
Geçerli sınıf örneğinin iş parçacığı KIMLIĞI.

`m_pNext`<br/>
Sonraki `_AtlCreateWndData` nesnenin işaretçisi.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)
