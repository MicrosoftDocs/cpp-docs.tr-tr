---
title: _com_error::WCodeToHRESULT
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCodeToHRESULT
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
ms.openlocfilehash: f2194e0e54a93d3227b84d893f9d3f208d972d09
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180517"
---
# <a name="_com_errorwcodetohresult"></a>_com_error::WCodeToHRESULT

**Microsoft 'a özgü**

16 bit *wCode* 'u 32-bit HRESULT 'e eşler.

## <a name="syntax"></a>Sözdizimi

```
static HRESULT WCodeToHRESULT(
   WORD wCode
) throw( );
```

#### <a name="parameters"></a>Parametreler

*wCode*<br/>
32-bit HRESULT ile eşlenecek 16 bit *wCode* .

## <a name="return-value"></a>Dönüş Değeri

32-bit HRESULT, 16 bit *wCode*'dan eşlendi.

## <a name="remarks"></a>Açıklamalar

Bkz. [wCode](../cpp/com-error-wcode.md) üye işlevi.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error Sınıfı](../cpp/com-error-class.md)
