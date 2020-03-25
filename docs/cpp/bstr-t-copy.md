---
title: _bstr_t::copy
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::copy
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
ms.openlocfilehash: 1fe8cfb5b644b3c7c34cf3325a91ebdf23a04946
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190332"
---
# <a name="_bstr_tcopy"></a>_bstr_t::copy

**Microsoft 'a özgü**

Encapsulated `BSTR`bir kopyasını oluşturur.

## <a name="syntax"></a>Sözdizimi

```
BSTR copy( bool fCopy = true ) const;
```

#### <a name="parameters"></a>Parametreler

*fCopy*<br/>
TRUE ise, **Copy** içerilen `BSTR`bir kopyasını döndürür, aksi halde **Copy** gerçek bstr döndürür.

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

[_bstr_t Sınıfı](../cpp/bstr-t-class.md)
