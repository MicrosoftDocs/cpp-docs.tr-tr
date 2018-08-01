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
ms.openlocfilehash: c592607732eb5558ce74edb7b71adbc023b2ae52
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402289"
---
# <a name="comerrorguid"></a>_com_error::GUID
**Microsoft'a özgü**  
  
 Çağrıları `IErrorInfo::GetGUID` işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
GUID GUID( ) const throw( );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sonucunu döndürür `IErrorInfo::GetGUID` için `IErrorInfo` nesne kaydedilmiş içinde `_com_error` nesne. Hayır ise `IErrorInfo` nesnesi kaydedilmezse döndürür `GUID_NULL`.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrılırken `IErrorInfo::GetGUID` yöntemi göz ardı edilir.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_com_error Sınıfı](../cpp/com-error-class.md)