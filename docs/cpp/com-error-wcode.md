---
description: 'Hakkında daha fazla bilgi edinin: _com_error:: WCode'
title: _com_error::WCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCode
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
ms.openlocfilehash: e3a19e5ae6c98cb38445e5eaa822474b2a852135
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295737"
---
# <a name="_com_errorwcode"></a>_com_error::WCode

**Microsoft'a Özgü**

Encapsulated HRESULT 'e eşlenmiş 16 bit hata kodunu alır.

## <a name="syntax"></a>Syntax

```
WORD WCode ( ) const throw( );
```

## <a name="return-value"></a>Dönüş Değeri

HRESULT, 0x80040200 aralığında 0x8004FFFF içindeyse, `WCode` Yöntem hresult eksi 0x80040200 döndürür; Aksi takdirde, sıfır döndürür.

## <a name="remarks"></a>Açıklamalar

`WCode`Yöntemi, com destek kodunda gerçekleşen bir eşlemeyi geri almak için kullanılır. Bir `dispinterface` özellik veya yöntem için sarmalayıcı, bağımsız değişkenleri ve çağrıları paketleyen bir destek yordamını çağırır `IDispatch::Invoke` . Geri dönmeden sonra, HRESULT bir hata `DISP_E_EXCEPTION` döndürülürse, hata bilgileri `EXCEPINFO` geçirilen yapıdan alınır `IDispatch::Invoke` . Hata kodu yapının üyesi içinde depolanan 16 bitlik bir değer `wCode` `EXCEPINFO` ya da yapının üyesinde tam 32 bitlik bir değer olabilir `scode` `EXCEPINFO` . 16 bit `wCode` döndürülürse, önce 32 bitlik bir hata hresult ile eşlenmelidir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error sınıfı](../cpp/com-error-class.md)
