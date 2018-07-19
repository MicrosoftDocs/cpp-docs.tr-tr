---
title: _com_error::ErrorInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 52935c81849ded072cb20d6c835b3a71b66c2871
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941320"
---
# <a name="comerrorerrorinfo"></a>_com_error::ErrorInfo
**Microsoft'a özgü**  
  
 Alır `IErrorInfo` oluşturucuya nesnesi geçirildi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
IErrorInfo * ErrorInfo( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Ham `IErrorInfo` öğesi oluşturucuya geçirilen.  
  
## <a name="remarks"></a>Açıklamalar  
 Kapsüllenmiş alır `IErrorInfo` öğesi bir `_com_error` nesne veya hiç yoksa NULL `IErrorInfo` öğesi kaydedilir. Çağıranın çağırmalıdır `Release` bittiğinde, döndürülen nesneyi kullanmayı.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_error Sınıfı](../cpp/com-error-class.md)