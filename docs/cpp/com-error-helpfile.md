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
ms.openlocfilehash: a1f02238d228b5de4302812bacf4f9ad5cf1300c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 [_com_error Sınıfı](../cpp/com-error-class.md)