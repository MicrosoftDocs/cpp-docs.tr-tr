---
title: _com_error::ErrorMessage
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorMessage
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
ms.openlocfilehash: b1c1b5a79cdf5ee2a4a17d969d23ce0d0d85ab54
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155188"
---
# <a name="comerrorerrormessage"></a>_com_error::ErrorMessage

**Microsoft'a özgü**

HRESULT içinde depolanan için dize iletiyi alır `_com_error` nesne.

## <a name="syntax"></a>Sözdizimi

```
const TCHAR * ErrorMessage( ) const throw( );
```

## <a name="return-value"></a>Dönüş Değeri

HRESULT içinde kaydedilen için dize iletisi döndürür `_com_error` nesne. HRESULT eşlenmiş bir 16-bit ise [wCode](../cpp/com-error-wcode.md), ardından genel bir ileti "`IDispatch error #<wCode>`" döndürülür. İleti bulunursa, ardından genel bir ileti "`Unknown error #<hresult>`" döndürülür. Döndürülen dize bir Unicode ya da _UNICODE makrosu durumuna bağlı olarak, çok baytlı bir dize değil.

## <a name="remarks"></a>Açıklamalar

HRESULT içinde kaydedilen için uygun sistem ileti metni alır `_com_error` nesne. Sistem ileti metni Win32 çağırılarak alınır [FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage) işlevi. Tarafından döndürülen dize ayrılan `FormatMessage` API ve serbest bırakıldığında `_com_error` nesnesi yok edildiğinde.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)