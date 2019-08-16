---
title: _com_error::ErrorMessage
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorMessage
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
ms.openlocfilehash: 44fc9755cd69050ea82145636f01614258943794
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500586"
---
# <a name="_com_errorerrormessage"></a>_com_error::ErrorMessage

**Microsoft 'a özgü**

`_com_error` Nesnesinde depolanan HRESULT için dize iletisini alır.

## <a name="syntax"></a>Sözdizimi

```
const TCHAR * ErrorMessage( ) const throw( );
```

## <a name="return-value"></a>Dönüş Değeri

`_com_error` Nesne içinde kaydedilen HRESULT için dize iletisi döndürür. HRESULT eşlenmiş bir 16 bit [wCode](../cpp/com-error-wcode.md)ise "`IDispatch error #<wCode>`" genel iletisi döndürülür. Hiçbir ileti bulunamazsa, "`Unknown error #<hresult>`" genel iletisi döndürülür. Döndürülen dize, _UNICODE makrosunun durumuna bağlı olarak Unicode veya çok baytlı bir dizedir.

## <a name="remarks"></a>Açıklamalar

`_com_error` Nesne içinde kaydedilen HRESULT için uygun sistem iletisi metnini alır. Sistem ileti metni, Win32 [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) işlevi çağırarak elde edilir. Döndürülen dize `FormatMessage` API tarafından ayrılır ve `_com_error` nesne yok edildiğinde serbest bırakılır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)