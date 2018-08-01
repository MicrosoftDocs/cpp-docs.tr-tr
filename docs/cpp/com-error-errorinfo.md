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
ms.openlocfilehash: f3f4d105efb7269c0c1344d6a9399ebbe4fa9fd2
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404300"
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_com_error Sınıfı](../cpp/com-error-class.md)