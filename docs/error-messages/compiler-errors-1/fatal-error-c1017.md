---
title: "Önemli hata C1017 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1017
dev_langs: C++
helpviewer_keywords: C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 478a0a17ef8e0f0e6cb6589798d901837e7aff75
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1017"></a>Önemli hata C1017
Geçersiz tamsayı sabit ifade  
  
 İfade bir `#if` yönergesi yoktu veya bir sabite sonucu vermedi.  
  
 Kullanılarak tanımlanan sabitleri `#define` olarak kullanılıyorsa, bir tamsayı sabiti değerlendirmek değerlere sahip olmalıdır bir `#if`, `#elif`, veya `#else` yönergesi.  
  
 Aşağıdaki örnek C1017 oluşturur:  
  
```  
// C1017.cpp  
#define CONSTANT_NAME "YES"  
#if CONSTANT_NAME   // C1017  
#endif  
```  
  
 Olası çözüm:  
  
```  
// C1017b.cpp  
// compile with: /c  
#define CONSTANT_NAME 1  
#if CONSTANT_NAME  
#endif  
```  
  
 Çünkü `CONSTANT_NAME` bir dize ve bir tamsayı değerlendirir `#if` yönergesi önemli hatası C1017 oluşturur.  
  
 Diğer durumlarda, önişlemci tanımlanmamış sabit sıfır olarak değerlendirir. Aşağıdaki örnekte gösterildiği gibi bu, istenmeyen sonuçlara neden olabilir. `YES`sıfır olarak değerlendirilir şekilde, tanımlanmamıştır. İfade `#if` `CONSTANT_NAME` false ve kullanılacak kodu değerlendiren `YES` önişlemci tarafından kaldırılır. `NO`aynı zamanda tanımsız (sıfır), bu nedenle olan `#elif` `CONSTANT_NAME==NO` true olarak değerlendirilir (`0 == 0`), kodda bırakmayı önişlemci neden `#elif` deyim bölümü — tamamen planlanan davranış karşıtı.  
  
```  
// C1017c.cpp  
// compile with: /c  
#define CONSTANT_NAME YES  
#if CONSTANT_NAME  
   // Code to use on YES...  
#elif CONSTANT_NAME==NO  
   // Code to use on NO...  
#endif  
```  
  
 Tam olarak derleyici önişlemci yönergeleri nasıl işlediğini görmek için [/P](../../build/reference/p-preprocess-to-a-file.md), [/E](../../build/reference/e-preprocess-to-stdout.md), veya [/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md).