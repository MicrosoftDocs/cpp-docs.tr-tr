---
title: _com_error::HelpContext | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HelpContext
dev_langs:
- C++
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7123fcf5859ce3fc373b29b4cb3e7b32109b464e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext
**Microsoft özel**  
  
 Çağrıları **IErrorInfo::GetHelpContext** işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
DWORD HelpContext( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sonucunu döndürür **IErrorInfo::GetHelpContext** için **IErrorInfo** nesne kaydedilen içinde `_com_error` nesnesi. Öyle değilse **IErrorInfo** nesne kaydedilir, sıfır döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Arama sırasında herhangi bir hata **IErrorInfo::GetHelpContext** yöntemi göz ardı edilir.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_error Sınıfı](../cpp/com-error-class.md)