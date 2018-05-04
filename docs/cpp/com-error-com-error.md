---
title: _com_error::_com_error | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::_com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d26239f6edf98e90f9d4d773d654025da410a97
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 [_com_error Sınıfı](../cpp/com-error-class.md)