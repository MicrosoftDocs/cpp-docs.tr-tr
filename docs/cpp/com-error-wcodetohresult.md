---
description: 'Hakkında daha fazla bilgi edinin: _com_error:: WCodeToHRESULT'
title: _com_error::WCodeToHRESULT
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCodeToHRESULT
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
ms.openlocfilehash: 9925c34f14f0685cb563e37a8cae0970911f009c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295724"
---
# <a name="_com_errorwcodetohresult"></a>_com_error::WCodeToHRESULT

**Microsoft'a Özgü**

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
[_com_error sınıfı](../cpp/com-error-class.md)
