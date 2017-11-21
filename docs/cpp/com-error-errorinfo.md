---
title: _com_error::ErrorInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::ErrorInfo
dev_langs: C++
helpviewer_keywords: ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3e968a3b9814aeec898d4e157781b58c40a87e25
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [_com_error sınıfı](../cpp/com-error-class.md)