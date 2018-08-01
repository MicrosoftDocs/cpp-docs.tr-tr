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
ms.openlocfilehash: 426709857447d972365aa034059bcd34305d6d40
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402516"
---
# <a name="overview-of-c-statements"></a>C++ Deyimlerine Genel Bakış
C++ deyimlerine zaman bir ifade deyimi, bir seçim deyimi, bir yineleme deyimi veya bir atlama deyimi özellikle ilgili dizisini değiştirir dışında ardışık olarak yürütülür.  
  
 Deyimlerini aşağıdaki türde olabilir:  
  
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
  
 Çoğu durumda, C++ deyimi sözdizimi, ANSI c aynıdır C dilinde olan iki arasındaki başlıca fark, bildirimlerine yalnızca bir blok başlangıcında izin; C++ ekler *bildirim deyimindeki*, etkili bir şekilde kaldıran bu kısıtlama. Bu, önceden başlatma değeri burada hesaplanabilir programda bir noktada değişkenleri tanıtmak sağlar.  
  
 Blokları içindeki değişkenleri bildirme kapsamı ve bu değişkenlerin ömrünü üzerinde kesin denetim uygulamak amacıyla sağlar.  
  
 Aşağıdaki C++ anahtar sözcükleri deyimleri konular açıklanmaktadır:  
  
|||||  
|-|-|-|-|  
|[break](../cpp/break-statement-cpp.md)|[else](../cpp/if-else-statement-cpp.md)|[__if_exists](../cpp/if-exists-statement.md)|[__try](../cpp/structured-exception-handling-c-cpp.md)|  
|[Servis talebi](../cpp/switch-statement-cpp.md)|[__except](../cpp/structured-exception-handling-c-cpp.md)|[__if_not_exists](../cpp/if-not-exists-statement.md)|[deneyin](../cpp/try-throw-and-catch-statements-cpp.md)|  
|[Yakalama](../cpp/try-throw-and-catch-statements-cpp.md)|[for](../cpp/for-statement-cpp.md)|[__leave](../c-language/try-finally-statement-c.md)|[while](../cpp/while-statement-cpp.md)|  
|[continue](../cpp/continue-statement-cpp.md)|[goto](../cpp/goto-statement-cpp.md)|[return](../cpp/return-statement-cpp.md)||  
|[default](../cpp/switch-statement-cpp.md)|[__finally](../cpp/structured-exception-handling-c-cpp.md)|[switch](../cpp/switch-statement-cpp.md)||  
|[do](../cpp/do-while-statement-cpp.md)|[Eğer](../cpp/if-else-statement-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)||  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Deyimler](../cpp/statements-cpp.md)