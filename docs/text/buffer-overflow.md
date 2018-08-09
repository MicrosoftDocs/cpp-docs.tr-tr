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
ms.openlocfilehash: 9bb362be360986371200c8cde292b3fff5acd7cd
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020193"
---
# <a name="buffer-overflow"></a>Arabellek Taşması
Karakter boyutları değişen bir arabelleğe karakter yerleştirdiğinizde sorunlara neden olabilir. Karakterleri bir dizeden kopyalar, aşağıdaki kodu düşünün `sz`, bir arabelleğine `rgch`:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
    rgch[ cb++ ] = *sz++;  
```  
  
 Soru: olan son bayt bir ön bayt kopyalanır? Olası Arabellek Taşması çünkü aşağıdaki sorunu çözmez:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 `_mbccpy` Çağrı çalışır doğru şeyi yapmak: 1 veya 2 bayt olup tam karakter kopyalayın. Ancak, 2 bayt genişliğinde karakter değilse kopyalanan son karakter arabelleği uymayabilir dikkate almaz. Doğru çözümdür:  
  
```  
cb = 0;  
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 Bu kodu test döngüsünde olası arabellek taşması kullanmadan test `_mbclen` işaret ettiği geçerli karakter boyutunu test etmek için `sz`. Bir çağrı yaparak `_mbsnbcpy` işlevi, kodda değiştirebilirsiniz **sırada** tek satırlık bir kod ile döngüsü. Örneğin:  
  
```  
_mbsnbcpy( rgch, sz, sizeof( rgch ) );  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MBCS Programlama İpuçları](../text/mbcs-programming-tips.md)