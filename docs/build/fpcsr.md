---
title: Olamayan FpCsr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: dff95d5d-7589-4432-82db-64b459c24352
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9defb41a026b32acb4375185f14c903788b91a23
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fpcsr"></a>FpCsr
Kayıt durumu da x87 içerir FPU denetim sözcüğü. Çağırma kuralı kalıcı olması için bu kayıt belirler.  
  
 FPU denetim sözcük kaydı başlangıcında aşağıdaki standart değerlere ayarlanır x87 yürütme program:  
  
```  
FPCSR[0:6]: Exception masks all 1's (all exceptions masked)  
FPCSR[7]: Reserved - 0  
FPCSR[8:9]: Precision Control - 10B (double precision)  
FPCSR[10:11]: Rounding  control - 0 (round to nearest)  
FPCSR[12]: Infinity control - 0 (not used)  
```  
  
 Tüm alanları olamayan FPCSR içinde değiştirir Aranan bunları çağırıcısına döndürmeden önce geri yüklemeniz gerekir. Ayrıca, bu alanların hiçbirini değiştirdi çağıran bunları standart değerlerine anlaşmayla Aranan değiştirilen değerleri bekliyor olmadıkça çağrılan çağırmadan önce geri yüklemeniz gerekir.  
  
 Denetim bayrakları olmayan-volatilite ilgili kuralları için iki özel durum vardır:  
  
1.  Verilen işlevin belgelenen amacı geçici olamayan FpCsr değiştirme olduğu işlevlerde işaretler.  
  
2.  Kanıtlanabilir olduğunda bu kuralları ihlali davranır/burada bu kurallar, örneğin, tüm program Analizi ile ihlal edilmemesi bir program ile aynı yol bir programlarda sonuçları düzeltin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağırma Kuralı](../build/calling-convention.md)