---
title: _com_error::WCodeToHRESULT
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCodeToHRESULT
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
ms.openlocfilehash: f2fc84be53d95754d21c30eaea8dd981447453d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593079"
---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT

**Microsoft'a özgü**

16-bit eşler *wCode* 32 bitlik HRESULT için.

## <a name="syntax"></a>Sözdizimi

```
static HRESULT WCodeToHRESULT(
   WORD wCode
) throw( );
```

#### <a name="parameters"></a>Parametreler

*WCode*<br/>
16 bit *wCode* 32 bitlik HRESULT eşlendi.

## <a name="return-value"></a>Dönüş Değeri

16-bit eşleştirilmiş 32 bitlik HRESULT *wCode*.

## <a name="remarks"></a>Açıklamalar

Bkz: [WCode](../cpp/com-error-wcode.md) üye işlevi.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error Sınıfı](../cpp/com-error-class.md)