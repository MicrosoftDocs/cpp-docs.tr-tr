---
title: _com_error::WCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCode
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
ms.openlocfilehash: 92dffbdbe034ef55be04c1b7d204be6880d8d4b2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190202"
---
# <a name="_com_errorwcode"></a>_com_error::WCode

**Microsoft 'a özgü**

Encapsulated HRESULT 'e eşlenmiş 16 bit hata kodunu alır.

## <a name="syntax"></a>Sözdizimi

```
WORD WCode ( ) const throw( );
```

## <a name="return-value"></a>Dönüş Değeri

HRESULT, 0x80040200 aralığında 0x8004FFFF içindeyse `WCode` yöntemi HRESULT eksi 0x80040200 döndürür; Aksi takdirde, sıfır döndürür.

## <a name="remarks"></a>Açıklamalar

`WCode` yöntemi, COM destek kodunda gerçekleşen bir eşlemeyi geri almak için kullanılır. Bir `dispinterface` özelliği veya yöntemi için sarmalayıcı, bağımsız değişkenleri paketleyen ve `IDispatch::Invoke`çağıran bir destek yordamını çağırır. Geri dönmeden sonra, `DISP_E_EXCEPTION` bir HRESULT hatası döndürülürse, hata bilgileri `IDispatch::Invoke`geçirilen `EXCEPINFO` yapısından alınır. Hata kodu, `EXCEPINFO` yapısının `wCode` üyesinde depolanan 16 bitlik bir değer ya da `EXCEPINFO` yapısının `scode` üyesinde tam 32 bitlik bir değer olabilir. 16 bit `wCode` döndürülürse, önce 32 bitlik bir hata HRESULT ile eşlenmelidir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error Sınıfı](../cpp/com-error-class.md)
