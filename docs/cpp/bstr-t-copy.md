---
title: _bstr_t::copy
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::copy
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
ms.openlocfilehash: 13ddf57e0bdbdbcc0c5b487e879e14b000de3ad0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393941"
---
# <a name="bstrtcopy"></a>_bstr_t::copy

**Microsoft'a özgü**

Kapsüllenmiş bir kopyasını oluşturur `BSTR`.

## <a name="syntax"></a>Sözdizimi

```
BSTR copy( bool fCopy = true ) const;
```

#### <a name="parameters"></a>Parametreler

*fCopy*<br/>
TRUE ise **kopyalama** kapsanan bir kopyasını döndürür `BSTR`, aksi takdirde **kopyalama** gerçek BSTR'yi döndürür.

## <a name="remarks"></a>Açıklamalar

Kapsüllenmiş `BSTR` nesnesinin yeni ayrılmış bir kopyasını döndürür.

## <a name="example"></a>Örnek

```cpp
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t
   *pVal = m_bsConStr.copy();
}
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_bstr_t Sınıfı](../cpp/bstr-t-class.md)