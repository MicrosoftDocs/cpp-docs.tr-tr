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
ms.openlocfilehash: 8fbc735dfae1b30209eccfd14f1170826fb07680
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="comerrorerrorinfo"></a>_com_error::ErrorInfo
**Microsoft özel**  
  
 Alır **IErrorInfo** oluşturucuya nesnesi geçirildi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
IErrorInfo * ErrorInfo( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Ham **IErrorInfo** öğesi oluşturucuya geçirilen.  
  
## <a name="remarks"></a>Açıklamalar  
 Kapsüllenmiş alır **IErrorInfo** öğesi bir `_com_error` nesnesi veya **NULL** yoksa **IErrorInfo** öğesi kaydedilir. Arayan çağırmalısınız **sürüm** bitirdikten sonra döndürülen nesne üzerinde kullanıyor.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_error Sınıfı](../cpp/com-error-class.md)