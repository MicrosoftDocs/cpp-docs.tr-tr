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
ms.openlocfilehash: ec16faa9881fc1c69dca5f8f39b8797cf0fcff0d
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948110"
---
# <a name="comerrorcomerror"></a>_com_error::_com_error
**Microsoft'a özgü**  
  
 Oluşturur bir `_com_error` nesne.  
  
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
 Null olmayan bir üzerinde AddRef çağırmasına neden `IErrorInfo` arabirimi. Bu, sık karşılaşılan arabirim sahipliğinin `_com_error` nesnesine geçirildiği durumda doğru başvuru sayımı sağlar; örneğin:  
  
```cpp 
throw _com_error(hr, perrinfo);  
```  
  
 Kodunuzun sahipliği istemiyorsanız `_com_error` nesnesi ve `AddRef` yıkıcısında `Release` içinde `_com_error` yok Edicisi, nesneyi şu şekilde oluşturun:  
  
```cpp 
_com_error err(hr, perrinfo, true);  
```  
  
 *,*  
 Varolan bir `_com_error` nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucu bir HRESULT ve isteğe bağlı verilen yeni bir nesne oluşturur `IErrorInfo` nesne. İkincisi, varolan `_com_error` nesnesinin bir kopyasını oluşturur.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_error Sınıfı](../cpp/com-error-class.md)