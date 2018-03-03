---
title: _com_error::Description | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::Description
dev_langs:
- C++
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f3ed306a8eba4e76c2eefc738b617117188e85c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comerrordescription"></a>_com_error::Description
**Microsoft özel**  
  
 Çağrıları **IErrorInfo::GetDescription** işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
_bstr_t Description( ) const;  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sonucunu döndürür **IErrorInfo::GetDescription** için **IErrorInfo** nesne kaydedilen içinde `_com_error` nesnesi. Elde edilen `BSTR` içinde kapsüllenir bir `_bstr_t` nesnesi. Öyle değilse **IErrorInfo** olan kaydedilmiş boş döndürür `_bstr_t`.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrıları **IErrorInfo::GetDescription** işlevi ve alır **IErrorInfo** içinde kayıtlı `_com_error` nesnesi. Arama sırasında herhangi bir hata **IErrorInfo::GetDescription** yöntemi göz ardı edilir.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_error Sınıfı](../cpp/com-error-class.md)