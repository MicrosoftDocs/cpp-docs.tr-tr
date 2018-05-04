---
title: _com_error::ErrorMessage | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c16b8bb6859cd65b534d804764257b901050995b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="comerrorerrormessage"></a>_com_error::ErrorMessage
**Microsoft özel**  
  
 İçin dize iletiyi alır `HRESULT` depolanan `_com_error` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
const TCHAR * ErrorMessage( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dize ileti için döndürür `HRESULT` içinde kayıtlı `_com_error` nesnesi. Varsa `HRESULT` eşlenen bir 16 bit [wCode](../cpp/com-error-wcode.md), sonra genel bir ileti "`IDispatch error #<wCode>`" döndürülür. Hiçbir ileti bulunursa, sonra genel bir ileti "`Unknown error #<hresult>`" döndürülür. Döndürülen dize Unicode veya durumuna bağlı olarak birden çok baytlı dize olan **_UNICODE** makrosu.  
  
## <a name="remarks"></a>Açıklamalar  
 İçin uygun sistem ileti metnini alır `HRESULT` içinde kayıtlı `_com_error` nesnesi. Sistem ileti metni Win32 çağırılarak alınır [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) işlevi. Tarafından döndürülen dize ayrılmış `FormatMessage` API ve bunu serbest bırakıldığında `_com_error` nesne yok.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_error Sınıfı](../cpp/com-error-class.md)