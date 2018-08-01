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
ms.openlocfilehash: c1389635c3ef026e8b3a7dfe13976cca58a15a82
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406724"
---
# <a name="comerrorcomerror"></a>_com_error::_com_error
**Microsoft'a özgü**  
  
 Oluşturur bir **_com_error** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_com_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = NULL,  
   bool fAddRef=false) throw( );  

_com_error( const _com_error& that ) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 *İK*  
 HRESULT bilgileri.  
  
 *perrinfo*  
 `IErrorInfo` nesne.  
  
 `bool fAddRef=false`  
 Null olmayan bir üzerinde AddRef çağırmasına neden `IErrorInfo` arabirimi. Bu doğru başvuru sayımı burada sahipliğini arabiriminin geçirilen içine ortak durumda sağlayan **_com_error** gibi nesnesi:  
  
```cpp 
throw _com_error(hr, perrinfo);  
```  
  
 Kodunuzun sahipliği istemiyorsanız **_com_error** nesnesi ve `AddRef` yıkıcısında `Release` içinde **_com_error** yıkıcı nesnesi olarak oluşturun aşağıdaki gibidir:  
  
```cpp 
_com_error err(hr, perrinfo, true);  
```  
  
 *,*  
 Mevcut bir **_com_error** nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucu bir HRESULT ve isteğe bağlı verilen yeni bir nesne oluşturur `IErrorInfo` nesne. İkincisi, varolan bir kopyasını oluşturur **_com_error** nesne.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_com_error Sınıfı](../cpp/com-error-class.md)