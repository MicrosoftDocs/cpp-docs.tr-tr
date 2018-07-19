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
ms.openlocfilehash: f904fa11195c27f8e08856ef391d0ba8adbedece
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939683"
---
# <a name="comerrorsource"></a>_com_error::Source
**Microsoft'a özgü**  
  
 Çağrıları `IErrorInfo::GetSource` işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
_bstr_t Source() const;  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sonucunu döndürür `IErrorInfo::GetSource` için `IErrorInfo` nesne kaydedilmiş içinde `_com_error` nesne. Elde edilen BSTR, `_bstr_t` nesnesinde kapsüllenir. Hayır ise `IErrorInfo` olan kaydedilmemişse, boş bir döndürür `_bstr_t`.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrılırken `IErrorInfo::GetSource` yöntemi göz ardı edilir.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_error Sınıfı](../cpp/com-error-class.md)