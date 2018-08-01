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
ms.openlocfilehash: 9367e92110ba7fb232e89b9d950e491e5e8da5c7
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407175"
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
 HRESULT içinde kaydedilen için uygun sistem ileti metni alır `_com_error` nesne. Sistem ileti metni Win32 çağırılarak alınır [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351) işlevi. Tarafından döndürülen dize ayrılan `FormatMessage` API ve serbest bırakıldığında `_com_error` nesnesi yok edildiğinde.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_com_error Sınıfı](../cpp/com-error-class.md)