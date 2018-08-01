---
title: _bstr_t::operator = | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.assetid: fb31bb1b-ce29-4388-b5fd-8dac830cf18a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3dfed780e0769e342ff368af453fc70764a372f0
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404479"
---
# <a name="bstrtoperator-"></a>_bstr_t::operator =
**Microsoft'a özgü**  
  
 Mevcut bir yeni bir değer atar `_bstr_t` nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_bstr_t& operator=(const _bstr_t& s1) throw ( );  
_bstr_t& operator=(const char* s2);  
_bstr_t& operator=(const wchar_t* s3);  
_bstr_t& operator=(const _variant_t& var);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *S1*  
 A `_bstr_t` varolan atanacak nesne `_bstr_t` nesne.  
  
 *S2*  
 Mevcut bir atanacak çok baytlı bir dize `_bstr_t` nesne.  
  
 *S3*  
 Mevcut bir atanacak bir Unicode dize `_bstr_t` nesne.  
  
 *var*  
 A `_variant_t` varolan atanacak nesne `_bstr_t` nesne.  
  
 **END Microsoft özgü**  
  
## <a name="example"></a>Örnek  
 Bkz: [_bstr_t::Assign](../cpp/bstr-t-assign.md) kullanma örneği için **işleç =**.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_bstr_t Sınıfı](../cpp/bstr-t-class.md)