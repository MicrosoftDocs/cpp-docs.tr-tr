---
title: _bstr_t::copy
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::copy
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
ms.openlocfilehash: b6029e98e83b171d9ab9f8f3f0282fa3f46ca167
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227601"
---
# <a name="_bstr_tcopy"></a>_bstr_t::copy

**Microsoft'a Özgü**

Encapsulated öğesinin bir kopyasını oluşturur `BSTR` .

## <a name="syntax"></a>Söz dizimi

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
