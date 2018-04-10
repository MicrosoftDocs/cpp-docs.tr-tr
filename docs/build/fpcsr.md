---
title: Olamayan FpCsr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: dff95d5d-7589-4432-82db-64b459c24352
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 15b7caebc99c4724c0e28b7812da8ef224184385
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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