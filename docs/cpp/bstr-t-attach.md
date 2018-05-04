---
title: _bstr_t::Attach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eeb114a33d3ac356bff16aeab47b8d894b7513e6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="bstrtattach"></a>_bstr_t::Attach
**Microsoft özel**  
  
 Bağlantıları bir `_bstr_t` sarmalayıcı bir `BSTR`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      void Attach(  
   BSTR s  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *s*  
 `BSTR` değişkeniyle ilişkilendirilecek veya ona atanacak bir `_bstr_t`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_bstr_t` daha önce başka bir `BSTR` öğesine eklenmişse, `_bstr_t``BSTR` kaynağını temizler (başka hiçbir `_bstr_t` değişkeni `BSTR` öğesini kullanmıyorsa).  
  
## <a name="example"></a>Örnek  
 Bkz: [_bstr_t::Assign](../cpp/bstr-t-assign.md) kullanarak bir örnek için **Attach**.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_bstr_t Sınıfı](../cpp/bstr-t-class.md)