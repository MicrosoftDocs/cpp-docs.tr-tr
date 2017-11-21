---
title: _com_error::HelpFile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::HelpFile
dev_langs: C++
helpviewer_keywords: HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8b29120a15af3a494ad2a755f83342b3a6b83908
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comerrorhelpfile"></a>_com_error::HelpFile
**Microsoft özel**  
  
 Çağrıları **IErrorInfo::GetHelpFile** işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
_bstr_t HelpFile() const;  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sonucunu döndürür **IErrorInfo::GetHelpFile** için **IErrorInfo** nesne kaydedilen içinde `_com_error` nesnesi. Elde edilen BSTR, `_bstr_t` nesnesinde kapsüllenir. Öyle değilse **IErrorInfo** olan kaydedilmiş boş döndürür `_bstr_t`.  
  
## <a name="remarks"></a>Açıklamalar  
 Arama sırasında herhangi bir hata **IErrorInfo::GetHelpFile** yöntemi göz ardı edilir.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_error sınıfı](../cpp/com-error-class.md)