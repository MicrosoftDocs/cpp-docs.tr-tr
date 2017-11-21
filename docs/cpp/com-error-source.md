---
title: _com_error::Source | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::Source
dev_langs: C++
helpviewer_keywords: Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 01f63158f2406505e833ab58dcb53e099c3348f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [_com_error sınıfı](../cpp/com-error-class.md)