---
title: _bstr_t::operator = | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ed1de7a529d8c4c1b0d7ae8623d0f1c4a58b5075
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="bstrtoperator-"></a>_bstr_t::operator =
**Microsoft özel**  
  
 Var olan yeni bir değer atar `_bstr_t` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      _bstr_t& operator=(  
   const _bstr_t& s1   
) throw ( );  
_bstr_t& operator=(  
   const char* s2   
);  
_bstr_t& operator=(  
   const wchar_t* s3   
);  
_bstr_t& operator=(  
   const _variant_t& var   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *S1*  
 A `_bstr_t` mevcut bir atanacak nesne `_bstr_t` nesne.  
  
 *S2*  
 Varolan bir atanacak birden çok baytlı bir dize `_bstr_t` nesnesi.  
  
 `s3`  
 Varolan bir atanacak bir UNICODE dizesi `_bstr_t` nesnesi.  
  
 `var`  
 A `_variant_t` mevcut bir atanacak nesne `_bstr_t` nesne.  
  
 **SON Microsoft özel**  
  
## <a name="example"></a>Örnek  
 Bkz: [_bstr_t::Assign](../cpp/bstr-t-assign.md) kullanma örneği için `operator=`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_bstr_t Sınıfı](../cpp/bstr-t-class.md)