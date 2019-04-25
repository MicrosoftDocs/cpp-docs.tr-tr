---
title: _com_error::HRESULTToWCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::HRESULTToWCode
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
ms.openlocfilehash: d89503e822d92bf6a1fcb2b6bb658d532af32c5d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155052"
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode

**Microsoft'a özgü**

16 bit için 32 bitlik HRESULT eşler `wCode`.

## <a name="syntax"></a>Sözdizimi

```
static WORD HRESULTToWCode(
   HRESULT hr
) throw( );
```

#### <a name="parameters"></a>Parametreler

*İK*<br/>
16 bit eşlenmesi 32 bitlik HRESULT `wCode`.

## <a name="return-value"></a>Dönüş Değeri

16-bit `wCode` 32 bitlik HRESULT eşlenmiş.

## <a name="remarks"></a>Açıklamalar

Bkz: [_com_error::WCode](../cpp/com-error-wcode.md) daha fazla bilgi için.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error Sınıfı](../cpp/com-error-class.md)