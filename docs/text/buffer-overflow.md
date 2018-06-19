---
title: Arabellek Taşması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- buffers [C++], character sizes
- buffer overflows [C++]
- MBCS [C++], buffer overflow
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13d01460e7ed9cb95d92303d82ea136803737331
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854658"
---
# <a name="buffer-overflow"></a>Arabellek Taşması
Karakter boyutları değişen bir arabelleğe karakter geçirdiğinizde sorunlara neden olabilir. Bir dizeden karakterleri kopyalar, aşağıdaki kodu düşünün `sz`, arabellek içine, `rgch`:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
    rgch[ cb++ ] = *sz++;  
```  
  
 Soru: olan son bayta kalan baytı kopyalanır? Olası Arabellek Taşması çünkü aşağıdaki sorunu çözmez:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 `_mbccpy` Çağrısı çalışır doğru olanı yapmak: 1 veya 2 bayt olsun tam karakter kopyalayın. Ancak karakter 2 bayt genişliğinde ise kopyalanan son karakterin arabellek uyduğundan değil dikkate almaz. Doğru çözümdür:  
  
```  
cb = 0;  
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 Bu kod testleri olası arabellek taşması döngüsünde kullanarak test `_mbclen` gösterdiği geçerli karakteri boyutunu test etmek için `sz`. Çağrı yaparak `_mbsnbcpy` işlevi, kodda değiştirilebilir `while` döngü tek satırlık bir kod ile. Örneğin:  
  
```  
_mbsnbcpy( rgch, sz, sizeof( rgch ) );  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MBCS Programlama İpuçları](../text/mbcs-programming-tips.md)