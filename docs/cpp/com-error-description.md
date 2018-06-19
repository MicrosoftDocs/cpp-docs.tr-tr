---
title: _com_error::Description | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Description
dev_langs:
- C++
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7df1fb3a8ca600b888e5d6f2c51fc44fda17dd27
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32414265"
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