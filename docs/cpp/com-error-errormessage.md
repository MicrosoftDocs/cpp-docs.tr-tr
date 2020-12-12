---
description: 'Hakkında daha fazla bilgi edinin: _com_error:: ErrorMessage'
title: _com_error::ErrorMessage
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorMessage
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
ms.openlocfilehash: e7f91882d55e629744df5f26f7dcc64df1dddb22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296010"
---
# <a name="_com_errorerrormessage"></a>_com_error::ErrorMessage

**Microsoft'a Özgü**

Nesnesinde depolanan HRESULT için dize iletisini alır `_com_error` .

## <a name="syntax"></a>Syntax

```
const TCHAR * ErrorMessage( ) const throw( );
```

## <a name="return-value"></a>Dönüş Değeri

Nesne içinde kaydedilen HRESULT için dize iletisi döndürür `_com_error` . HRESULT eşlenmiş bir 16 bit [wCode](../cpp/com-error-wcode.md)ise "" genel iletisi `IDispatch error #<wCode>` döndürülür. Hiçbir ileti bulunamazsa, "" genel iletisi `Unknown error #<hresult>` döndürülür. Döndürülen dize, _UNICODE makrosunun durumuna bağlı olarak Unicode veya çok baytlı bir dizedir.

## <a name="remarks"></a>Açıklamalar

Nesne içinde kaydedilen HRESULT için uygun sistem iletisi metnini alır `_com_error` . Sistem ileti metni, Win32 [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) işlevi çağırarak elde edilir. Döndürülen dize API tarafından ayrılır `FormatMessage` ve nesne yok edildiğinde serbest bırakılır `_com_error` .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error sınıfı](../cpp/com-error-class.md)
