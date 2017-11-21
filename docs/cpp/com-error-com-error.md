---
title: _com_error::_com_error | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::_com_error
dev_langs: C++
helpviewer_keywords: _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 440151fd8b8cd7d28b1e2a9ad951e238ae41dffb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comerrorcomerror"></a>_com_error::_com_error
**Microsoft özel**  
  
 Oluşturan bir `_com_error` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      _com_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = NULL,  
   bool fAddRef=false  
) throw( );  
_com_error(  
   const _com_error& that   
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `hr`  
 `HRESULT` bilgileri.  
  
 `perrinfo`  
 **IErrorInfo** nesnesi.  
  
 **bool fAddRef = false**  
 AddRef null olmayan bir üzerinde çağırmak Oluşturucusu neden **IErrorInfo** arabirimi. Bu, sık karşılaşılan arabirim sahipliğinin `_com_error` nesnesine geçirildiği durumda doğru başvuru sayımı sağlar; örneğin:  
  
```  
throw _com_error(hr, perrinfo);  
```  
  
 Kodunuzu sahipliği geçirmek istemiyorsanız `_com_error` nesnesi ve `AddRef` dengelemek için gerekli **sürüm** içinde `_com_error` yıkıcı nesnesi aşağıdaki gibi oluşturun:  
  
```  
_com_error err(hr, perrinfo, true);  
```  
  
 `that`  
 Varolan bir `_com_error` nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucusu verilen yeni bir nesne oluşturur bir `HRESULT` ve isteğe bağlı **IErrorInfo** nesnesi. İkincisi, varolan `_com_error` nesnesinin bir kopyasını oluşturur.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_error sınıfı](../cpp/com-error-class.md)