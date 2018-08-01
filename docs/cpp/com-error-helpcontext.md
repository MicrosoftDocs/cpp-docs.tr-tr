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
ms.openlocfilehash: b1edf990697aa6becca0ad377f18e8f7045c96a4
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401850"
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext
**Microsoft'a özgü**  
  
 Çağrıları `IErrorInfo::GetHelpContext` işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
DWORD HelpContext( ) const throw( );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sonucunu döndürür `IErrorInfo::GetHelpContext` için `IErrorInfo` nesne kaydedilmiş içinde `_com_error` nesne. Hayır ise `IErrorInfo` nesnesi kaydedilmezse, sıfır döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrılırken `IErrorInfo::GetHelpContext` yöntemi göz ardı edilir.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_com_error Sınıfı](../cpp/com-error-class.md)