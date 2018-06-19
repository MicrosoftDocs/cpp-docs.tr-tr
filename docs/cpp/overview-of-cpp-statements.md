---
title: C++ deyimlerine genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements [C++]
ms.assetid: e56996b2-b846-4b99-ac94-ac72fffc5ec7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2858807816178115dd34c05d6c88c3dd6fecdee3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32421753"
---
# <a name="overview-of-c-statements"></a>C++ Deyimlerine Genel Bakış
C++ deyimlerine ne zaman bir ifade deyimi, bir seçim deyimi, bir yineleme deyimi veya atlama deyimi özellikle bu dizisi değiştirir dışında ardışık olarak yürütülür.  
  
 Deyimlerini aşağıdaki türden biri olabilir:  
  
```  
  
labeled-statement  
expression-statement  
compound-statement  
selection-statement  
iteration-statement  
jump-statement  
declaration-statement  
try-throw-catch  
  
```  
  
 Çoğu durumda, C++ deyimi sözdizimi, ANSI c aynıdır C'de olan iki arasındaki birincil fark, bildirimler yalnızca bir bloğun başlangıcında izin verilir; C++ ekler *bildirimi deyimi*, etkili bir şekilde kaldıran bu kısıtlama. Bu, önceden hesaplanan başlatma değeri burada hesaplanabilir programı bir noktada değişkenleri tanıtmak sağlar.  
  
 Blokları içinde değişkenleri bildirme ayrıca değişkenlere ömrü ve kapsamını üzerinden kesin bir denetim sağlar.  
  
 Aşağıdaki C++ anahtar sözcükleri deyimleri konularda açıklanmıştır:  
  
|||||  
|-|-|-|-|  
|[break](../cpp/break-statement-cpp.md)|[else](../cpp/if-else-statement-cpp.md)|[__if_exists](../cpp/if-exists-statement.md)|[__try](../cpp/structured-exception-handling-c-cpp.md)|  
|[Durumu](../cpp/switch-statement-cpp.md)|[__except](../cpp/structured-exception-handling-c-cpp.md)|[__if_not_exists](../cpp/if-not-exists-statement.md)|[Deneyin](../cpp/try-throw-and-catch-statements-cpp.md)|  
|[Yakalama](../cpp/try-throw-and-catch-statements-cpp.md)|[for](../cpp/for-statement-cpp.md)|[__leave](../c-language/try-finally-statement-c.md)|[while](../cpp/while-statement-cpp.md)|  
|[continue](../cpp/continue-statement-cpp.md)|[goto](../cpp/goto-statement-cpp.md)|[return](../cpp/return-statement-cpp.md)||  
|[default](../cpp/switch-statement-cpp.md)|[__finally](../cpp/structured-exception-handling-c-cpp.md)|[switch](../cpp/switch-statement-cpp.md)||  
|[do](../cpp/do-while-statement-cpp.md)|[Eğer](../cpp/if-else-statement-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)||  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Deyimler](../cpp/statements-cpp.md)