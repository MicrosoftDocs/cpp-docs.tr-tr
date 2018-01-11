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
ms.workload: cplusplus
ms.openlocfilehash: 00b2f7f487673c67aa7b681499462ea05a471b48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [_bstr_t Sınıfı](../cpp/bstr-t-class.md)