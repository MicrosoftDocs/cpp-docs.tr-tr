---
title: _ATL_MODULE70 Yapısı
ms.date: 11/04/2016
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
ms.openlocfilehash: 8d39cdd281e09cdfe09546627aa630a11d12464e
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168572"
---
# <a name="_atl_module70-structure"></a>_ATL_MODULE70 Yapısı

Her ATL modülü tarafından kullanılan verileri içerir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct _ATL_MODULE70 {
    UINT cbSize;
    LONG m_nLockCnt;
    _ATL_TERMFUNC_ELEM* m_pTermFuncs;
    CComCriticalSection m_csStaticDataInitAndTypeInfo;
};
```

## <a name="members"></a>Üyeler

`cbSize`<br/>
Sürüm oluşturma için kullanılan yapının boyutu.

`m_nLockCnt`<br/>
Modülün etkin kalacağı süreyi belirleme başvuru sayısı.

`m_pTermFuncs`<br/>
ATL kapandığında çağrılması için kaydedilmiş işlevleri izler.

`m_csStaticDataInitAndTypeInfo`<br/>
Çok iş parçacıklı durumlarda iç verilere erişimi koordine etmek için kullanılır.

## <a name="remarks"></a>Açıklamalar

[_ATL_MODULE](atl-typedefs.md#_atl_module) , bir typedef olarak tanımlanır `_ATL_MODULE70`.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)
