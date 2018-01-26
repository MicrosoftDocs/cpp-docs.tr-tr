---
title: Setjmp longjmp kullanma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- longjmp_cpp
- setjmp_cpp
dev_langs: C++
helpviewer_keywords:
- C++ exception handling, setjmp/longjmp functions
- setjmpex.h
- longjmp function in C++ programs
- setjmp.h
- setjmp function
- setjmp function, C++ programs
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3fede2e7865ab002d77a174a28928df491b29981
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="using-setjmplongjmp"></a>setjmp/longjmp Kullanma
Zaman [setjmp](../c-runtime-library/reference/setjmp.md) ve [longjmp](../c-runtime-library/reference/longjmp.md) olan birlikte kullanıldığında, yerel olmayan yürütmek için bir yol sağladıkları `goto`. Bunlar, genellikle standart arama kullanmadan önce çağrılan bir yordam hata işleme veya kurtarma kodunda yürütme denetimi geçirmek için kullanılan veya kuralları döndürür.  
  
> [!CAUTION]
>  Ancak, çünkü `setjmp` ve `longjmp` C++ nesne semantiği desteklemez ve yerel değişkenler en iyi duruma getirilmesi engelleyerek performansını azaltabilir, bunları C++ programlarında kullanmamanızı öneririz. Kullanmanızı öneririz `try` / `catch` yerine oluşturur.  
  
 Kullanmaya karar verirseniz `setjmp` / `longjmp` bir C++ programı da dahil \<setjmp.h'ı > veya \<setjmpex.h > işlevleri ve C++ özel durum işleme arasında doğru etkileşim güvence altına almak için. Kullanırsanız [/EH](../build/reference/eh-exception-handling-model.md) derlemek için yerel nesneleri için Yıkıcılar yığını geriye doğru izleme sırasında denir. Kullanırsanız **/EHs** derleme ve, işlev çağrıları kullanan bir işlev bir biri [nothrow](../cpp/nothrow-cpp.md) ve kullanan bir işlev `nothrow` çağrıları `longjmp`, yıkıcı bırakma gerçekleşmeyebilir sonra İyileştirici bağlı olarak.  
  
 Taşınabilir kodda, yerel olmayan zaman `goto` çağırır `longjmp` yürütüldüğünde, çerçeve tabanlı nesnelerin doğru yok etme güvenilir olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C (Yapılandırılmış) ile C++ Özel Durumlarını Karıştırma](../cpp/mixing-c-structured-and-cpp-exceptions.md)