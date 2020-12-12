---
description: 'Daha fazla bilgi edinin: _ATL_MODULE70 yapısı'
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
ms.openlocfilehash: 8a3076cebe7cab2bce49f660e8198052af393024
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165361"
---
# <a name="_atl_module70-structure"></a>_ATL_MODULE70 yapısı

Her ATL modülü tarafından kullanılan verileri içerir.

## <a name="syntax"></a>Syntax

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

[_ATL_MODULE](atl-typedefs.md#_atl_module) , bir typedef olarak tanımlanır `_ATL_MODULE70` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](../../atl/reference/atl-classes.md)
