---
title: _com_error::Source | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Source
dev_langs:
- C++
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f722d1c4e8fc3d534403c2d18713e64dc2069011
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404905"
---
# <a name="comerrorsource"></a>_com_error::Source
**Microsoft'a özgü**  
  
 Çağrıları `IErrorInfo::GetSource` işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_bstr_t Source() const;  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sonucunu döndürür `IErrorInfo::GetSource` için `IErrorInfo` nesne kaydedilmiş içinde `_com_error` nesne. Ortaya çıkan `BSTR` içinde kapsüllenir bir `_bstr_t` nesne. Hayır ise `IErrorInfo` olan kaydedilmemişse, boş bir döndürür `_bstr_t`.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrılırken `IErrorInfo::GetSource` yöntemi göz ardı edilir.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_com_error Sınıfı](../cpp/com-error-class.md)