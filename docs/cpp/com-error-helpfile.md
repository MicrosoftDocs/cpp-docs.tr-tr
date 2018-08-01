---
title: _com_error::HelpFile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HelpFile
dev_langs:
- C++
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3afcda41d5dc4ad3cc1fd74ed5449d574946f1e5
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402048"
---
# <a name="comerrorhelpfile"></a>_com_error::HelpFile
**Microsoft'a özgü**  
  
 Çağrıları `IErrorInfo::GetHelpFile` işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_bstr_t HelpFile() const;  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sonucunu döndürür `IErrorInfo::GetHelpFile` için `IErrorInfo` nesne kaydedilmiş içinde `_com_error` nesne. Elde edilen BSTR, `_bstr_t` nesnesinde kapsüllenir. Hayır ise `IErrorInfo` olan kaydedilmemişse, boş bir döndürür `_bstr_t`.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrılırken `IErrorInfo::GetHelpFile` yöntemi göz ardı edilir.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_com_error Sınıfı](../cpp/com-error-class.md)