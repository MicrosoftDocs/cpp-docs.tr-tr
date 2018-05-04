---
title: _com_error::GUID | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::GUID
dev_langs:
- C++
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee1952e50251cfac7563357c7626ab8603589e4d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="comerrorguid"></a>_com_error::GUID
**Microsoft özel**  
  
 Çağrıları **IErrorInfo::GetGUID** işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
GUID GUID( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sonucunu döndürür **IErrorInfo::GetGUID** için **IErrorInfo** nesne kaydedilen içinde `_com_error` nesnesi. Öyle değilse **IErrorInfo** nesne kaydedilir, döndürür `GUID_NULL`.  
  
## <a name="remarks"></a>Açıklamalar  
 Arama sırasında herhangi bir hata **IErrorInfo::GetGUID** yöntemi göz ardı edilir.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_error Sınıfı](../cpp/com-error-class.md)