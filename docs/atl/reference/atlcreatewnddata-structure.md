---
description: 'Daha fazla bilgi edinin: _AtlCreateWndData yapısı'
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
ms.openlocfilehash: 912f2d108baa9cae1b91a34f3c5e386339d11f0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158614"
---
# <a name="_atlcreatewnddata-structure"></a>_AtlCreateWndData yapısı

Bu yapı, ATL 'deki Pencereleme kodunda sınıf örneği verisi içerir.

## <a name="syntax"></a>Syntax

```cpp
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```

## <a name="members"></a>Üyeler

`m_pThis`<br/>
**`this`** Pencere yordamlarındaki sınıf örneğine erişim almak için kullanılan işaretçi.

`m_dwThreadID`<br/>
Geçerli sınıf örneğinin iş parçacığı KIMLIĞI.

`m_pNext`<br/>
Sonraki `_AtlCreateWndData` nesnenin işaretçisi.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)
