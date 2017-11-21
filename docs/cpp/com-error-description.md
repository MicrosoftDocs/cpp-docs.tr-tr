---
title: _com_error::Description | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::Description
dev_langs: C++
helpviewer_keywords: Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c4bf868fd548cc7e0c72559f3754d7e1a035cfa5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [_com_error sınıfı](../cpp/com-error-class.md)