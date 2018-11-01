---
title: _ATL_MODULE70 yapısı
ms.date: 11/04/2016
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
ms.openlocfilehash: bf733a10a0be53eafb634c645dad6a4b58b8206d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438850"
---
# <a name="atlmodule70-structure"></a>_ATL_MODULE70 yapısı

Her ATL modülü tarafından kullanılan verileri içerir.

## <a name="syntax"></a>Sözdizimi

```
struct _ATL_MODULE70 {
    UINT cbSize;
    LONG m_nLockCnt;
    _ATL_TERMFUNC_ELEM* m_pTermFuncs;
    CComCriticalSection m_csStaticDataInitAndTypeInfo;
};
```

## <a name="members"></a>Üyeler

`cbSize`<br/>
Sürüm oluşturma için kullanılan bir yapının boyutu.

`m_nLockCnt`<br/>
Başvuru sayma modülü ne kadar süreyle etkin tutulan bağlantıyı destekliyorsa kalmalı belirlemek için.

`m_pTermFuncs`<br/>
ATL kapatıldığında çağrılacak kayıtlı işlevlerini izler.

`m_csStaticDataInitAndTypeInfo`<br/>
Çok iş parçacıklı durumlarda iç veri erişimi koordine etmek için kullanılır.

## <a name="remarks"></a>Açıklamalar

[_ATL_MODULE](atl-typedefs.md#_atl_module) typedef tanımlanan `_ATL_MODULE70`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)

