---
title: MxCsr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4f3c229d-0862-4733-acc7-9ed7a0b870ce
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7794cea8906440c0adca94791d08e3ced6af747e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mxcsr"></a>MxCsr
Kayıt durumu MxCsr de içerir. Çağırma kuralı bu kayıt geçici ve kalıcı bir bölümü olarak böler. Volatile bölümü 6 durumu bayrakları, MXCSR oluşur [0:5], MXCSR [6:15] kaydı geri kalanı kalıcı olarak değerlendirilir.  
  
 Kalıcı bölümü, program yürütme başlangıcında aşağıdaki standart değerlere ayarlanır:  
  
```  
MXCSR[6]         : Denormals are zeros - 0  
MXCSR[7:12]      : Exception masks all 1's (all exceptions masked)  
MXCSR[13:14]   : Rounding  control - 0 (round to nearest)  
MXCSR[15]      : Flush to zero for masked underflow - 0 (off)  
```  
  
 MXCSR içindeki kalıcı alanlar değiştirir Aranan bunları çağırıcısına döndürmeden önce geri yüklemeniz gerekir. Ayrıca, bu alanların hiçbirini değiştirdi çağıran bunları standart değerlerine anlaşmayla Aranan değiştirilen değerleri bekliyor olmadıkça çağrılan çağırmadan önce geri yüklemeniz gerekir.  
  
 Denetim bayrakları olmayan-volatilite ilgili kuralları için iki özel durum vardır:  
  
-   Verilen işlevin belgelenen amacı geçici olamayan MxCsr değiştirme olduğu işlevlerde işaretler.  
  
-   Kanıtlanabilir olduğunda bu kuralları ihlali davranır/burada bu kurallar, örneğin, tüm program Analizi ile ihlal edilmemesi bir program ile aynı yol bir programlarda sonuçları düzeltin.  
  
 Hiçbir varsayımlar özellikle bir işlevin belgelerinde açıklanan sürece MXCSR geçici kısmının işlevi sınır arasında durumuyla ilgili yapılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağırma Kuralı](../build/calling-convention.md)