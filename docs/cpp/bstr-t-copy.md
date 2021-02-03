---
description: ': _Bstr_t:: Copy hakkında daha fazla bilgi'
title: _bstr_t::copy
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::copy
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.openlocfilehash: 98726e0c3100851d1496e532310ece2209d71ae0
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522865"
---
# `_bstr_t::copy`

**Microsoft'a Özgü**

Encapsulated öğesinin bir kopyasını oluşturur `BSTR` .

## <a name="syntax"></a>Sözdizimi

```cpp
BSTR copy( bool fCopy = true ) const;
```

### <a name="parameters"></a>Parametreler

*`fCopy`*\
Varsa **`true`** , **`copy`** içerilen öğesinin bir kopyasını döndürür `BSTR` , aksi takdirde **`copy`** gerçek değeri döndürür `BSTR` .

## <a name="remarks"></a>Açıklamalar

`BSTR`Parametreye bağlı olarak, kapsüllenmiş nesnenin veya kapsüllenmiş nesnenin kendisinin yeni ayrılmış bir kopyasını döndürür.

## <a name="example"></a>Örnek

```cpp
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t
   *pVal = m_bsConStr.copy();
}
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[`_bstr_t` sınıfı](../cpp/bstr-t-class.md)
