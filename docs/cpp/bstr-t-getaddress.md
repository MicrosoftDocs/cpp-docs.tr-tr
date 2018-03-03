---
title: _bstr_t::GetAddress | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetAddress
dev_langs:
- C++
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c1b2b348277f7d33a32c8d0e6ad1fc80d51ec68d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="bstrtgetaddress"></a>_bstr_t::GetAddress
**Microsoft özel**  
  
 Varolan bir dizeyi boşaltır ve yeni ayrılan bir dizenin adresini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
BSTR* GetAddress( );  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `BSTR` tarafından sarmalanan bir `_bstr_t` işaretçisi.  
  
## <a name="remarks"></a>Açıklamalar  
 `GetAddress`, `_bstr_t` paylaşan tüm `BSTR` nesnelerini etkiler. Kopya oluşturucu ve `_bstr_t` kullanılırsa `BSTR`'yi birden fazla `operator=` paylaşabilir.  
  
## <a name="example"></a>Örnek  
 Bkz: [_bstr_t::Assign](../cpp/bstr-t-assign.md) kullanarak bir örnek için `GetAddress`.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_bstr_t Sınıfı](../cpp/bstr-t-class.md)