---
title: _com_error::ErrorMessage | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::ErrorMessage
dev_langs: C++
helpviewer_keywords: ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0b60c0f74cd350382b6cf8669361087dee601fe4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [_com_error sınıfı](../cpp/com-error-class.md)