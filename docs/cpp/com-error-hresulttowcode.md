---
title: _com_error::HRESULTToWCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::HRESULTToWCode
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
ms.openlocfilehash: 35a497c273f15c9755d3607e7907a3a48dad8dc8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180569"
---
# <a name="_com_errorhresulttowcode"></a>_com_error::HRESULTToWCode

**Microsoft 'a özgü**

32 bit HRESULT ile 16 bit `wCode`eşler.

## <a name="syntax"></a>Sözdizimi

```
static WORD HRESULTToWCode(
   HRESULT hr
) throw( );
```

#### <a name="parameters"></a>Parametreler

*HR*<br/>
16 bit `wCode`eşlenecek 32 bitlik HRESULT.

## <a name="return-value"></a>Dönüş Değeri

16 bit `wCode`, 32-bit HRESULT ile eşlendi.

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [_com_error:: WCode](../cpp/com-error-wcode.md) .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error Sınıfı](../cpp/com-error-class.md)
