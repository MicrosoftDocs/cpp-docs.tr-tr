---
title: _com_error::Source | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::Source
dev_langs:
- C++
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a725ddb3ff72acc749a5dbf09d2ddcc94856590c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorsource"></a>_com_error::Source
**Microsoft özel**  
  
 Çağrıları **IErrorInfo::GetSource** işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
_bstr_t Source() const;  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sonucunu döndürür **IErrorInfo::GetSource** için **IErrorInfo** nesne kaydedilen içinde `_com_error` nesnesi. Elde edilen BSTR, `_bstr_t` nesnesinde kapsüllenir. Öyle değilse **IErrorInfo** olan kaydedilmiş boş döndürür `_bstr_t`.  
  
## <a name="remarks"></a>Açıklamalar  
 Arama sırasında herhangi bir hata **IErrorInfo::GetSource** yöntemi göz ardı edilir.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_error Sınıfı](../cpp/com-error-class.md)