---
description: ': _Bstr_t:: Copy hakkında daha fazla bilgi'
title: _bstr_t::copy
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::copy
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
ms.openlocfilehash: 29ca965730dbcc22b4b725661ece68442d39aeba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229346"
---
# <a name="_bstr_tcopy"></a>_bstr_t::copy

**Microsoft'a Özgü**

Encapsulated öğesinin bir kopyasını oluşturur `BSTR` .

## <a name="syntax"></a>Sözdizimi

```
BSTR copy( bool fCopy = true ) const;
```

#### <a name="parameters"></a>Parametreler

*fCopy*<br/>
**`true`** **Copy** , içerilen öğesinin bir kopyasını döndürür `BSTR` , aksı halde **Copy** gerçek bstr döndürür.

## <a name="remarks"></a>Açıklamalar

Kapsüllenmiş `BSTR` nesnesinin yeni ayrılmış bir kopyasını döndürür.

## <a name="example"></a>Örnek

```cpp
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t
   *pVal = m_bsConStr.copy();
}
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t sınıfı](../cpp/bstr-t-class.md)
