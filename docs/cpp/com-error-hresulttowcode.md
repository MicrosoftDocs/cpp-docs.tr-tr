---
description: 'Hakkında daha fazla bilgi edinin: _com_error:: HRESULTToWCode'
title: _com_error::HRESULTToWCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::HRESULTToWCode
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
ms.openlocfilehash: 1bbf62be42d4e34a2ef73493f0449c2ffbaf0646
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295841"
---
# <a name="_com_errorhresulttowcode"></a>_com_error::HRESULTToWCode

**Microsoft'a Özgü**

32 bitlik HRESULT 'yi 16 bit 'e eşler `wCode` .

## <a name="syntax"></a>Sözdizimi

```
static WORD HRESULTToWCode(
   HRESULT hr
) throw( );
```

#### <a name="parameters"></a>Parametreler

*sa*<br/>
16-bit ile eşlenecek 32 bitlik HRESULT `wCode` .

## <a name="return-value"></a>Dönüş Değeri

`wCode`32-BIT HRESULT 'den 16 bit eşlenmiş.

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [_com_error:: WCode](../cpp/com-error-wcode.md) .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error sınıfı](../cpp/com-error-class.md)
