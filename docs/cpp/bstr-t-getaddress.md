---
title: _bstr_t::GetAddress | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _bstr_t::GetAddress
dev_langs: C++
helpviewer_keywords: GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5921b3091532c63e3ba92d6e6e74f29a85123ac1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [_bstr_t sınıfı](../cpp/bstr-t-class.md)