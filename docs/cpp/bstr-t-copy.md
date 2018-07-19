---
title: _bstr_t::Copy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::copy
dev_langs:
- C++
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d23f204e7e8a545fbee7ab516495ed711d7984a9
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948165"
---
# <a name="bstrtcopy"></a>_bstr_t::copy
**Microsoft'a özgü**  
  
 Kapsüllenmiş bir kopyasını oluşturur `BSTR`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
BSTR copy( bool fCopy = true ) const;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *fCopy*  
 TRUE ise `copy` kapsanan bir kopyasını döndürür `BSTR`, aksi halde `copy` gerçek BSTR'yi döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Kapsüllenmiş `BSTR` nesnesinin yeni ayrılmış bir kopyasını döndürür.  
  
## <a name="example"></a>Örnek  
  
```cpp 
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t  
   *pVal = m_bsConStr.copy();  
}  
```  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_bstr_t Sınıfı](../cpp/bstr-t-class.md)