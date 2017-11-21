---
title: _bstr_t::GetBSTR | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _bstr_t::GetBSTR
dev_langs: C++
helpviewer_keywords: GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7b8a66c9bf40ccb1467b0679f567a79bfd065315
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="bstrtgetbstr"></a>_bstr_t::GetBSTR
**Microsoft özel**  
  
 Başlangıcına işaret `BSTR` tarafından Sarmalanan `_bstr_t`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
BSTR& GetBSTR( );  
  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başlangıcı `BSTR` tarafından Sarmalanan `_bstr_t`.  
  
## <a name="remarks"></a>Açıklamalar  
 `GetBSTR`, `_bstr_t` paylaşan tüm `BSTR` nesnelerini etkiler. Kopya oluşturucu ve `_bstr_t` kullanılırsa `BSTR`'yi birden fazla `operator=` paylaşabilir.  
  
## <a name="example"></a>Örnek  
 Bkz: [_bstr_t::Assign](../cpp/bstr-t-assign.md) kullanarak bir örnek için `GetBSTR`.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_bstr_t sınıfı](../cpp/bstr-t-class.md)