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
ms.openlocfilehash: f9f69811b7b25a793d11ef6d53aaf0638c752a11
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408622"
---
# <a name="bstrtattach"></a>_bstr_t::Attach
**Microsoft'a özgü**  
  
 Bağlantılar bir `_bstr_t` sarmalayıcısını bir `BSTR`.  
  
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
 Bkz: [_bstr_t::Assign](../cpp/bstr-t-assign.md) bir örnek için **iliştirme**.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_bstr_t Sınıfı](../cpp/bstr-t-class.md)