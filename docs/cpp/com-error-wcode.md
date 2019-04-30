---
title: _com_error::WCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCode
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
ms.openlocfilehash: f33871634b516723c94fead847f64ef20d25513f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399323"
---
# <a name="comerrorwcode"></a>_com_error::WCode

**Microsoft'a özgü**

Kapsüllenmiş HRESULT biçimine eşlenen 16-bit hata kodunu alır.

## <a name="syntax"></a>Sözdizimi

```
WORD WCode ( ) const throw( );
```

## <a name="return-value"></a>Dönüş Değeri

HRESULT için 0x80040200 0x8004FFFF aralığında ise `WCode` yöntemi 0x80040200 eksi HRESULT döndürür; Aksi takdirde, sıfır döndürür.

## <a name="remarks"></a>Açıklamalar

`WCode` Yöntemi COM desteği kodda gerçekleşen bir eşleme geri almak için kullanılır. İçin sarmalayıcı bir `dispinterface` özellik veya yöntem çağrıları ve bağımsız değişkenler paketleri bir destek yordam çağrıları `IDispatch::Invoke`. Bir hata varsa HRESULT dönüş sırasında `DISP_E_EXCEPTION` döndürülür, hata bilgilerini alınır `EXCEPINFO` yapısı geçirilen `IDispatch::Invoke`. Hata kodu olabilir depolanan bir 16 bitlik değer `wCode` üyesi `EXCEPINFO` yapısı veya bir tam 32-bit değeri `scode` üyesi `EXCEPINFO` yapısı. 16 bit varsa `wCode` döndürülür, ilk eşlenmeli bir 32-bit hata HRESULT.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error Sınıfı](../cpp/com-error-class.md)